
---
### [[05 - INSERT INTO.pdf#page=6&selection=38,0,41,1|05 - INSERT INTO, p.6]]

Uma das operações mais importantes em um banco de dados é a inserção de registros (dados). Fazemos isso com o uso do comando **INSERT INTO**.

### Sintaxe padrão:

```
INSERT INTO nome_tabela (coluna1, coluna2,...)
VALUES (valor1, valor2,...);
```

De acordo com a sintaxe apresentada, devemos especificar a tabela e quais colunas dessa tabela receberão os dados, e em seguida, logo após a palavra-chave **VALUES**, especificamos os dados em si – na mesma ordem em que as colunas foram especificadas.

Caso haja uma coluna com auto incremento, ela não deve ser incluída na lista de colunas do comando, pois seus dados serão gerados e inseridos automaticamente pelo MySQL quando um novo registro for adicionado.

---
# Comandos em SQL

Pense assim, a linguagem SQL é uma só, porém ela é dividida em tipos de acordo com a funcionalidade dos comandos.  
Os tipos da linguagem SQL são:

- **DDL** - Data Definition Language - Linguagem de Definição de Dados.  
    São os comandos que interagem com os objetos do banco.
    
    - São comandos DDL : CREATE, ALTER e DROP
- **DML** - Data Manipulation Language - Linguagem de Manipulação de Dados.  
    São os comandos que interagem com os dados dentro das tabelas.
    
    - São comandos DML : INSERT, DELETE e UPDATE
- **DQL** - Data Query Language - Linguagem de Consulta de dados.  
    São os comandos de consulta.
    
    - São comandos DQL : SELECT (é o comando de consulta)  
        Aqui cabe um parenteses. Em alguns livros o SELECT fica na DML em outros tem esse grupo próprio.
- **DTL** - Data Transaction Language - Linguagem de Transação de Dados.  
    São os comandos para controle de transação.
    
    - São comandos DTL : BEGIN TRANSACTION, COMMIT E ROLLBACK
- **DCL** - Data Control Language - Linguagem de Controle de Dados.  
    São os comandos para controlar a parte de segurança do banco de dados.
    
    - São comandos DCL : GRANT, REVOKE E DENY.

# Uma forma mais simples pra ser lembrado

O que diferencia as siglas é a letra do meio.

Como, por exemplo:

- **DML** = "**M**" do meio vem de **Manipulação**.
- **DDL** = "**D**" do meio vem de **Definição**.
- **DCL** = "**C**" do meio vem de **Controle**.
- **DTL** = "**T**" do meio vem de **Transação**.
- **DQL** = "**Q**" do meio vem de **"Qonsulta"**.