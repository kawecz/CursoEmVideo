
----
# [[03 - Criando Banco de Dados MySQL.pdf#page=11&selection=0,0,2,8|CREATE DATABASE]]

Use o comando `CREATE DATABASE` para criar um banco de dados.

## Sintaxe[](https://www.ibm.com/docs/pt-br/netcoolomnibus/8.1.0?topic=reference-create-database-command#omn_adm_sql_creatingdatabase__title__2 "Copy to clipboard")

```plaintext-ibm
CREATE DATABASE database_name;
```

O nome do banco de dados deve ser exclusivo no ObjectServer e estar em conformidade com as convenções de nomenclatura do ObjectServer.

Um banco de dados é sempre persistente.

## Exemplo[](https://www.ibm.com/docs/pt-br/netcoolomnibus/8.1.0?topic=reference-create-database-command#omn_adm_sql_creatingdatabase__title__3 "Copy to clipboard")

```plaintext-ibm
create database mydb;
```

---
# [[03 - Criando Banco de Dados MySQL.pdf#page=13&selection=0,0,2,5|CREATE TABLE]]

Use o comando `CREATE TABLE` para criar uma tabela.

## Sintaxe[](https://www.ibm.com/docs/pt-br/netcoolomnibus/8.1.0?topic=reference-create-table-command#omn_adm_sql_creatingtable__title__2 "Copy to clipboard")

```plaintext-ibm
CREATE TABLE [database_name.]table_name
PERSISTENT | VIRTUAL
(column_name data_type [ PRIMARY KEY | NODEFAULT | NOMODIFY | HIDDEN],...
[, PRIMARY KEY(column_name,...) ] );
```

O nome da tabela deve ser exclusivo no banco de dados e estar em conformidade com as convenções de nomenclatura do ObjectServer.

O tipo de armazenamento é `PERSISTENT` ou `VIRTUAL`. Uma tabela persistente é recriada, preenchida com todos os seus dados, quando o ObjectServer for reiniciado. Já a tabela virtual é recriada com a mesma descrição da tabela, mas sem nenhum dado, quando o ObjectServer for reiniciado.

Ao definir as colunas, você deverá especificar o nome da coluna e o tipo de dados e também é possível especificar propriedades opcionais.

O número máximo de colunas em uma tabela é 512, exceto as colunas mantidas pelo sistema. O tamanho máximo da linha para uma tabela, que é a soma do comprimento das colunas na linha, é 64 KB.

## Exemplo[](https://www.ibm.com/docs/pt-br/netcoolomnibus/8.1.0?topic=reference-create-table-command#omn_adm_sql_creatingtable__title__3 "Copy to clipboard")

```plaintext-ibm
create table mydb.mytab persistent
(col1 integer primary key, col2 varchar(20));
```

