
---
## **1. Introdução**

- Objetivo: Aprender a alterar a estrutura de tabelas existentes e a apagar tabelas no MySQL.
    
- Recapitulando: Já criamos banco de dados, tabelas, inserimos dados. Agora vamos modificar estruturas sem perder dados.
    

---

## **2. Comando ALTER TABLE**

- **Função:** Alterar a estrutura de uma tabela.
    
- **Sintaxe básica:**
    

```sql
ALTER TABLE nome_tabela <ação>;
```

### **2.1 Adicionar uma coluna**

- Exemplo:
    

```sql
ALTER TABLE pessoas ADD COLUMN profissao VARCHAR(10);
```

- Observações:
    
    - `ADD COLUMN` adiciona uma coluna no final da tabela por padrão.
        
    - Não usar acentos nos nomes de colunas.
        
    - `describe pessoas;` ou `desc pessoas;` mostra a estrutura da tabela.
        

### **2.2 Remover uma coluna**

- Exemplo:
    

```sql
ALTER TABLE pessoas DROP COLUMN profissao;
```

- Observação: Remove a coluna permanentemente.
    

### **2.3 Adicionar coluna em posição específica**

- Depois de uma coluna existente:
    

```sql
ALTER TABLE pessoas ADD COLUMN profissao VARCHAR(10) AFTER nome;
```

- Como primeira coluna:
    

```sql
ALTER TABLE pessoas ADD COLUMN codigo INT FIRST;
```

- **Regras de posicionamento:**
    
    - `AFTER coluna_existente` → após a coluna indicada.
        
    - `FIRST` → primeira coluna.
        
    - Sem parâmetro → adiciona no final.
        

### **2.4 Modificar tipo e constraints**

- Alterar tipo de dado e restrições:
    

```sql
ALTER TABLE pessoas MODIFY COLUMN profissao VARCHAR(20) NOT NULL DEFAULT '';
```

- `MODIFY` altera tipo e constraints, mas não permite renomear coluna.
    

### **2.5 Renomear coluna**

- Sintaxe:
    

```sql
ALTER TABLE pessoas CHANGE COLUMN profissao prof VARCHAR(20);
```

- Observações:
    
    - `CHANGE` exige nome antigo e novo.
        
    - Todas as constraints precisam ser redefinidas se quiser mantê-las.
        

### **2.6 Renomear tabela**

```sql
ALTER TABLE pessoas RENAME TO gafanhotos;
```

---

## **3. Comando DROP TABLE**

- **Função:** Apagar tabelas inteiras.
    
- Sintaxe:
    

```sql
DROP TABLE nome_tabela;
DROP TABLE IF EXISTS nome_tabela; -- só apaga se existir
```

- Observação: Ao apagar uma tabela, todos os dados contidos nela também são apagados.
    
- **Diferença de DROP em ALTER TABLE:**
    
    - `ALTER TABLE DROP COLUMN` → apaga coluna.
        
    - `DROP TABLE` → apaga tabela inteira.
        

---

## **4. Criando tabela com CREATE TABLE**

- Estrutura exemplo (`cursos`):
    

```sql
CREATE TABLE IF NOT EXISTS cursos (
  idcurso INT FIRST,
  nome VARCHAR(30) NOT NULL UNIQUE,
  descricao TEXT,
  carga INT UNSIGNED,
  totaulas INT UNSIGNED,
  ano YEAR DEFAULT '2016'
) DEFAULT CHARSET=utf8;
```

- Observações:
    
    - `IF NOT EXISTS` evita erro caso a tabela já exista.
        
    - `NOT NULL` → campo obrigatório.
        
    - `UNIQUE` → valores únicos.
        
    - `UNSIGNED` → número não pode ser negativo.
        
    - `DEFAULT` → valor padrão.
        

---

## **5. Adicionando chave primária**

- Primeiro, criar coluna de identificação:
    

```sql
ALTER TABLE cursos ADD COLUMN idcurso INT FIRST;
```

- Em seguida, definir como chave primária:
    

```sql
ALTER TABLE cursos ADD PRIMARY KEY (idcurso);
```

---

## **6. Inserindo e visualizando dados**

- Inserir registros:
    

```sql
INSERT INTO teste VALUES (1, 'Pedro', 22), (2, 'Maria', 77);
```

- Visualizar registros:
    

```sql
SELECT * FROM teste;
```

- Sem chave primária, valores de `id` podem se repetir.
    

---

## **7. Classificação dos comandos**

- **DDL (Data Definition Language)** – Definição da estrutura:
    
    - `CREATE TABLE`, `ALTER TABLE`, `DROP TABLE`
        
- **DML (Data Manipulation Language)** – Manipulação de dados:
    
    - `INSERT`, `UPDATE`, `DELETE`
        
- Observação: Mesmo que `DROP TABLE` apague dados, ele é DDL, pois altera a **estrutura**, não apenas os dados.
    

---

## **8. Boas práticas**

- Sempre manter **backup** do banco de dados antes de usar DROP ou ALTER.
    
- Evitar alterar banco de dados em produção sem teste.
    
- Teste os comandos em ambiente local.
    

---

### **Resumo visual rápido**

|Comando SQL|Ação|
|---|---|
|`ALTER TABLE ... ADD COLUMN`|Adiciona coluna|
|`ALTER TABLE ... DROP COLUMN`|Remove coluna|
|`ALTER TABLE ... MODIFY COLUMN`|Modifica tipo/constraint|
|`ALTER TABLE ... CHANGE COLUMN`|Renomeia coluna e modifica tipo/constraint|
|`ALTER TABLE ... RENAME TO`|Renomeia tabela|
|`DROP TABLE`|Remove tabela inteira|
|`CREATE TABLE IF NOT EXISTS`|Cria tabela se não existir|

---

**Conclusão:**  
O `ALTER TABLE` é extremamente versátil para modificar a estrutura da tabela sem perder dados. `DROP TABLE` apaga toda a tabela e seus dados. Ambos são comandos **DDL**, fundamentais para administração de bancos de dados.
