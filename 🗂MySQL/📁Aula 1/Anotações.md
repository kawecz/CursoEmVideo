
---

## 1. Contexto histórico

- Antes dos computadores → dados eram guardados em **papel** (fichas → pastas → arquivos metálicos).
    
- Década de 40 → computadores militares/universitários (1945–46).
    
- Década de 50 → necessidade de digitalizar dados.
    

### Analogia de TI:

- **Fichas** → **Registros**
    
- **Pastas** → **Tabelas**
    
- **Armários** → **Arquivos**
    

⚡ Isso será útil para entender como bancos de dados armazenam informações.

---

## 2. Primeiras formas de armazenamento digital

- **Arquivos Sequenciais**: dados em fita/cartão → para acessar o 5º registro, precisava ler 1º até 4º.  
    ➝ Vantagem: melhor que papel.  
    ➝ Desvantagem: muito lento.
    
- **Arquivos de Acesso Direto**: surgem com disquetes e HDs.  
    ➝ Permitia acessar diretamente o registro pelo **índice**.  
    ➝ Muito mais rápido.
    

---

## 3. Década de 60: Avanços importantes

- O **Departamento de Defesa dos EUA** cria o **CODASYL** (encontro de militares, empresas e universidades).
    
- Surgem:
    
    - **COBOL** → linguagem de programação voltada para negócios e dados (ainda usada em sistemas legados).
        
    - Conceito de **Banco de Dados**, definido em 4 partes:
        
        1. **Base de Dados** (os dados em si)
            
        2. **Sistema Gerenciador de Banco de Dados (SGBD/DBMS)**
            
        3. **Linguagem de Exploração** (para acessar dados – depois virou SQL)
            
        4. **Programas adicionais** (controle de usuários, automações etc.)
            

---

## 4. IBM e os Modelos de Dados

- IBM propôs modelos iniciais:
    
    - **Modelo Hierárquico** → dados em árvore.
        
    - **Modelo em Rede** → dados interligados em rede.
        
- Problema: pouco práticos para **relacionar dados**.
    

---

## 5. Modelo Relacional

- Criado por **Edgar Codd (IBM, anos 70)**.
    
- Ideia: dados organizados em **tabelas** que podem se **relacionar**.
    
- Permite consultas mais complexas → Ex: cliente → compras → estoque → fornecedor.
    
- Ainda hoje é a base do **MySQL** e da maioria dos SGBDs.
    

---

## 6. Linguagem SQL

- Primeiro nome: **SEQUEL (Structured Query English Language)**.
    
- Evoluiu para: **SQL (Structured Query Language)**.
    
- Função: consultar e manipular dados.
    
- Problema: cada fabricante criou sua própria versão → ANSI e ISO padronizaram → **ANSI-SQL**.
    

---

## 7. Principais Bancos de Dados

- **Pagos**: Oracle, IBM DB2, Microsoft SQL Server, dBase (antigo).
    
- **Gratuitos**: MySQL, MariaDB, Firebird, PostgreSQL.
    
- Curso foca no **MySQL** (popular, gratuito, mantido pela Oracle).
    

---

# 🛠️ Notas de Estudo para TI

### Conceitos-chave:

- **Registro** = uma linha de informação (ex: dados de um cliente).
    
- **Tabela** = conjunto de registros.
    
- **Arquivo** = conjunto de tabelas.
    
- **SGBD** = software que gerencia banco de dados (ex: MySQL).
    
- **SQL** = linguagem padrão para interagir com bancos de dados.
    

### Linha do tempo resumida:

1. Papel (fichas/pastas)
    
2. Arquivos sequenciais (fita/cartões)
    
3. Arquivos de acesso direto (discos)
    
4. Modelos hierárquico e em rede (IBM)
    
5. Modelo relacional (Edgar Codd, base do MySQL)
    
6. Linguagem SQL → padronização ANSI-SQL
    
