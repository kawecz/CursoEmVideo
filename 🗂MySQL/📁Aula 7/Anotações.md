
---
### **1. Introdução ao tema**

- O professor Gustavo Guanabara inicia a **sétima aula** de MySQL explicando que o foco será **manipulação de registros**.
    
- "Registros", "linhas" e "tuplas" significam a mesma coisa: uma linha dentro da tabela do banco de dados.
    
- Já os **campos/atributos** são as **colunas** da tabela.
    

---

**2. Revisão do contexto**

- Antes dessa aula já aprendemos a **criar tabelas** e a **inserir registros** (`INSERT INTO`).
    
- Para manipular colunas usamos o comando `ALTER TABLE`.
    
- Agora o objetivo é **alterar ou remover registros** (linhas) dentro das tabelas.
    

---

**3. Estrutura do banco de exemplo**

- Banco de dados utilizado: `cadastro`.
    
- Tabelas principais:
    
    - `gafanhotos`: colunas → id, nome, profissão, nascimento, sexo, peso, altura, nacionalidade.
        
    - `cursos`: colunas → idcurso, nome, descrição, carga, total de aulas, ano.
        

---

**4. Diferença entre linha e coluna**

- **Linha (registro/tupla):** cada conjunto de dados (ex.: um aluno ou um curso).
    
- **Coluna (campo/atributo):** cada tipo de informação (ex.: nome, idade, carga horária).
    
- Exemplo: `SELECT * FROM gafanhotos;` → mostra as linhas (registros) e as colunas (atributos).
    

---

**5. Inserindo registros para testes**

- O professor insere **10 registros na tabela `cursos`** usando `INSERT INTO`.
    
- Alguns dados estão **errados de propósito**:
    
    - "HTML4" → deveria ser "HTML5".
        
    - "PGP" em vez de "PHP".
        
    - "Jarva" em vez de "Java".
        
    - Datas e cargas erradas.
        

Esses erros servem para treinar os comandos de atualização.

---

**6. Atualizando registros (UPDATE)**

- O comando básico é:
    

```sql
UPDATE nome_tabela 
SET coluna1 = valor1, coluna2 = valor2 
WHERE condição;
```

- **Exemplo 1:** corrigindo “HTML4” para “HTML5”:
    

```sql
UPDATE cursos 
SET nome = 'HTML5' 
WHERE idcurso = 1;
```

- **Exemplo 2:** corrigindo nome e ano do curso PHP:
    

```sql
UPDATE cursos 
SET nome = 'PHP', ano = 2015 
WHERE idcurso = 4;
```

- **Exemplo 3:** corrigindo várias colunas ao mesmo tempo (curso Java):
    

```sql
UPDATE cursos 
SET nome = 'Java', carga = 40, ano = 2015 
WHERE idcurso = 5 
LIMIT 1;
```

---

**7. Uso do `LIMIT` como segurança**

- `LIMIT` restringe a quantidade de registros afetados.
    
- Exemplo:
    

```sql
UPDATE cursos 
SET ano = 2018, carga = 0 
WHERE ano = 2050 
LIMIT 1;
```

→ Mesmo que existam várias linhas com ano = 2050, só **1 será alterada**.

---

**8. Perigos do `UPDATE` sem cuidado**

- Se não usar `WHERE` ou usar errado, pode alterar **todas as linhas** da tabela.
    
- Exemplo:
    

```sql
UPDATE cursos 
SET ano = 2050, carga = 800 
WHERE ano = 2018;
```

→ Vai alterar **todas as linhas** de 2018.

- O **Workbench tem o “Safe Updates” ativado por padrão**, que bloqueia updates perigosos. Ele pode ser desativado temporariamente para fins de estudo.
    

---

**9. Boas práticas e riscos**

- Sempre use `WHERE` com chave primária para evitar erros.
    
- Sempre tenha **backup** antes de manipular registros.
    
- Evite `UPDATE` em bancos de produção sem testes.
    

---

**10. Conclusão da aula**

- Aprendemos a **manipular registros (linhas)** com `UPDATE`.
    
- Vimos:
    
    - Alteração de um campo.
        
    - Alteração de vários campos ao mesmo tempo.
        
    - Alteração de várias linhas.
        
    - Uso de `LIMIT` para segurança.
        
- Foi ressaltado o perigo de comandos mal usados e a importância de **backup**.
    
- Próxima aula: aprender a **criar backups no MySQL**.
    

---

✅ **Resumo rápido dos comandos principais:**

```sql
-- Atualizar 1 coluna
UPDATE cursos SET nome = 'HTML5' WHERE idcurso = 1;

-- Atualizar várias colunas
UPDATE cursos SET nome = 'PHP', ano = 2015 WHERE idcurso = 4;

-- Atualizar várias linhas (perigoso!)
UPDATE cursos SET ano = 2050, carga = 800 WHERE ano = 2018;

-- Atualizar com segurança (LIMIT)
UPDATE cursos SET ano = 2018, carga = 0 WHERE ano = 2050 LIMIT 1;
```
