
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
