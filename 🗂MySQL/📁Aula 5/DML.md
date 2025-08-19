
---
Esses comandos permitem que você acesse e altere os dados que estão em um banco de dados.

|             |                                                                                                          |
| ----------- | -------------------------------------------------------------------------------------------------------- |
| **Comando** | **Descrição**                                                                                            |
| `SELECT`    | `SELECT` é um comando de acesso. Ele permite que você acesse dados em um banco de dados.                 |
| `INSERT`    | `INSERT` é um comando de alteração. Ele permite que você insira linhas de dados em uma tabela existente. |
| `DELETE`    | `DELETE` é um comando de alteração. Ele permite que você remova linhas de dados em uma tabela existente. |
| `UPDATE`    | `UPDATE` é um comando de alteração. Ele permite que você altere os dados nas linhas de uma tabela.       |

---

### **1. SELECT**

- **O que faz:** Busca (consulta) dados dentro de uma tabela.
    
- **Syntax:**
    

```sql
SELECT colunas
FROM nome_tabela
[WHERE condição]
[ORDER BY coluna]
[LIMIT número];
```

- **Exemplo:**
    

```sql
-- Buscar todas as colunas
SELECT * FROM clientes;

-- Buscar apenas nome e email
SELECT nome, email FROM clientes;

-- Buscar clientes maiores de 18 anos
SELECT * FROM clientes WHERE idade >= 18;

-- Buscar os 5 primeiros registros ordenados por idade
SELECT * FROM clientes ORDER BY idade DESC LIMIT 5;
```

➡️ `SELECT` é o **mais usado**, pois permite consultar dados de várias formas.

---

### **2. INSERT**

- **O que faz:** Insere novos registros (linhas) em uma tabela.
    
- **Syntax:**
    

```sql
INSERT INTO nome_tabela (coluna1, coluna2, ...)
VALUES (valor1, valor2, ...);
```

- **Exemplo:**
    

```sql
-- Inserindo um único cliente
INSERT INTO clientes (nome, email, idade) 
VALUES ('Ana Silva', 'ana@email.com', 25);

-- Inserindo múltiplos registros de uma vez
INSERT INTO clientes (nome, email, idade) 
VALUES 
('Carlos Souza', 'carlos@email.com', 30),
('Maria Lima', 'maria@email.com', 22);
```

➡️ Sempre informe as colunas, a não ser que insira em **todas** elas na ordem da tabela.

---

### **3. DELETE**

- **O que faz:** Remove linhas de uma tabela.
    
- **Syntax:**
    

```sql
DELETE FROM nome_tabela
[WHERE condição];
```

- **Exemplo:**
    

```sql
-- Excluir um cliente específico
DELETE FROM clientes WHERE id = 3;

-- Excluir todos os clientes com idade menor que 18
DELETE FROM clientes WHERE idade < 18;

-- ⚠️ Excluir todos os registros da tabela
DELETE FROM clientes;
```

➡️ Muito cuidado ⚠️: se você esquecer o `WHERE`, **vai apagar todos os dados da tabela**.

---

### **4. UPDATE**

- **O que faz:** Atualiza dados já existentes na tabela.
    
- **Syntax:**
    

```sql
UPDATE nome_tabela
SET coluna1 = valor1, coluna2 = valor2
[WHERE condição];
```

- **Exemplo:**
    

```sql
-- Atualizar o email de um cliente específico
UPDATE clientes 
SET email = 'novoemail@email.com'
WHERE id = 2;

-- Aumentar a idade de todos os clientes em +1
UPDATE clientes
SET idade = idade + 1;

-- Atualizar nome e idade de um cliente
UPDATE clientes
SET nome = 'João Silva', idade = 28
WHERE id = 5;
```

➡️ Assim como no `DELETE`, se você esquecer o `WHERE`, **todos os registros serão alterados**.

---

✅ **Resumo em tabela rápida:**

|Comando|O que faz|Exemplo|
|---|---|---|
|`SELECT`|Consulta dados|`SELECT nome, email FROM clientes;`|
|`INSERT`|Insere registros|`INSERT INTO clientes (nome, idade) VALUES ('Ana', 25);`|
|`DELETE`|Remove registros|`DELETE FROM clientes WHERE id=3;`|
|`UPDATE`|Atualiza registros|`UPDATE clientes SET idade=30 WHERE id=2;`|
