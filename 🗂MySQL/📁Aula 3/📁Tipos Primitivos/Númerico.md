
---
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