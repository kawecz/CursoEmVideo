
---
# [[06 - ALTER TABLE DROP TABLE.pdf#page=4&selection=15,0,16,65|Adicionando uma nova Coluna]]

Para **adicionar uma nova coluna em uma tabela no MySQL**, você usa o comando **`ALTER TABLE`** junto com **`ADD COLUMN`**.

### **Sintaxe básica**

```sql
ALTER TABLE nome_da_tabela
ADD COLUMN nome_da_coluna tipo_da_coluna [restrições];
```

### **Explicando:**

- `nome_da_tabela` → a tabela onde você quer adicionar a coluna.
    
- `nome_da_coluna` → o nome que a nova coluna terá.
    
- `tipo_da_coluna` → tipo de dado (ex.: `INT`, `VARCHAR(100)`, `DATE`, etc.).
    
- `[restrições]` → opcional (ex.: `NOT NULL`, `DEFAULT`, `UNIQUE`).
    

---

### **Exemplos práticos**

1. **Adicionar uma coluna de texto simples:**
    

```sql
ALTER TABLE clientes
ADD COLUMN telefone VARCHAR(20);
```

> Aqui criamos uma coluna `telefone` que pode armazenar até 20 caracteres.

2. **Adicionar uma coluna com valor padrão:**
    

```sql
ALTER TABLE pedidos
ADD COLUMN status VARCHAR(20) DEFAULT 'pendente';
```

> Todos os registros existentes receberão o valor padrão `'pendente'`.

3. **Adicionar uma coluna obrigatória (NOT NULL):**
    

```sql
ALTER TABLE funcionarios
ADD COLUMN data_admissao DATE NOT NULL;
```

> Isso exige que toda nova linha inserida tenha uma data de admissão.

4. **Escolher a posição da nova coluna:**
    

- Colocar **no início da tabela**:
    

```sql
ALTER TABLE clientes
ADD COLUMN idade INT FIRST;
```

- Colocar **depois de uma coluna específica**:
    

```sql
ALTER TABLE clientes
ADD COLUMN cidade VARCHAR(50) AFTER nome;
```

---

### **Resumo rápido**

- Use `ALTER TABLE ... ADD COLUMN ...`.
    
- Defina o tipo de dado corretamente.
    
- Pode usar `DEFAULT`, `NOT NULL`, `UNIQUE`, etc.
    
- Pode controlar a posição da coluna com `FIRST` ou `AFTER`.
    

---
# [[06 - ALTER TABLE DROP TABLE.pdf#page=5&selection=13,0,14,65|Removendo uma Coluna]]

Para **remover uma coluna em uma tabela no MySQL**, também usamos o comando **`ALTER TABLE`**, mas agora com **`DROP COLUMN`**.

### **Sintaxe básica**

```sql
ALTER TABLE nome_da_tabela
DROP COLUMN nome_da_coluna;
```

---

### **Exemplos práticos**

1. **Remover uma coluna simples:**
    

```sql
ALTER TABLE clientes
DROP COLUMN telefone;
```

> Isso remove a coluna `telefone` da tabela `clientes`.

2. **Remover várias colunas de uma vez:**
    

```sql
ALTER TABLE pedidos
DROP COLUMN desconto,
DROP COLUMN observacao;
```

> Remove `desconto` e `observacao` de uma só vez.

3. **Cuidados importantes:**
    

- Depois de remover a coluna, todos os dados dela serão **perdidos permanentemente**.
    
- Não há como “desfazer” direto, só restaurando de backup.
    
- Se a coluna for usada em **índices, chaves estrangeiras ou constraints**, você precisará remover essas restrições antes.
    

---

### **Resumo rápido**

- `ALTER TABLE ... DROP COLUMN ...;` → remove uma coluna.
    
- Pode remover várias colunas de uma vez separando por vírgula.
    
- Dados daquela coluna serão apagados permanentemente.
    
- Verifique se não há chaves/índices usando a coluna antes de remover.
    

---
# [[06 - ALTER TABLE DROP TABLE.pdf#page=6&selection=19,0,19,30|Escolhendo a Posição da Coluna]]


No **MySQL**, quando você adiciona uma coluna com `ALTER TABLE ... ADD COLUMN`, pode escolher **em que posição** ela vai aparecer na tabela.


### **Opções para posicionar colunas**

1. **Adicionar no final da tabela (padrão):**
    

```sql
ALTER TABLE clientes
ADD COLUMN telefone VARCHAR(20);
```

> Se você não especificar nada, a nova coluna será criada **na última posição** da tabela.

---

2. **Adicionar no início da tabela:**
    

```sql
ALTER TABLE clientes
ADD COLUMN idade INT FIRST;
```

> Aqui, `idade` será a **primeira coluna** da tabela.

---

3. **Adicionar depois de uma coluna existente:**
    

```sql
ALTER TABLE clientes
ADD COLUMN cidade VARCHAR(50) AFTER nome;
```

> A coluna `cidade` será criada **logo depois** da coluna `nome`.

---

### **Observação importante**

- A posição da coluna **não altera o funcionamento da tabela** (os dados continuam acessados pelos nomes das colunas).
    
- É apenas para **organização visual** quando você lista ou descreve a tabela (`DESCRIBE tabela;`).
    
- Se for necessário mudar a posição **de uma coluna já existente**, você pode usar `MODIFY` ou `CHANGE`:
    

```sql
ALTER TABLE clientes
MODIFY COLUMN idade INT AFTER email;
```

> Aqui, a coluna `idade` (já existente) é movida para logo depois de `email`.

---
# [[06 - ALTER TABLE DROP TABLE.pdf#page=7&selection=15,0,16,65|Modificando Definições]]

Para **modificar definições de uma coluna no MySQL**, usamos o comando **`ALTER TABLE`** junto com **`MODIFY`** ou **`CHANGE`**.


## 🔹 1. Usando `MODIFY`

- Serve para **alterar o tipo de dado** ou as restrições da coluna, **mantendo o mesmo nome**.
    

### Sintaxe:

```sql
ALTER TABLE nome_da_tabela
MODIFY COLUMN nome_da_coluna novo_tipo [restrições] [posição];
```

### Exemplo:

```sql
ALTER TABLE clientes
MODIFY COLUMN telefone VARCHAR(30) NOT NULL AFTER nome;
```

> Aqui, a coluna `telefone` passa a aceitar até 30 caracteres, não pode ser nula, e será posicionada depois da coluna `nome`.

---

## 🔹 2. Usando `CHANGE`

- Serve para **alterar tipo, restrições e até renomear a coluna**.
    
- Você deve **repetir o nome antigo e o novo**.
    

### Sintaxe:

```sql
ALTER TABLE nome_da_tabela
CHANGE COLUMN nome_antigo novo_nome tipo [restrições] [posição];
```

### Exemplo:

```sql
ALTER TABLE clientes
CHANGE COLUMN telefone celular VARCHAR(25) UNIQUE;
```

> Aqui, a coluna `telefone` foi renomeada para `celular`, aceita até 25 caracteres e agora deve ser única.

---

## 🔹 3. Diferenças entre `MODIFY` e `CHANGE`

|Comando|Pode alterar tipo|Pode alterar restrições|Pode renomear a coluna|Precisa repetir o nome?|
|---|---|---|---|---|
|`MODIFY`|✅|✅|❌|❌|
|`CHANGE`|✅|✅|✅|✅ (nome antigo e novo)|

---

## 🔹 4. Exemplos práticos extras

1. **Tornar coluna obrigatória (`NOT NULL`):**
    

```sql
ALTER TABLE funcionarios
MODIFY COLUMN salario DECIMAL(10,2) NOT NULL;
```

2. **Alterar tipo de coluna e definir valor padrão:**
    

```sql
ALTER TABLE pedidos
MODIFY COLUMN status VARCHAR(20) DEFAULT 'pendente';
```

3. **Renomear e alterar tipo ao mesmo tempo:**
    

```sql
ALTER TABLE produtos
CHANGE COLUMN preco valor_unitario DECIMAL(8,2) NOT NULL;
```

---

✅ **Resumo:**

- Use `MODIFY` se quiser apenas mudar tipo/restrições/posição.
    
- Use `CHANGE` se quiser também **renomear** a coluna.
    

---

# [[06 - ALTER TABLE DROP TABLE.pdf#page=8&selection=17,0,17,17|Renomeando Coluna]]

Para **renomear uma coluna no MySQL**, você tem **duas formas** possíveis:


## 🔹 1. Usando `CHANGE` (mais antigo, ainda muito usado)

- Permite **renomear e alterar tipo/restrições ao mesmo tempo**.
    
- Necessário informar **nome antigo** e **novo nome**.
    

### Sintaxe:

```sql
ALTER TABLE nome_da_tabela
CHANGE COLUMN nome_antigo novo_nome tipo [restrições];
```

### Exemplo:

```sql
ALTER TABLE clientes
CHANGE COLUMN telefone celular VARCHAR(20);
```

> Aqui a coluna `telefone` foi renomeada para `celular`, mantendo o tipo `VARCHAR(20)`.

⚠️ Atenção: sempre precisa repetir o **tipo e restrições** da coluna, senão pode perder a definição original.

---

## 🔹 2. Usando `RENAME COLUMN` (MySQL 8.0+)

- Sintaxe mais simples.
    
- Só renomeia, sem precisar reescrever o tipo.
    

### Sintaxe:

```sql
ALTER TABLE nome_da_tabela
RENAME COLUMN nome_antigo TO novo_nome;
```

### Exemplo:

```sql
ALTER TABLE clientes
RENAME COLUMN telefone TO celular;
```

> Aqui só troca o nome, mantendo tipo e restrições intactos.

---

## 🔹 Diferença entre os dois

|Método|Versão MySQL|Precisa repetir tipo/restrições?|Pode só renomear?|
|---|---|---|---|
|`CHANGE`|Todas (antigo)|✅ Sim|✅ Sim, mas precisa informar tipo|
|`RENAME COLUMN`|MySQL 8.0+|❌ Não|✅ Sim, direto|

---

✅ **Resumo rápido:**

- Se estiver no **MySQL 8+**, prefira `RENAME COLUMN` → mais limpo e seguro.
    
- Se estiver em versão mais antiga, use `CHANGE COLUMN`.
    

---
# [[06 - ALTER TABLE DROP TABLE.pdf#page=9&selection=13,0,14,65|Renomeando Tabela]]


## 🔹 1. Usando `RENAME TABLE`

- É a forma mais simples e direta.
    
- Permite renomear **uma ou várias tabelas de uma vez**.
    

### Sintaxe:

```sql
RENAME TABLE nome_antigo TO novo_nome;
```

### Exemplo:

```sql
RENAME TABLE clientes TO usuarios;
```

> A tabela `clientes` agora passa a se chamar `usuarios`.

✅ Também dá para renomear várias de uma vez:

```sql
RENAME TABLE pedidos TO vendas, produtos TO itens;
```

---

## 🔹 2. Usando `ALTER TABLE`

- Também funciona para renomear **apenas uma tabela por vez**.
    

### Sintaxe:

```sql
ALTER TABLE nome_antigo RENAME TO novo_nome;
```

### Exemplo:

```sql
ALTER TABLE funcionarios RENAME TO colaboradores;
```

---

## 🔹 3. Cuidados importantes

- Se houver **views, procedures, triggers ou foreign keys** referenciando a tabela antiga, você precisará ajustá-los manualmente (o MySQL **não altera automaticamente** essas dependências).
    
- O novo nome **não pode já existir** no banco de dados.
    
- Evite nomes reservados (como `order`, `user`, etc.) para não dar conflito.
    

---

✅ **Resumo rápido:**

- `RENAME TABLE` → mais usado, permite renomear várias tabelas de uma vez.
    
- `ALTER TABLE ... RENAME TO ...` → alternativa para uma tabela só.
    

---
# [[06 - ALTER TABLE DROP TABLE.pdf#page=10&selection=0,0,0,16|Mais uma Tabela…]]

## 🔹 1. Criando uma tabela simples

```sql
CREATE TABLE clientes (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(100) NOT NULL,
    email VARCHAR(100) UNIQUE,
    data_cadastro DATE DEFAULT (CURRENT_DATE)
);
```

**Explicando:**

- `id INT AUTO_INCREMENT PRIMARY KEY` → cria chave primária numérica, que aumenta automaticamente.
    
- `nome VARCHAR(100) NOT NULL` → campo de texto obrigatório.
    
- `email VARCHAR(100) UNIQUE` → campo único (não pode ter dois iguais).
    
- `data_cadastro DATE DEFAULT (CURRENT_DATE)` → recebe a data do dia, se não for informada.
    

---

## 🔹 2. Criando tabela **somente se não existir**

Às vezes você não tem certeza se a tabela já existe → para evitar erro, use **`IF NOT EXISTS`**:

```sql
CREATE TABLE IF NOT EXISTS clientes (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(100) NOT NULL,
    email VARCHAR(100) UNIQUE
);
```

---

## 🔹 3. Definindo chaves estrangeiras

Se a tabela tiver relação com outra:

```sql
CREATE TABLE pedidos (
    id INT AUTO_INCREMENT PRIMARY KEY,
    cliente_id INT NOT NULL,
    data_pedido DATE NOT NULL,
    FOREIGN KEY (cliente_id) REFERENCES clientes(id)
);
```

> Aqui, `cliente_id` é uma chave estrangeira que aponta para `clientes(id)`.

---

## 🔹 4. Criando várias tabelas ao mesmo tempo

```sql
CREATE TABLE IF NOT EXISTS categorias (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(50) NOT NULL
);

CREATE TABLE IF NOT EXISTS produtos (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(100) NOT NULL,
    preco DECIMAL(10,2) NOT NULL,
    categoria_id INT,
    FOREIGN KEY (categoria_id) REFERENCES categorias(id)
);
```

---

## 🔹 5. Cuidados

- Sempre defina **PRIMARY KEY** (chave primária) para identificação única.
    
- Prefira `AUTO_INCREMENT` em IDs.
    
- Use `IF NOT EXISTS` em scripts que podem rodar várias vezes.
    
- Se for relacionar tabelas, defina **FOREIGN KEY** corretamente.
    

---

✅ **Resumo rápido:**

- `CREATE TABLE` → cria nova tabela.
    
- `IF NOT EXISTS` → evita erro se a tabela já existir.
    
- Use `PRIMARY KEY`, `UNIQUE`, `FOREIGN KEY`, `DEFAULT`, `NOT NULL` para maior controle.
    

---
# [[06 - ALTER TABLE DROP TABLE.pdf#page=11&selection=0,0,0,26|Adicionando Chave Primária]]


## 🔹 1. Criando tabela já com chave primária

Normalmente a **PRIMARY KEY** é definida já no `CREATE TABLE`:

```sql
CREATE TABLE clientes (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(100) NOT NULL,
    email VARCHAR(100)
);
```

> Aqui, `id` é a chave primária.

---

## 🔹 2. Adicionando chave primária em uma tabela já existente

Se a tabela já existe e não tem chave primária:

```sql
ALTER TABLE clientes
ADD PRIMARY KEY (id);
```

> Define a coluna `id` como chave primária.

---

## 🔹 3. Adicionando chave primária composta

Você pode usar **mais de uma coluna** como chave primária (PK composta):

```sql
ALTER TABLE pedidos
ADD PRIMARY KEY (cliente_id, produto_id);
```

> Aqui, a combinação de `cliente_id` + `produto_id` é única.

---

## 🔹 4. Se já existe uma chave primária

- Só pode haver **uma PRIMARY KEY por tabela**.
    
- Para trocar, primeiro é preciso **remover** a antiga:
    

```sql
ALTER TABLE clientes
DROP PRIMARY KEY,
ADD PRIMARY KEY (email);
```

> Remove a PK existente e coloca `email` como nova PK.

---

## 🔹 5. Usando junto com `AUTO_INCREMENT`

A coluna `AUTO_INCREMENT` **precisa ser chave primária ou índice único**:

```sql
ALTER TABLE produtos
MODIFY COLUMN id INT AUTO_INCREMENT,
ADD PRIMARY KEY (id);
```

---

✅ **Resumo rápido:**

- `ADD PRIMARY KEY (coluna)` → adiciona uma PK.
    
- Só pode haver **uma PRIMARY KEY por tabela**.
    
- Pode ser **simples (1 coluna)** ou **composta (2+ colunas)**.
    
- Se já existir uma PK, use `DROP PRIMARY KEY` antes.
    

---
# [[06 - ALTER TABLE DROP TABLE.pdf#page=12&selection=0,0,0,17|Apagando a Tabela]]


## 🔹 1. Apagar uma tabela

```sql
DROP TABLE nome_da_tabela;
```

Exemplo:

```sql
DROP TABLE clientes;
```

> Remove a tabela `clientes` e **todos os dados nela** de forma permanente.

---

## 🔹 2. Apagar somente se existir

Para evitar erro caso a tabela não exista:

```sql
DROP TABLE IF EXISTS clientes;
```

---

## 🔹 3. Apagar várias tabelas ao mesmo tempo

```sql
DROP TABLE IF EXISTS pedidos, produtos, categorias;
```

---

## 🔹 4. Diferença entre `DROP`, `TRUNCATE` e `DELETE`

|Comando|O que faz|Estrutura da tabela continua?|Restaura AUTO_INCREMENT?|
|---|---|---|---|
|`DROP TABLE`|Apaga a tabela inteira (estrutura + dados)|❌ Não|❌ Não (tabela some)|
|`TRUNCATE TABLE`|Apaga **todos os dados**, mas mantém a tabela|✅ Sim|✅ Sim (zera o AUTO_INCREMENT)|
|`DELETE FROM tabela`|Apaga **linhas específicas**|✅ Sim|❌ Não (não reseta AUTO_INCREMENT)|

---

## 🔹 5. Cuidados

- **Irreversível** → depois de um `DROP`, só restaura se tiver **backup**.
    
- Se houver **FOREIGN KEYS** apontando para a tabela, você pode precisar apagar ou desativar essas restrições antes (`SET FOREIGN_KEY_CHECKS = 0;`).
    
- Em ambientes de produção, prefira **`TRUNCATE`** ou **`DELETE`** em vez de `DROP`, para não perder a estrutura.
    

---

✅ **Resumo rápido:**

- `DROP TABLE nome;` → apaga tabela.
    
- `DROP TABLE IF EXISTS nome;` → só apaga se existir.
    
- `DROP TABLE t1, t2;` → apaga várias tabelas.
    
- Use com cuidado, pois é destrutivo e permanente.
    


