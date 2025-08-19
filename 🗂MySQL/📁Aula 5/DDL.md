
---
Os comandos DDL consistem em diferentes comandos com diferentes funcionalidades, que discutirei na seguinte ordem:

|                 |                                                                                         |                                 |
| --------------- | --------------------------------------------------------------------------------------- | ------------------------------- |
| **Comando DDL** | **DESCRIÇÃO**                                                                           | **SYNTAX**                      |
| `CREATE`        | Crie uma tabela e suas colunas junto com seu tipo de dados.                             | `CREATE TABLE`                  |
| `ALTER`         | Modifique os nomes das colunas e adicione ou exclua uma coluna.                         | `ALTER TABLE`                   |
| `RENAME`        | Altere o nome da tabela.                                                                | `RENAME TABLE`                  |
| `COMMENT`       | Adicione uma explicação ao código SQL para que outros membros da equipe possam revisar. | `--`<br><br>`/* …`<br><br>`…*/` |
| `TRUNCATE`      | Remover dados de uma tabela sem excluir a tabela.                                       | `TRUNCATE TABLE`                |
| `DROP`          | Exclua a tabela com seus dados.                                                         | `DROP TABLE`                    |

---

### **1. CREATE**

- **O que faz:** Cria uma nova tabela no banco de dados, definindo as colunas e seus tipos de dados.
    
- **Syntax:**
    

```sql
CREATE TABLE nome_tabela (
    coluna1 tipo_dado [restrições],
    coluna2 tipo_dado [restrições],
    ...
);
```

- **Exemplo:**
    

```sql
CREATE TABLE usuarios (
    id INT PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(100) NOT NULL,
    email VARCHAR(100) UNIQUE,
    idade INT
);
```

➡️ Aqui criamos a tabela `usuarios` com colunas `id`, `nome`, `email` e `idade`.

---

### **2. ALTER**

- **O que faz:** Modifica uma tabela já existente (adicionar, excluir ou renomear colunas).
    
- **Syntax:**
    

```sql
ALTER TABLE nome_tabela
ADD nome_coluna tipo_dado;

ALTER TABLE nome_tabela
DROP COLUMN nome_coluna;

ALTER TABLE nome_tabela
CHANGE nome_coluna antigo_nome novo_nome tipo_dado;

ALTER TABLE nome_tabela
MODIFY nome_coluna novo_tipo;
```

- **Exemplo:**
    

```sql
ALTER TABLE usuarios ADD telefone VARCHAR(20);
ALTER TABLE usuarios DROP COLUMN idade;
ALTER TABLE usuarios CHANGE nome nome_completo VARCHAR(150);
ALTER TABLE usuarios MODIFY email VARCHAR(200);
```

➡️ Assim você pode **evoluir sua tabela sem recriá-la**.

---

### **3. RENAME**

- **O que faz:** Muda o nome de uma tabela.
    
- **Syntax:**
    

```sql
RENAME TABLE nome_atual TO novo_nome;
```

- **Exemplo:**
    

```sql
RENAME TABLE usuarios TO clientes;
```

➡️ Agora a tabela `usuarios` passa a se chamar `clientes`.

---

### **4. COMMENT**

- **O que faz:** Insere comentários no código SQL, ajudando na organização e explicação.
    
- **Syntax:**
    

```sql
-- Comentário de uma linha

/* Comentário
   em múltiplas linhas */
```

- **Exemplo:**
    

```sql
-- Criação da tabela de clientes
CREATE TABLE clientes (
    id INT PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(100) NOT NULL
);

/* Comentário longo:
   Essa tabela armazena informações dos clientes
   que realizam compras no sistema */
```

➡️ Comentários não afetam a execução do SQL.

---

### **5. TRUNCATE**

- **O que faz:** Apaga todos os dados de uma tabela, mas mantém sua estrutura.
    
- **Syntax:**
    

```sql
TRUNCATE TABLE nome_tabela;
```

- **Exemplo:**
    

```sql
TRUNCATE TABLE clientes;
```

➡️ A tabela `clientes` ficará **vazia**, mas ainda existirá com suas colunas.

---

### **6. DROP**

- **O que faz:** Exclui a tabela inteira, junto com seus dados e estrutura.
    
- **Syntax:**
    

```sql
DROP TABLE nome_tabela;
```

- **Exemplo:**
    

```sql
DROP TABLE clientes;
```

➡️ Aqui a tabela `clientes` deixa de existir completamente.

---

✅ **Resumo rápido em tabela:**

|Comando|O que faz|Exemplo|
|---|---|---|
|`CREATE`|Cria tabela|`CREATE TABLE usuarios (...);`|
|`ALTER`|Modifica tabela|`ALTER TABLE usuarios ADD telefone VARCHAR(20);`|
|`RENAME`|Renomeia tabela|`RENAME TABLE usuarios TO clientes;`|
|`COMMENT`|Adiciona comentário|`-- comentário`|
|`TRUNCATE`|Apaga dados mas mantém tabela|`TRUNCATE TABLE clientes;`|
|`DROP`|Apaga tabela por completo|`DROP TABLE clientes;`|


