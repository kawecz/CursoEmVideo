
---

## 1. Objetivo da Aula

- Refazer o banco de dados criado na aula anterior, mas de forma **mais eficiente e otimizada**.
    
- Resolver problemas de:
    
    - **Duplicação de registros** (exemplo: vários "Sr. Vladimir").
        
    - **Uso de tipos primitivos inadequados**.
        
    - **Configuração correta de caracteres** (acentuação).
        
- Introdução ao conceito de **Chaves Primárias (Primary Keys)** e **Constraints**.
    

---

## 2. Comandos principais vistos

### Criar e apagar banco de dados

```sql
CREATE DATABASE cadastro;
DROP DATABASE cadastro;
```

### Criando banco com parâmetros

```sql
CREATE DATABASE cadastro
DEFAULT CHARACTER SET utf8
DEFAULT COLLATE utf8_general_ci;
```

⚡ Aqui usamos **constraints**:

- `DEFAULT CHARACTER SET` → define codificação de caracteres.
    
- `DEFAULT COLLATE` → define regras de ordenação e comparação (collation).
    

---

## 3. Melhorando a tabela "pessoas"

### Estrutura da versão inicial

```sql
CREATE TABLE pessoas (
   nome VARCHAR(30),
   idade TINYINT,
   sexo CHAR(1),
   peso FLOAT,
   altura FLOAT,
   nacionalidade VARCHAR(20)
);
```

### Problemas:

- `idade` muda com o tempo → melhor usar `nascimento DATE`.
    
- `sexo` como `CHAR(1)` permite qualquer letra → usar `ENUM('M','F')`.
    
- `peso` e `altura` como `FLOAT` não controlam precisão → usar `DECIMAL`.
    
- `nacionalidade` pode ter valor padrão → usar `DEFAULT 'Brasil'`.
    

---

## 4. Nova versão da tabela

```sql
CREATE TABLE pessoas (
   id INT NOT NULL AUTO_INCREMENT,
   nome VARCHAR(30) NOT NULL,
   nascimento DATE,
   sexo ENUM('M','F'),
   peso DECIMAL(5,2),
   altura DECIMAL(3,2),
   nacionalidade VARCHAR(20) DEFAULT 'Brasil',
   PRIMARY KEY (id)
) DEFAULT CHARSET = utf8;
```

### Novidades técnicas:

- **`id`**: campo exclusivo, inteiro, `AUTO_INCREMENT` + `PRIMARY KEY`.
    
- **`NOT NULL`**: garante que certos campos não podem ficar vazios.
    
- **`DEFAULT`**: define valor padrão.
    
- **`ENUM`**: limita as opções possíveis.
    
- **`DECIMAL(p,s)`**: controla precisão → `5,2` = 3 dígitos antes da vírgula + 2 depois.
    

---

## 5. Conceitos importantes de Banco de Dados

- **Primary Key (Chave Primária)** → identifica de forma única cada registro (não se repete, não pode ser nulo).
    
- **Constraints** → regras aplicadas a campos ou tabelas.
    
    - `NOT NULL`
        
    - `DEFAULT`
        
    - `AUTO_INCREMENT`
        
    - `PRIMARY KEY`
        
- **Collation** → define como o banco trata acentuação, ordenação e comparação de textos.
    
- **Tipos Primitivos**: escolha correta economiza espaço e melhora desempenho.
    

---

## 6. Vocabulário Técnico (Nouns, Verbs, Adjectives)

### Nouns (substantivos – conceitos de BD)

- database, table, record, field, schema, query, character set, collation, constraint, primary key, identifier.
    

### Verbs (ações – ligados a SQL e TI)

- create, drop, delete, define, optimize, improve, configure, store, update, execute.
    

### Adjectives (adjetivos técnicos)

- relational, unique, default, primary, null, optimized, fixed, variable, incremental.
    

---

## 7. Gramática aplicada (SQL + inglês)

- **Verbos viram comandos**:
    
    - `CREATE`, `DROP`, `USE`, `ALTER` → imperativos, usados em maiúsculas.
        
- **Substantivos** = objetos que você cria: `DATABASE`, `TABLE`, `FIELD`.
    
- **Adjetivos** aparecem como constraints ou propriedades: `NOT NULL`, `DEFAULT`, `PRIMARY`.
    

---

# 🎯 Resumo final da Aula 4

- Você aprendeu a **apagar e recriar bancos de dados** (`DROP` + `CREATE`).
    
- Agora o banco e a tabela já têm **configuração de UTF-8**, evitando problemas de acentuação.
    
- A tabela "pessoas" foi **refatorada** para ser mais inteligente:
    
    - Substituição de idade → data de nascimento.
        
    - Controle de sexo com `ENUM`.
        
    - Precisão numérica com `DECIMAL`.
        
    - Valor padrão em nacionalidade.
        
    - Identificação única com `id` como chave primária.
        
