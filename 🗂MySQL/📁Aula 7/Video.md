
---

<iframe title="Curso MySQL #07 - Manipulando Linhas (UPDATE, DELETE e TRUNCATE)" src="https://www.youtube.com/embed/wXViczeTr6Q?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>

---
## Aula 7 – Manipulação de Registros (MySQL)

**[00:10]** 🎵 Música de abertura 🎵  
Olá, pequeno gafanhoto! Seja bem-vindo a mais uma aula do Curso em Vídeo de MySQL. Eu sou Gustavo Guanabara, seu professor. Nesta **sétima aula de Banco de Dados**, vamos aprender a **manipular registros**.

---

### 1. Conceitos Iniciais

**[00:29]**

- "Manipular registros" também pode aparecer como "manipular linhas" ou "manipular tuplas".
    
- Todos esses termos são sinônimos: **registro = linha = tupla**.
    
- Campos (atributos) de uma tabela são chamados de **colunas**.
    

**[01:11]**  
Na aula anterior vimos como **inserir linhas** usando o comando `INSERT INTO`.  
Se você ainda não sabe usá-lo, assista à aula anterior antes de continuar.

---

### 2. Preparando o Ambiente

**[01:57]**

- Estou com o WAMP e o Workbench abertos.
    
- Para abrir o banco `cadastro`, você pode:
    
    - clicar duas vezes no nome dele, ou
        
    - digitar `USE cadastro;` e pressionar `Ctrl + Enter`.
        

**[02:41]**

- Tabela **gafanhotos**: `id, nome, profissão, nascimento, sexo, peso, altura, nacionalidade`.
    
- Tabela **cursos**: `idcurso, nome, descrição, carga, total de aulas, ano`.
    

**[03:09]**  
Com `SELECT * FROM gafanhotos;` podemos ver os registros.

- Cada **linha** = um registro.
    
- Cada **coluna** = um campo/atributo.
    
- O resultado do `SELECT` é chamado de **Result Set**.
    

---

### 3. Trabalhando com Registros

**[03:59]**

- **Linhas/tuplas/registros** → dados inseridos.
    
- **Colunas/campos/atributos** → estrutura.
    
- Alterar colunas é feito com `ALTER TABLE`.
    
- Hoje veremos como **manipular linhas** (dados).
    

**[04:26]**  
A tabela `cursos` inicialmente está vazia.

- Vamos incluir registros usando `INSERT INTO`.
    
- Já preparei um comando com vários registros (alguns com erros de digitação propositalmente: "HTML4", "PGP", "Jarva"...).
    
- **Digite esse comando no seu Workbench** para acompanhar a aula.
    

---

### 4. Atualizando Registros – Comando UPDATE

**[07:59]**  
Primeira correção:

- Corrigir "HTML4" para "HTML5".
    

Comando:

```sql
UPDATE cursos
SET nome = 'HTML5'
WHERE idcurso = 1;
```

- `UPDATE` = atualize
    
- `SET` = configure
    
- `WHERE` = onde
    

---

**[10:39]**  
Segunda correção: curso `PGP` (linha 4).

- Corrigir nome e ano ao mesmo tempo:
    

```sql
UPDATE cursos
SET nome = 'PHP', ano = 2015
WHERE idcurso = 4;
```

---

**[12:00]**  
Terceira correção: curso `Jarva` (linha 5).

- Corrigir nome, carga e ano:
    

```sql
UPDATE cursos
SET nome = 'Java', carga = 40, ano = 2015
WHERE idcurso = 5
LIMIT 1;
```

- `LIMIT 1` adiciona segurança para afetar apenas **um registro**.
    

---

### 5. O Perigo do UPDATE

**[14:17]**  
Exemplo: atualizar todos os cursos de 2018 para ano `2050` e carga `800`.

```sql
UPDATE cursos
SET ano = 2050, carga = 800
WHERE ano = 2018;
```

⚠️ Esse comando altera **todas as linhas que têm ano 2018**.  
Por padrão, o Workbench bloqueia isso com a opção **Safe Updates** (para proteger o usuário).

Se desmarcar **Safe Updates** em `Preferences > SQL Editor`, será possível rodar esse comando.  
➡️ Mas faça isso apenas em ambiente de testes!

---

### 6. Usando LIMIT para Segurança

**[16:46]**  
Exemplo: alterar os cursos de 2050 para 2018 e carga 0, mas limitando a 1 linha:

```sql
UPDATE cursos
SET ano = 2018, carga = 0
WHERE ano = 2050
LIMIT 1;
```

Assim, apenas a **primeira linha** encontrada será modificada.

➡️ `LIMIT` serve como uma **camada extra de segurança**.

---

### 7. Conclusão

**[17:57]**

- `UPDATE` é um comando poderoso, mas perigoso.
    
- Sempre use `WHERE` para limitar as alterações.
    
- Se possível, use também `LIMIT`.
    
- Tenha sempre **backup do banco de dados**.
    

**[18:26]**  
Na próxima aula, aprenderemos a **remover registros** com segurança (`DELETE`).

---

👉 Resumindo:

- **INSERT** = adiciona linhas.
    
- **UPDATE** = modifica linhas existentes.
    
- **DELETE** = remove linhas.
    
- Cuidado: um `UPDATE` mal feito pode alterar milhares de registros de uma vez.
    
