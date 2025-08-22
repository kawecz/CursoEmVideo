
---
<iframe title="Curso MySQL #05 - Inserindo Dados na Tabela (INSERT INTO)" src="https://www.youtube.com/embed/NCG9niOlm40?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>

---

## **Apresentação da Aula**

- [01:00–01:27] Aula 5 do curso de Banco de Dados. Continuidade do tema da aula anterior: **Inserção de Dados na Tabela**.
    
- Revisão: já foram criados o **Banco de Dados** (`create database`) e a **tabela** (`create table`). Agora será abordada a inserção de dados dentro dessa tabela.
    

---

## **Preparação e Motivação**

- [01:27–02:11] O professor reforça a importância de praticar durante o estudo, afirmando que sem prática não é possível aprender banco de dados nem tecnologia em geral.
    
- Incentivo: pausa nos vídeos apenas para preparar o ambiente e praticar os exercícios.
    

---

## **Exemplo Prático – Godofredo**

- [02:11–03:12] Revisão dos dados da primeira tabela (`pessoa`) usando o exemplo do personagem **Godofredo**:
    
    - Campos: `nome`, `data de nascimento`, `sexo`, `peso`, `altura`, `nacionalidade`.
        
    - Alteração: não se cadastra idade; registra-se **data de nascimento**.
        
    - Godofredo nasceu em **02/01/1984**, pesa 78,5 kg, mede 1,83 m, brasileiro.
        

---

## **Estrutura da Tabela**

- [03:12–04:42] Revisão detalhada da criação da tabela `pessoa`:
    
    - `ID`: chave primária (`PRIMARY KEY`), auto-incrementável (`AUTO_INCREMENT`), `NOT NULL`.
        
    - `nome`: `VARCHAR(30)`, `NOT NULL`.
        
    - `nascimento`: `DATE`.
        
    - `sexo`: `ENUM('M','F')`.
        
    - `peso`: `DECIMAL(5,2)`.
        
    - `altura`: `DECIMAL(3,2)`.
        
    - `nacionalidade`: `VARCHAR(20)`, `DEFAULT 'Brasil'`.
        
    - `DEFAULT CHARSET` usado para caracteres acentuados (padrão latino).
        

---

## **Comandos SQL – Revisão**

- [05:00–06:36] Classificação dos comandos SQL:
    
    - **DDL (Data Definition Language)**: definição da estrutura (ex.: `CREATE DATABASE`, `CREATE TABLE`).
        
    - **DML (Data Manipulation Language)**: manipulação de dados (ex.: `INSERT INTO`).
        
    - Outros comandos: DQL, DCL, DTL (serão vistos futuramente).
        

---

## **Inserindo Dados – Passo a Passo**

- [06:36–07:57] Preparação do comando `INSERT INTO`:
    
    1. Listar todos os campos da tabela entre parênteses: `(id, nome, nascimento, sexo, peso, altura, nacionalidade)`.
        
    2. Abrir ambiente MySQL Workbench via WampServer no Windows 10.
        
    3. Selecionar o banco de dados: `USE cadastro;`.
        
- [08:34–10:53] Inserção inicial de dados do Godofredo:
    
    - Formato de data MySQL: `YYYY-MM-DD`.
        
    - Valores entre aspas `' '` indicam dados.
        
    - Ponto-e-vírgula `;` encerra o comando.
        
    - Exemplo:
        
        ```sql
        INSERT INTO pessoas (id, nome, nascimento, sexo, peso, altura, nacionalidade)
        VALUES ('1','Godofredo','1984-01-02','masculino','78.5','1.83','Brasil');
        ```
        

---

## **AUTO_INCREMENT e DEFAULT**

- [12:37–16:35] Explicação do `AUTO_INCREMENT`:
    
    - Não é necessário informar o `ID`; ele é gerado automaticamente.
        
    - Uso do `DEFAULT` para valores padrão, como `ID` ou `nacionalidade`.
        
    - Inserção de novos registros usando `DEFAULT` para automatizar valores:
        
        ```sql
        INSERT INTO pessoas VALUES (DEFAULT, 'Creuza','1920-01-01','F','50','1.85', DEFAULT);
        ```
        

---

## **Ordem dos Campos**

- [17:00–18:41] Se os valores forem inseridos na **mesma ordem dos campos da tabela**, não é necessário especificar os nomes dos campos no comando.
    
- Inserção simplificada:
    
    ```sql
    INSERT INTO pessoas
    VALUES (DEFAULT,'Adalgiza','1930-11-02','F','63.2','1.75','Irlanda');
    ```
    

---

## **Inserção de Múltiplos Registros**

- [19:03–21:44] É possível inserir várias pessoas em um único comando `INSERT INTO`:
    
    ```sql
    INSERT INTO pessoas VALUES
    (DEFAULT,'Ana','1975-12-22','F','52.3','1.45','EUA'),
    (DEFAULT,'Cláudio','1975-04-22','M','99','2.15','Brasil'),
    (DEFAULT,'Pedro','1999-12-03','M','87','2','Brasil'),
    (DEFAULT,'Janaína','1987-11-12','F','75.4','1.66','EUA');
    ```
    
- Executando o comando e verificando via `SELECT * FROM pessoas;`, os dados são exibidos corretamente.
    

---

## **Resumo Final**

- [22:29–23:13] Diferenciação de comandos:
    
    - **DDL**: define a estrutura do banco.
        
    - **DML**: manipula dados (ex.: `INSERT INTO`).
        
- Comando `INSERT INTO` é o **primeiro comando DML** aprendido.
    

---

## **Encerramento**

- [23:24–24:01] Professor incentiva a inscrição no canal, likes, favoritos e ativação de notificações por e-mail.
    
