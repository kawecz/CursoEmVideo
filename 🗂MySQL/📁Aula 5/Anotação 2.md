
---
### **1. Revisão do Banco de Dados**

- Banco criado: `cadastro`.
    
- Tabela criada: `pessoas`.
    
- Campos da tabela:
    
    - `id` (chave primária, `AUTO_INCREMENT`, `NOT NULL`)
        
    - `nome` (`VARCHAR(30)`, `NOT NULL`)
        
    - `nascimento` (`DATE`)
        
    - `sexo` (`ENUM('M','F')`)
        
    - `peso` (`DECIMAL(5,2)`)
        
    - `altura` (`DECIMAL(3,2)`)
        
    - `nacionalidade` (`VARCHAR(20)`, `DEFAULT 'Brasil'`)
        

---

### **2. Inserção de Dados (INSERT INTO)**

- **Comando básico**:
    

```sql
INSERT INTO pessoas (id, nome, nascimento, sexo, peso, altura, nacionalidade)
VALUES ('1', 'Godofredo', '1984-01-02', 'Masculino', '78.5', '1.83', 'Brasil');
```

- Observações importantes:
    
    - Datas no MySQL seguem o formato `YYYY-MM-DD`.
        
    - Dados entre aspas simples `' '` são tratados como **valores**, não tipos.
        
    - Campos `AUTO_INCREMENT` não precisam ser informados; o MySQL preenche automaticamente.
        
    - Campos com `DEFAULT` também podem ser omitidos.
        

---

### **3. Simplificando o INSERT**

- Se a **ordem dos campos no comando** for igual à ordem da tabela, você pode omitir a lista de campos:
    

```sql
INSERT INTO pessoas VALUES (DEFAULT, 'Adalgiza', '1930-11-02', 'Feminino', 63.2, 1.75, 'Irlanda');
```

- `DEFAULT` no lugar de `id` permite que o MySQL atribua o próximo valor da sequência.
    

---

### **4. Inserindo Vários Registros de Uma Vez**

- É possível inserir múltiplos registros com **um único comando**:
    

```sql
INSERT INTO pessoas (nome, nascimento, sexo, peso, altura, nacionalidade)
VALUES 
('Ana', '1975-12-22', 'Feminino', 52.3, 1.45, 'EUA'),
('Cláudio', '1975-04-22', 'Masculino', 99.0, 2.15, 'Brasil'),
('Pedro', '1999-12-03', 'Masculino', 87.0, 2.0, 'Brasil');
```

- Cada registro está entre parênteses e separado por vírgulas.
    
- O ponto-e-vírgula `;` finaliza o comando.
    

---

### **5. Comandos SQL e Classificação**

- **DDL (Data Definition Language)**: comandos de definição de estrutura (ex: `CREATE DATABASE`, `CREATE TABLE`).
    
- **DML (Data Manipulation Language)**: comandos de manipulação de dados (ex: `INSERT INTO`, `UPDATE`, `DELETE`).
    
- Gustavo enfatiza que **INSERT INTO** é DML, pois manipula dados, não estrutura.
    

---

### **6. Boas práticas**

- Sempre testar o comando com `SELECT * FROM pessoas;` para conferir se os dados foram inseridos corretamente.
    
- Use `DEFAULT` para campos `AUTO_INCREMENT` ou com valor padrão definido.
    
- Mantenha consistência na ordem dos campos para simplificar os comandos.
    
