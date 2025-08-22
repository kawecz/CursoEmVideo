
---
<iframe title="Curso MySQL #04 - Melhorando a Estrutura do Banco de Dados" src="https://www.youtube.com/embed/cHLKtALWDos?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>

---
## Introdução

[00:00] ♫ Cantarolando a música do 007 ♫ Anh? Unh? ♫ Música ♫  
Olá, pequeno _gafanhoto_! Sejam bem-vindos a mais uma aula do seu curso de **Banco de Dados com MySQL**.

O meu nome é **Gustavo Guanabara** e eu sou seu professor.

[00:22] Chegamos à **quarta aula** do curso de Banco de Dados.  
E hoje vamos cumprir a promessa da aula anterior:

> **Melhorar a estrutura do banco de dados que criamos.**

---

## Refazendo o Banco de Dados

[00:38] Na verdade, não vamos apenas “melhorar”, mas **refazer de uma maneira melhor**.  
Isso porque:

- Existem comandos como `ALTER TABLE` (que veremos em breve),
    
- Como não cadastramos ninguém ainda, podemos apagar tudo e recomeçar,
    
- Assim praticamos desde o começo, do jeito certo.
    

[00:59] E de quebra, vamos resolver um problema citado antes:  
O **cadastro do Sr. Vladimir**, que poderia ter vários iguais.  
A solução será o uso de **Chaves Primárias**.

Então, se prepara, abre seu ambiente bonitinho, porque agora a gente vai praticar!

---

## Relembrando a Aula Passada

[01:14] Se você se lembra, apresentei o **Godofredo** (32 anos, sexo masculino, 78kg...),  
que tinha características como:

- Nome,
    
- Idade,
    
- Sexo,
    
- Peso,
    
- Altura,
    
- Nacionalidade.
    

[01:32] Essas características também estavam na **Dolores** (esposa dele) e na filhinha **Godolores**.  
Todos tinham **as mesmas características**, e colocamos num container → dentro de um navio → que representava o banco de dados.

[01:47] Na última aula, aprendemos os comandos:

- `CREATE DATABASE`
    
- `CREATE TABLE`
    

De forma **bem simples**, quase sem parâmetros.

[01:58] Agora vamos evoluir:

- Criar bancos de dados melhores,
    
- Com mais de uma tabela,
    
- Com relações entre tabelas.
    

---

## Melhorando o CREATE DATABASE

[02:12] O comando `CREATE DATABASE` cria um banco de dados.  
Mas podemos deixá-lo **melhor especificado**, principalmente quanto à **formatação de caracteres**.

[03:01] Relembrando do curso de HTML:

- Português usa **acentos** (não presentes no inglês),
    
- Para resolver, usamos **UTF-8**.
    
- O UTF-8 suporta acentuações latinas e de outros idiomas.
    

[03:38] Então, antes de recriar o banco, vamos **apagar o antigo**.

```sql
DROP DATABASE cadastro;
```

[04:42] Pronto, banco “cadastro” apagado.  
Agora vamos recriá-lo de forma aprimorada.

[05:11] O novo comando incluirá **constraints** (regras).  
Exemplo:

```sql
CREATE DATABASE cadastro
  DEFAULT CHARACTER SET utf8
  DEFAULT COLLATE utf8_general_ci;
```

- `CHARACTER SET utf8` → garante suporte a acentos.
    
- `COLLATE utf8_general_ci` → define ordenação/comparação de caracteres.
    

[06:15] Agora nosso banco já nasce configurado para trabalhar corretamente com UTF-8.

---

## Diferença na Prática

[06:55] Se criarmos um banco sem definir nada:

```sql
CREATE DATABASE meubanco;
```

Ele pode vir configurado como **latin1_swedish_ci** (ou outro padrão do ambiente).

[07:41] Ou seja:

- `CREATE DATABASE` simples cria com a configuração padrão do sistema.
    
- Com `CHARACTER SET` e `COLLATE`, garantimos UTF-8.
    

👉 **Conclusão:** Sempre use a forma completa, mesmo sendo mais longa.

---

## Melhorando o CREATE TABLE

[08:22] Agora vamos atualizar também a **estrutura da tabela Pessoas**.

A versão anterior tinha:

- Nome, Idade, Sexo, Peso, Altura, Nacionalidade.
    

Todos usando tipos muito simples (`char`, `varchar`, `int`, `float`).

### Otimizando campos

[09:02] Exemplo:

- `int` ocupa 11 bytes,
    
- `tinyint` ocupa 3 bytes.
    

Num registro pode parecer pouco, mas em **1 milhão de pessoas** faz muita diferença.

### Ajustes planejados

[09:48] - **Idade** será substituída por **data de nascimento** (`DATE`).

- **Sexo** será `ENUM('M','F')`.
    
- **Peso** → `DECIMAL(5,2)`.
    
- **Altura** → `DECIMAL(3,2)`.
    
- **Nacionalidade** → `VARCHAR(20) DEFAULT 'Brasil'`.
    

### Comando final (sem chave primária ainda):

```sql
CREATE TABLE pessoas (
  nome VARCHAR(30) NOT NULL,
  nascimento DATE,
  sexo ENUM('M','F'),
  peso DECIMAL(5,2),
  altura DECIMAL(3,2),
  nacionalidade VARCHAR(20) DEFAULT 'Brasil'
) DEFAULT CHARSET=utf8;
```

---

## Resolvendo o Problema do “Sr. Vladimir”

[17:13] Na estrutura acima, poderíamos cadastrar vários “Vladimirs”.  
Para evitar duplicações, precisamos de uma **chave primária**.

[19:16] Nenhum dos campos existentes serve (nomes podem repetir, altura pode ser igual, etc.).  
Por isso criamos um **campo identificador único**:

```sql
id INT NOT NULL AUTO_INCREMENT,
PRIMARY KEY (id)
```

---

## Comando Final (com chave primária)

```sql
CREATE TABLE pessoas (
  id INT NOT NULL AUTO_INCREMENT,
  nome VARCHAR(30) NOT NULL,
  nascimento DATE,
  sexo ENUM('M','F'),
  peso DECIMAL(5,2),
  altura DECIMAL(3,2),
  nacionalidade VARCHAR(20) DEFAULT 'Brasil',
  PRIMARY KEY (id)
) DEFAULT CHARSET=utf8;
```

---

## Conclusão

[20:57] Comparando com a tabela anterior, esta versão está **muito mais organizada e inteligente**:

- Campos otimizados,
    
- Uso de constraints (`NOT NULL`, `DEFAULT`),
    
- Uso de tipos corretos (`DATE`, `DECIMAL`, `ENUM`),
    
- Chave primária com `AUTO_INCREMENT`.
    

[21:26] Agora temos a tabela **Pessoas** criada corretamente, com a coluna `id` como **chave primária**.
