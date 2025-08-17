
---
# [[03 - Criando Banco de Dados MySQL.pdf#page=14&selection=87,0,87,16|Tipos Primitivos]]

# [[03 - Criando Banco de Dados MySQL.pdf#page=14&selection=0,0,0,8|Numérico]]
## **Inteiros (INTEIRO)**

Representam números sem parte decimal. São usados quando só precisamos de valores inteiros, como IDs, contadores, quantidades, etc.

- **TINYINT**: pequeno inteiro (1 byte). Intervalo: -128 a 127.
    
- **SMALLINT**: inteiro pequeno-médio (2 bytes). Intervalo: -32.768 a 32.767.
    
- **MEDIUMINT**: inteiro médio (3 bytes). Intervalo: -8.388.608 a 8.388.607.
    
- **INT ou INTEGER**: inteiro padrão (4 bytes). Intervalo: -2.147.483.648 a 2.147.483.647.
    
- **BIGINT**: inteiro grande (8 bytes). Intervalo: ±9,22e18.
    

✅ **Uso comum:** chaves primárias (`id`), contadores, quantidades.

---
## **Reais (REAL ou DECIMAIS)**

Representam números com parte fracionária (casas decimais). São usados em cálculos que exigem precisão ou aproximação.

- **DECIMAL(p, d)** ou **NUMERIC(p, d)**
    
    - Precisão exata, ideal para valores monetários.
        
    - `p` = número total de dígitos; `d` = casas decimais.
        
    - Exemplo: `DECIMAL(10,2)` → até 10 dígitos, sendo 2 depois da vírgula.
        
- **FLOAT**
    
    - Aproximação com 4 bytes (precisão simples).
        
    - Usado em cálculos científicos.
        
- **DOUBLE** ou **REAL**
    
    - Aproximação com 8 bytes (precisão dupla).
        
    - Mais preciso que `FLOAT`.
        

✅ **Uso comum:** valores monetários (`DECIMAL`), cálculos matemáticos (`FLOAT` ou `DOUBLE`).

---
## **Lógicos (BOOLEAN / LÓGICO)**

No MySQL não existe um tipo lógico puro, mas sim uma simulação com inteiros.

- **BOOLEAN** ou **BOOL** → são apenas _aliases_ para `TINYINT(1)`.
    
- Aceitam valores `0` (**FALSE**) ou `1` (**TRUE**).
    
- Valores diferentes de 0 são interpretados como `TRUE`.
    

✅ **Uso comum:** flags de status (ativo/inativo, pago/não pago).

---
# [[03 - Criando Banco de Dados MySQL.pdf#page=14&selection=4,0,4,10|Data/Tempo]]

## **DATE (Data)**

- Armazena apenas a **data** (ano, mês e dia).
    
- Formato: `'YYYY-MM-DD'` → Exemplo: `2025-08-16`.
    
- Intervalo: `'1000-01-01'` a `'9999-12-31'`.
    

✅ **Uso:** datas de nascimento, datas de eventos, prazos.

---
## **TIME (Hora)**

- Armazena apenas a **hora** (hora, minuto e segundo).
    
- Formato: `'HH:MM:SS'`.
    
- Intervalo: `'-838:59:59'` a `'838:59:59'`.
    
- Pode ser negativo → útil para calcular diferenças de tempo.
    

✅ **Uso:** horários de entrada/saída, duração de eventos.

---
## **DATETIME (Data e Hora)**

- Combina **data + hora** em um único campo.
    
- Formato: `'YYYY-MM-DD HH:MM:SS'`.
    
- Intervalo: `'1000-01-01 00:00:00'` a `'9999-12-31 23:59:59'`.
    
- Não depende do fuso horário (fixo).
    

✅ **Uso:** registros de criação/atualização, logs de ações.

---
## **TIMESTAMP (Data e Hora com Fuso)**

- Similar ao `DATETIME`, mas considera o **fuso horário**.
    
- Internamente armazenado como o número de segundos desde `'1970-01-01 00:00:01 UTC'` (Unix Epoch).
    
- Intervalo: `'1970-01-01 00:00:01 UTC'` a `'2038-01-19 03:14:07 UTC'`.
    
- Pode ser atualizado automaticamente (`DEFAULT CURRENT_TIMESTAMP`).
    

✅ **Uso:** auditoria, logs de sistemas, quando importa o fuso horário.

---
## **YEAR (Ano)**

- Armazena apenas o **ano**.
    
- Formato: `'YYYY'` (ex.: `2025`).
    
- Intervalo: `1901` a `2155`.
    

✅ **Uso:** ano de fabricação, ano de formatura, ano fiscal.

---
# [[03 - Criando Banco de Dados MySQL.pdf#page=14&selection=2,0,2,6|Literal]]

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

---

## **Resumo em Tabela**

|Tipo|Permite múltiplos valores?|Armazenamento interno|Uso|
|---|---|---|---|
|ENUM|Não (somente 1 valor)|Inteiro pequeno|Sexo, status, categoria única|
|SET|Sim|Bitmask (inteiro)|Habilidades, tags, múltiplas opções|

---
# [[03 - Criando Banco de Dados MySQL.pdf#page=14&selection=6,0,6,7|Espacial]]


O MySQL suporta **tipos de dados espaciais** para armazenar informações geográficas e geométricas, como coordenadas, áreas ou formas no espaço. Esses tipos são usados principalmente em **GIS (Geographic Information Systems)** e aplicações de mapas.

---

## **1. GEOMETRY**

- Tipo genérico que pode armazenar **qualquer objeto geométrico**.
    
- Pode ser usado como coluna base para armazenar `POINT`, `LINESTRING`, `POLYGON`, etc.
    
- Exemplo:
    
    ```sql
    CREATE TABLE locais (
      area GEOMETRY
    );
    ```
    

✅ **Uso:** armazenar qualquer geometria sem restrição de tipo específico.

---

## **2. POINT**

- Representa um **ponto no espaço 2D**, com coordenadas X e Y (longitude e latitude).
    
- Exemplo:
    
    ```sql
    CREATE TABLE cidades (
      coordenadas POINT
    );
    
    INSERT INTO cidades (coordenadas) VALUES (POINT(10, 20));
    ```
    

✅ **Uso:** marcar posições exatas no mapa, como cidades, marcos ou eventos.

---

## **3. POLYGON**

- Representa uma **área fechada no plano**, definida por uma sequência de pontos conectados.
    
- Exemplo:
    
    ```sql
    CREATE TABLE parques (
      area POLYGON
    );
    
    INSERT INTO parques (area) VALUES (
      POLYGON((0 0, 0 5, 5 5, 5 0, 0 0))
    );
    ```
    

✅ **Uso:** delimitar regiões, terrenos, bairros ou zonas.

---

## **4. MULTIPOLYGON**

- Representa **várias áreas (polígonos) juntas** em uma única coluna.
    
- Exemplo:
    
    ```sql
    CREATE TABLE estados (
      regioes MULTIPOLYGON
    );
    ```
    

✅ **Uso:** países com várias ilhas, agrupamento de áreas distintas, regiões complexas.

---

## **Resumo em Tabela**

|Tipo|Representa|Exemplo de uso|
|---|---|---|
|**GEOMETRY**|Qualquer geometria|Qualquer objeto geométrico|
|**POINT**|Ponto 2D|Coordenadas de cidade, marco|
|**POLYGON**|Área fechada|Parques, bairros, terrenos|
|**MULTIPOLYGON**|Conjunto de polígonos|Países com ilhas, regiões complexas|

---
