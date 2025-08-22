
---
<iframe title="Curso MySQL #06 - Alterando a Estrutura da Tabela (ALTER TABLE e DROP TABLE)" src="https://www.youtube.com/embed/To9qUcEMuY0?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>

---

## **Introdução**

[00:20](https://youtu.be/To9qUcEMuY0?si=jlzN4qfBEetjXbgD&t=20)  
Olá, pequeno gafanhoto! Seja bem-vindo a mais uma aula do seu curso em vídeo de banco de dados. Eu sou Gustavo Guanabara, seu professor. Chegamos à sexta aula do curso, dando continuidade à aula passada. Hoje iremos aprender a **alterar a estrutura de uma tabela**.

Recapitulando:

- Cada aula apresenta 1 ou 2 comandos no máximo.
    
- Já criamos o banco, criamos a tabela e inserimos dados nela.
    

---

## **Ativando o Servidor e Workbench**

[00:52](https://youtu.be/To9qUcEMuY0?si=jlzN4qfBEetjXbgD&t=52)

- Abra o servidor MySQL (WampServer) e aguarde ficar verde.
    
- Abra o MySQL Workbench e conecte-se à sua última sessão.
    
- O banco de dados “Cadastro” possui a tabela **Pessoas** com os campos:  
    `id`, `nome`, `nascimento`, `sexo`, `peso`, `altura`, `nacionalidade`.
    
- O campo `id` é a **chave primária**.
    

---

## **ALTER TABLE – Alterando Estruturas de Tabela**

### **Adicionar Coluna**

[01:58](https://youtu.be/To9qUcEMuY0?si=jlzN4qfBEetjXbgD&t=118)

- Comando básico:
    

```sql
ALTER TABLE pessoas ADD COLUMN profissao VARCHAR(10);
```

- Observações:
    
    - `column` é opcional.
        
    - Campos não podem ter acentos (`profissao` sem til).
        
    - Tamanho de varchar pode ser aumentado posteriormente com `MODIFY`.
        
- Para ver a tabela:
    

```sql
DESCRIBE pessoas;
-- ou
DESC pessoas;
```

### **Apagar Coluna**

[05:09](https://youtu.be/To9qUcEMuY0?si=jlzN4qfBEetjXbgD&t=309)

- Comando para remover uma coluna:
    

```sql
ALTER TABLE pessoas DROP COLUMN profissao;
```

### **Adicionar Coluna em Posição Específica**

[06:13](https://youtu.be/To9qUcEMuY0?si=jlzN4qfBEetjXbgD&t=373)

- Adicionar após um campo específico:
    

```sql
ALTER TABLE pessoas ADD COLUMN profissao VARCHAR(10) AFTER nome;
```

- Adicionar como primeiro campo:
    

```sql
ALTER TABLE pessoas ADD COLUMN codigo INT FIRST;
```

- Sem `AFTER` ou `FIRST`, a coluna é adicionada no final.
    

---

### **Modificar Coluna**

[09:06](https://youtu.be/To9qUcEMuY0?si=jlzN4qfBEetjXbgD&t=546)

- Alterar tipo ou constraints:
    

```sql
ALTER TABLE pessoas MODIFY COLUMN profissao VARCHAR(20) NOT NULL;
```

- Atenção: se a coluna já tiver valores nulos, colocar `NOT NULL` pode gerar conflito.
    

### **Renomear Coluna**

[11:23](https://youtu.be/To9qUcEMuY0?si=jlzN4qfBEetjXbgD&t=683)

- Comando `CHANGE` para renomear coluna:
    

```sql
ALTER TABLE pessoas CHANGE COLUMN profissao prof VARCHAR(20);
```

- Necessário redefinir constraints se quiser mantê-las (`NOT NULL`, `DEFAULT`, etc.).
    

---

### **Renomear Tabela**

[13:15](https://youtu.be/To9qUcEMuY0?si=jlzN4qfBEetjXbgD&t=795)

- Comando para renomear tabela:
    

```sql
ALTER TABLE pessoas RENAME TO gafanhotos;
```

- Lembre-se de atualizar (refresh) o Workbench para ver a mudança.
    

---

## **Criando Nova Tabela – Cursos**

[14:19](https://youtu.be/To9qUcEMuY0?si=jlzN4qfBEetjXbgD&t=859)

- Comando:
    

```sql
CREATE TABLE IF NOT EXISTS cursos (
  nome VARCHAR(30) NOT NULL UNIQUE,
  descricao TEXT,
  carga INT UNSIGNED,
  totaulas INT UNSIGNED,
  ano YEAR DEFAULT '2016'
) DEFAULT CHARSET=utf8;
```

- Explicações:
    
    - `IF NOT EXISTS` evita sobrescrever tabela existente.
        
    - `VARCHAR` para textos curtos, `TEXT` para textos longos.
        
    - `UNSIGNED` impede números negativos.
        
    - `DEFAULT` define valor padrão se nenhum for informado.
        

---

## **Adicionar Chave Primária Após Criação**

[19:12](https://youtu.be/To9qUcEMuY0?si=jlzN4qfBEetjXbgD&t=1152)

- Adicionar coluna de identificação:
    

```sql
ALTER TABLE cursos ADD COLUMN idcurso INT FIRST;
```

- Tornar coluna chave primária:
    

```sql
ALTER TABLE cursos ADD PRIMARY KEY (idcurso);
```

---

## **DROP TABLE – Apagar Tabela**

[21:53](https://youtu.be/To9qUcEMuY0?si=jlzN4qfBEetjXbgD&t=1313)

- Apagar tabela inteira:
    

```sql
DROP TABLE cursos;
```

- Pode incluir `IF EXISTS` para evitar erro se a tabela não existir:
    

```sql
DROP TABLE IF EXISTS alunos;
```

- Observação: apagar tabela elimina também todos os dados.
    

---

## **Classificação dos Comandos**

[25:24](https://youtu.be/To9qUcEMuY0?si=jlzN4qfBEetjXbgD&t=1524)

- **ALTER TABLE** → DDL (Define estrutura da tabela)
    
- **DROP TABLE** → DDL (Apaga estrutura da tabela; dados apagados são consequência)
    

---

## **Encerramento**

[27:28](https://youtu.be/To9qUcEMuY0?si=jlzN4qfBEetjXbgD&t=1648)

- Inscreva-se no canal para ser avisado de novas aulas.
    
- Utilize a playlist para assistir às aulas anteriores e posteriores.
    
- Ambiente de testes pode ser instalado localmente, sem internet.
    
- Curso é prático, focado em iniciantes, com exercícios passo-a-passo.
    

---

## **Dicas Finais do Professor**

[28:35](https://youtu.be/To9qUcEMuY0?si=jlzN4qfBEetjXbgD&t=1715)

- Nunca altere bancos de produção diretamente.
    
- Sempre faça backup antes de executar `DROP` ou `ALTER`.
    
- Pratique constantemente para fixar os comandos e conceitos.
    

---

## **Nota Pessoal do Professor**

[30:09](https://youtu.be/To9qUcEMuY0?si=jlzN4qfBEetjXbgD&t=1809)

- O curso é feito com esforço e dedicação, incluindo ajustes de iluminação e gravação em condições reais.
    
- Incentivo a praticar, compartilhar e estudar com atenção.
    
