
---
<iframe title="Curso MySQL #03 - Criando o primeiro Banco de Dados" src="https://www.youtube.com/embed/m9YPlX0fcJk?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>

---

## Introdução

[00:00] ♫ Cantarolando uma música ♫  
Olá, pequeno gafanhoto! Seja bem-vindo a mais uma aula do seu curso de Banco de Dados.  
O meu nome é **Gustavo Guanabara** e eu sou seu professor.

[00:27] Chegamos a mais uma aula do curso de Banco de Dados.  
E dessa vez nós vamos fazer o que está todo mundo esperando: **criar o nosso primeiro banco de dados**.

Mas antes, preciso ser chato mais uma vez e dizer:

[00:39] Você **não pode pular etapas**.  
Talvez você pense:

> “Ah, não, eu quero logo criar o banco de dados. Então vou procurar qual é o vídeo de criar o banco de dados.”

Na primeira aula eu expliquei o que é um banco de dados, para que serve e como funciona.  
Na segunda aula, a gente viu como instalar e preparar o ambiente.

[00:51] Então eu já estou com o ambiente todo preparadinho.  
Se você não viu essa aula, **seu ambiente não está preparado**.  
Então, meu querido: vai na playlist. Clique aqui!

[01:02] Você pode acessar direto pela playlist, ou no site **cursoemvideo.com**, ou na playlist do YouTube.  
Assista às primeiras aulas.

[01:11] É muito valioso, é muito importante que você saiba o que foi falado nas aulas anteriores.  
Então, meu querido, **não pule etapas**.

---

## Público do Curso

[01:18] Assim como todos os cursos do Curso em Vídeo, este de Banco de Dados é voltado para **iniciantes**.

[01:28] Vou repetir várias vezes:

- Se você já é avançado,
    
- Se você já sabe MySQL,
    

Talvez não aprenda muita coisa aqui.

[01:36] Mas mesmo assim, assista, porque **sempre tem algo novo**.  
O foco é para quem:

- Nunca criou um banco de dados,
    
- Criou poucos,
    
- Ou não sabe muito de MySQL.
    

[01:47] Talvez você já saiba criar em outro banco, como Access ou Oracle, mas não em MySQL.  
Aqui vamos ver essas diferenças.

[01:53] Reforçando: o **foco do curso** é:

- **MySQL**,
    
- **SQL** (linguagem e instruções).
    

[02:02] Vamos até passar rapidamente pelo **modelo relacional**, mas não é nosso foco.  
Aqui a ideia é botar a mão na massa — afinal, Curso em Vídeo é isso.

[02:11] E claro, tudo **mastigado e explicado** do jeito que você gosta.

---

## Entendendo Estrutura de Banco de Dados

[02:18] Eu organizei uma historinha para você entender a estrutura de um banco de dados.  
A gente já viu isso na primeira aula, mas vou explicar de outra maneira.

[02:33] Se você ainda está confuso, presta atenção.

---

### Exemplo com Personagens

[02:41] Apresento meu amigo **Godofredo**:

- 32 anos,
    
- Sexo masculino,
    
- 78,5 kg,
    
- 1,83 m,
    
- Brasileiro.
    

[03:03] Assim como você, ele tem características: nome, idade, peso, altura, nacionalidade.

[03:08] Agora, conheça a parceira dele: **Dolores**.

- 30 anos,
    
- Sexo feminino,
    
- 52,3 kg,
    
- 1,65 m,
    
- Mora no México.
    

[03:25] Eles se conheceram numa viagem (inventa a história que quiser).

[03:34] Do fruto desse amor, nasceu **Godolores** (nome criativo, né?):

- 3 anos,
    
- Sexo feminino,
    
- 25,8 kg,
    
- 89 cm,
    
- Nascida nos Estados Unidos.
    

[04:00] Não critique os nomes! O foco é que os três têm **características semelhantes**.

---

### Características e Instâncias

[04:11] Todos possuem:

- Nome,
    
- Idade,
    
- Sexo,
    
- Peso,
    
- Altura,
    
- Nacionalidade.
    

[04:25] Cada um com seus próprios valores.  
Isso os torna **instâncias diferentes** de um mesmo padrão.

[04:35] Esse é o objetivo do banco de dados: **registrar instâncias separadas** de coisas que têm características semelhantes.

[04:48] As características são iguais, mas os valores mudam.

---

### Containers (Tabelas)

[04:58] Imagine um **container** escrito “Pessoas”.  
Todas as pessoas cadastradas vão dentro dele.

[05:18] Todas terão as mesmas características. Algumas podem ser opcionais (ex.: nacionalidade).

[05:37] Agora eu posso criar outro container, por exemplo “Jogos”.  
Pessoas e jogos têm características diferentes, por isso ficam em containers diferentes.

[06:01] Container de Jogos:

- Título,
    
- Fabricante,
    
- Gênero,
    
- Plataforma.
    

[06:11] Ou seja: agrupar semelhantes, separar diferentes.

[06:20] Depois, coloco esses containers dentro de um **navio**.

[06:57] Esse navio é o **Banco de Dados**.

---

## Estrutura no Banco de Dados

- **Banco de Dados** → Coleção de tabelas (navio).
    
- **Tabelas** → Containers que agrupam instâncias semelhantes.
    
- **Registros** → Dados dentro das tabelas (as instâncias).
    
- **Campos** → Características (ex.: nome, idade, altura).
    

[07:13] Resumindo:

- Banco de Dados = Conjunto de tabelas
    
- Tabelas = Conjunto de registros
    
- Registros = Compostos por campos
    

---

## Criando o Banco no MySQL

[07:47] A primeira coisa que tenho que criar é o **banco de dados**.

Comando:

```sql
create database cadastro;
```

[08:16] Onde executar?  
No **ambiente preparado** na aula passada (WAMP + Workbench).

---

## Criando a Tabela Pessoas

[11:14] Tabela **Pessoas** terá os campos:

- Nome
    
- Idade
    
- Sexo
    
- Peso
    
- Altura
    
- Nacionalidade
    

[11:30] Resumindo a hierarquia:

- Banco de Dados → contém tabelas
    
- Tabelas → contêm registros
    
- Registros → compostos por campos
    

---

## Tipos de Dados no MySQL

[13:27] Famílias principais:

- Números
    
- Data e tempo
    
- Literais
    
- Espaciais
    

[15:03] Exemplos:

- Inteiros → TinyInt, SmallInt, Int, MediumInt, BigInt
    
- Reais → Decimal, Float, Double, Real
    
- Lógicos → Bit, Boolean
    
- Datas → Date, DateTime, TimeStamp, Time, Year
    
- Textos → Char, VarChar, Text, MediumText, LongText
    
- Binários → Blob
    
- Coleções → Enum, Set
    

---

## Exemplo de Criação da Tabela

[19:01] Estrutura:

```sql
create table pessoas (
  nome varchar(30),
  idade tinyint,
  sexo char(1),
  peso float,
  altura float,
  nacionalidade varchar(20)
);
```

---

👉 Pronto!  
Organizei sua transcrição em **seções, tópicos e código formatado** sem alterar nenhuma palavra do Guanabara.

Quer que eu faça também uma **versão enxuta** (resumo só com os comandos e conceitos, sem a parte da historinha)?