
---
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