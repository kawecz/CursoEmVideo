
---
No MySQL, literais representam **valores fixos** que você escreve diretamente em consultas. Eles podem ser de vários tipos: **caractere, texto, binário e coleções**. Cada tipo é usado para armazenar dados específicos de forma eficiente.

---

## **1. Literal de Caractere (CHAR)**

- Representa **um único caractere** ou uma pequena sequência de caracteres de tamanho fixo.
    
- É armazenado em colunas do tipo `CHAR(n)`.
    
- Exemplo:
    
    ```sql
    'A'
    'K'
    ```
    

✅ **Uso:** códigos, iniciais, siglas curtas.

---

## **2. Literal de Texto (STRING / VARCHAR / TEXT)**

- Representa **sequências de caracteres de tamanho variável**.
    
- Pode conter palavras, frases ou grandes blocos de texto.
    
- Tipos de coluna: `VARCHAR(n)` (tamanho variável), `TEXT` (grande quantidade de texto).
    
- Exemplos:
    
    ```sql
    'Kawe Cezar'
    'Olá, mundo!'
    ```
    

✅ **Uso:** nomes, endereços, descrições, comentários.

---
# [[03 - Criando Banco de Dados MySQL.pdf#page=14&selection=16,0,16,5|Texto]]

No MySQL, os tipos de texto são usados para armazenar **strings de tamanho variável**, de pequenas mensagens a grandes blocos de texto. Eles diferem principalmente pelo **tamanho máximo de armazenamento** e pelo **uso de memória**.

---

## **1. TINYTEXT**

- Armazena **textos curtos**.
    
- Tamanho máximo: 255 caracteres (~255 bytes).
    
- Ideal para campos pequenos como: títulos, nomes curtos, códigos.
    
- Exemplo:
    
    ```sql
    'Olá!'
    'Kawe'
    ```
    

---

## **2. TEXT**

- Armazena **textos de tamanho médio**.
    
- Tamanho máximo: 65.535 caracteres (~64 KB).
    
- Ideal para descrições, comentários ou pequenos artigos.
    
- Exemplo:
    
    ```sql
    'Este é um texto de exemplo que pode ter várias linhas...'
    ```
    

---

## **3. MEDIUMTEXT**

- Armazena **textos maiores**.
    
- Tamanho máximo: 16.777.215 caracteres (~16 MB).
    
- Ideal para textos longos como capítulos de livros, artigos longos ou conteúdos extensos.
    

---

## **4. LONGTEXT**

- Armazena **textos muito grandes**.
    
- Tamanho máximo: 4.294.967.295 caracteres (~4 GB).
    
- Ideal para armazenamento de arquivos de texto muito grandes, como logs extensos ou documentos inteiros.
    

---

## **Resumo em Tabela**

|Tipo|Tamanho Máximo|Uso|
|---|---|---|
|**TINYTEXT**|255 caracteres|Pequenos textos, títulos, códigos|
|**TEXT**|65.535 caracteres|Descrições, comentários, artigos curtos|
|**MEDIUMTEXT**|16.777.215 caracteres|Artigos longos, capítulos|
|**LONGTEXT**|4.294.967.295 caracteres|Textos gigantes, logs, documentos grandes|

---
# [[03 - Criando Banco de Dados MySQL.pdf#page=14&selection=18,0,18,7|Binário]]

No MySQL, os tipos **BLOB** (“Binary Large Object”) são usados para armazenar **dados binários** de diferentes tamanhos, como imagens, arquivos, vídeos ou qualquer dado não textual. Eles são similares aos tipos de texto (`TINYTEXT`, `TEXT`, etc.), mas armazenam **bytes puros**, não caracteres.

---

## **1. TINYBLOB**

- Armazena **dados binários pequenos**.
    
- Tamanho máximo: 255 bytes.
    
- Ideal para pequenos arquivos ou ícones.
    
- Exemplo:
    
    ```sql
    x'4D7953514C'  -- valor hexadecimal
    ```
    

---

## **2. BLOB**

- Armazena **dados binários médios**.
    
- Tamanho máximo: 65.535 bytes (~64 KB).
    
- Ideal para pequenas imagens, documentos ou arquivos binários de tamanho médio.
    

---

## **3. MEDIUMBLOB**

- Armazena **dados binários grandes**.
    
- Tamanho máximo: 16.777.215 bytes (~16 MB).
    
- Ideal para vídeos curtos, imagens grandes, backups pequenos.
    

---

## **4. LONGBLOB**

- Armazena **dados binários muito grandes**.
    
- Tamanho máximo: 4.294.967.295 bytes (~4 GB).
    
- Ideal para vídeos longos, arquivos extensos ou dados binários enormes.
    

---

## **Resumo em Tabela**

|Tipo|Tamanho Máximo|Uso|
|---|---|---|
|**TINYBLOB**|255 bytes|Pequenos arquivos, ícones|
|**BLOB**|65.535 bytes|Imagens pequenas, documentos|
|**MEDIUMBLOB**|16.777.215 bytes|Imagens grandes, vídeos curtos|
|**LONGBLOB**|4.294.967.295 bytes|Vídeos longos, arquivos enormes|

---
# [[03 - Criando Banco de Dados MySQL.pdf#page=14&selection=20,0,20,7|Coleção]]

No MySQL, às vezes queremos limitar os valores possíveis de uma coluna a um **conjunto pré-definido**. Para isso existem os tipos **ENUM** (valor único) e **SET** (um ou mais valores da lista). Eles ajudam a **garantir integridade de dados** e economizar espaço.

---

## **1. ENUM (Enumerado)**

- Permite **apenas um valor de uma lista pré-definida**.
    
- Sintaxe:
    
    ```sql
    ENUM('valor1','valor2','valor3',...)
    ```
    
- Internamente, cada valor é armazenado como **número inteiro pequeno**, mas é apresentado como texto.
    
- Exemplos:
    
    ```sql
    CREATE TABLE usuarios (
      sexo ENUM('masculino','feminino','outro')
    );
    
    INSERT INTO usuarios (sexo) VALUES ('masculino');  -- válido
    INSERT INTO usuarios (sexo) VALUES ('indefinido'); -- inválido
    ```
    

✅ **Uso:** sexo, status (ativo/inativo), categorias únicas.

---

## **2. SET**

- Permite **uma ou mais combinações de valores da lista pré-definida**.
    
- Sintaxe:
    
    ```sql
    SET('valor1','valor2','valor3',...)
    ```
    
- Armazena internamente como **bitmask**, economizando espaço mesmo com múltiplos valores selecionados.
    
- Exemplos:
    
    ```sql
    CREATE TABLE habilidades (
      habilidades SET('ler','escrever','programar','cantar')
    );
    
    INSERT INTO habilidades (habilidades) VALUES ('ler,programar');  -- válido
    INSERT INTO habilidades (habilidades) VALUES ('dançar');        -- inválido
    ```
    

✅ **Uso:** múltiplas escolhas, preferências, habilidades ou tags.

## **Resumo em Tabela**

|Tipo|Permite múltiplos valores?|Armazenamento interno|Uso|
|---|---|---|---|
|ENUM|Não (somente 1 valor)|Inteiro pequeno|Sexo, status, categoria única|
|SET|Sim|Bitmask (inteiro)|Habilidades, tags, múltiplas opções|


