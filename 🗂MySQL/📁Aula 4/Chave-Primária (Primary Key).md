
---
A chave primária, ou primary key, é o conceito mais básico relacionado à organização em um banco de dados. Toda tabela possuirá uma, e somente uma, chave primária. Essa chave é utilizada como **identificador único** da tabela, sendo representada por aquele campo (ou campos) que não receberá valores repetidos.

Por causa disso, existe uma lista de características que deve ser levada em consideração ao definir uma chave primária:

1. Chaves primárias **não** podem ser nulas;
2. Cada registro na tabela deve possuir uma, e somente uma, chave primária;
3. Normalmente, chaves primárias são incrementadas automaticamente pelo banco de dados, ou seja, não há necessidade de passarmos esse valor em um [INSERT](https://www.devmedia.com.br/comandos-basicos-em-sql-insert-update-delete-e-select/37170 "Comandos básicos em SQL"). Entretanto, essa é uma opção configurada na criação da base de dados que não é obrigatória. Nos casos em que ela (incremento automático) não é definida, é preciso garantir que não haverá valores repetidos nessa coluna;
4. São as chaves para o relacionamento entre entidades ou tabelas da base de dados. Assim haverá na tabela relacionada uma **referência** a essa chave primária (que será, na tabela relacionada, a chave estrangeira).

Para criarmos uma chave primária precisamos de um código como o mostrado na **Listagem 1**.

```
CREATE TABLE Pessoa
(
    ID_Pessoa integer PRIMARY KEY AUTOINCREMENT,
    Nome varchar(255),
    Endereco varchar(255),
    Cidade varchar(255)
);
```

**Listagem 1**. Gerando tabela Pessoa com chave primária com auto incremento

- **Linha 01**: comando SQL para criação da tabela Pessoa na base de dados. Quando executado, criará a tabela com os campos definidos nas **linhas 03** a **06**;
- **Linha 03**: campo ID_Pessoa da tabela. Gera um campo de valores inteiros (integer), com uma constraint PRIMARY KEY que indica que esse campo é a chave primária da tabela. Note ainda que o definimos como sendo de autoincremento (AUTOINCREMENT);
- **Linhas 04 a 06**: definição dos demais campos da tabela Pessoa.

De forma simples, Constraints dentro do SQL são regras/restrições definidas para uma coluna de uma tabela do banco de dados. Podemos dizer, também, que representam propriedades que os dados de certa coluna precisam obedecer. Chaves primárias e chaves estrangeiras são exemplos de constraints.

Vale ressaltar que a chave primária é essencial para o funcionamento da base de dados, representando um registro único que facilita buscas e garante que cada valor dentro da tabela será diferente do outro.