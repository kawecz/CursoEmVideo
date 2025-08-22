
---
<iframe title="Curso MySQL #01 - O que é um Banco de Dados?" src="https://www.youtube.com/embed/Ofktsne-utM?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>

---

# Curso em Vídeo – Banco de Dados MySQL (Aula 1)


[00:00] ♫ Cantarolando ♫ ♫ Bateria tocando ♫  
Olá, pequeno gafanhoto! Há quanto tempo! Estava com saudades de mim?

[00:23] E aí, como é que foram as férias? Eu espero que você tenha aproveitado. Porque, a partir de agora, oficialmente começa o seu curso de banco de dados com MySQL, aqui do Curso em Vídeo.

[00:35] Claro, você já viu na descrição do vídeo, você já recebeu o seu e-mail, você que é inscrito no canal já recebeu o e-mail. Então estamos aí, bem-vindo novamente ao Curso em Vídeo. Esse é um dos vídeos que as pessoas pedem bastante.

[00:47] Muita gente, depois que eu fiz o curso de Algoritmo, depois que eu coloquei o curso de PHP, fala assim:  
“Guanabara, mostra como é que é Banco de Dados para poder integrar com PHP.”  
E esse é o primeiro passo que a gente tá dando nesse sentido.

Então meu querido: coloca esse celular no silencioso!

[01:01] Fecha essa janela do Facebook que eu estou vendo! Tem outros sites (( ͡° ͜ʖ ͡°)) aí também abertos, pode fechar!  
Acomode-se na sua cadeira e vamos começar.

E como eu já disse 1 milhão de vezes: nós vamos começar agora o nosso curso em vídeo de banco de dados.

[01:11] E aí, gostou da piada? Não!? Mas pode esperar que vai ter piada pior até o final.  
E nessa primeira aula, como não poderia deixar de ser, nós vamos ver **a origem dos Bancos de Dados**.

---

## Origem dos Bancos de Dados

[01:27] Se você é um gafanhoto experiente aqui do Curso em Vídeo, já sabe que eu tenho esse problema: não consigo começar nada sem contar suas origens.  
Eu acho muito importante a gente conhecer a origem das coisas para poder entender até onde elas foram — e também compreender que não para por aqui.

[01:45] O que eu vou falar de banco de dados hoje pode ficar velho amanhã.  
Então vamos aproveitar logo para você aprender tudo bonitinho e organizado nesse curso básico para iniciantes de Banco de Dados com MySQL.

E eu vou começar, como sempre, voltando no tempo: para a década de 50.

[02:04] Se você lembra bem da sua aula de História da Computação (seja no colégio, na faculdade, sei lá), todo mundo falou:  
Os primeiros computadores eram universitários e militares, e surgiram na década de 40 (1945–1946). Foi o surgimento dos computadores para uso militar e acadêmico.

E eu não sei se você já se perguntou: nessa época, como é que os dados eram guardados?

[02:22] Eu lhe respondo: antes dos computadores, os dados eram guardados em papel. Sim, papel.  
As pessoas iam se cadastrar, e seus dados eram preenchidos em fichas de papel.

[02:35] Essa era a única maneira da época. E se você parar para pensar, até hoje em alguns lugares ainda é assim. Só que convenhamos: é um negócio muito velho.

Naquela época preenchia-se uma ficha → colocava-se dentro de uma pasta → e essa pasta era armazenada dentro de um arquivo metálico.

[02:50] Isso é óbvio, você provavelmente já viu. Mas os gafanhotos mais jovens talvez só tenham ouvido falar.

O fato é: na década de 50, essa era **a única maneira de se guardar dados**.

---

## Fichas, Pastas e Arquivos

[03:11] Esses três componentes (ficha, pasta, armário/arquivo) têm nomes específicos na área de TI:

- Fichas → Registros
    
- Pastas → Tabelas
    
- Armários → Arquivos
    

[03:36] Recapitulando:

- Armários grandes guardam pastas
    
- Pastas guardam fichas
    

Na TI:

- Arquivos guardam tabelas
    
- Tabelas armazenam registros
    

[03:46] Guarda isso! Vai ser muito importante quando a gente começar a ver MySQL.

---

## Evolução do Armazenamento

[04:08] Na década de 50–60, o desafio era digitalizar todos os dados que antes eram papel.

[04:27] Só que, no início, não foi bonito. Não surgiram bancos de dados logo de cara.  
As fichas eram armazenadas de forma arcaica: pegava-se uma ficha digital e colocava uma após a outra em **arquivos sequenciais** (fitas magnéticas ou cartões perfurados).

[04:49] Como esses meios eram sequenciais, para acessar o 5º registro, era preciso ler o 1º, o 2º, o 3º, o 4º e só então chegar ao 5º.

[05:23] Esse tipo de armazenamento ficou conhecido como **Arquivos Sequenciais**. Era lento, mas ainda assim melhor do que papel.

[06:05] Depois surgiram os discos (disquetes e HDs). Eles permitiam **acesso direto**, sem precisar ler tudo antes.  
Assim nasceram os **Arquivos de Acesso Direto**.

[07:15] Ainda assim, os índices eram muito simples. Aí, na década de 60, o **Departamento de Defesa dos EUA** entrou na jogada.

---

## CODASYL, COBOL e Banco de Dados

[08:01] O Departamento de Defesa criou o evento **CODASYL**, reunindo militares, empresas e universidades.

[08:19] De lá surgiu a linguagem **COBOL**, muito importante para programação de negócios e dados.  
Até hoje algumas empresas ainda usam COBOL.

[09:36] Além disso, o CODASYL discutiu o surgimento de uma nova tecnologia: o **Banco de Dados**.

Ele foi definido com **4 partes principais**:

1. Base de Dados (os dados em si)
    
2. Sistema Gerenciador (SGBD / DBMS)
    
3. Linguagem de Exploração (SQL)
    
4. Programas adicionais (gerência de usuários, automatizações etc.)
    

---

## IBM e os Modelos de Banco de Dados

[12:06] A IBM foi fundamental. Ela propôs:

- **Modelo Hierárquico** (dados em hierarquia)
    
- **Modelo em Rede** (dados interligados em rede inteligente)
    

[13:49] O problema: esses modelos não facilitavam **relacionamentos** entre os dados.

[14:08] Então, nos anos 70, Edgar Codd (pesquisador da IBM) criou o **Modelo Relacional**.  
É esse modelo que usamos até hoje em MySQL.

---

## SQL

[16:09] Para explorar os dados relacionais, surgiu uma linguagem: inicialmente **SEQUEL (Structured Query English Language)**.

[17:00] Depois virou **SQL (Structured Query Language)**.  
SQL é uma linguagem de consulta para dar instruções ao banco de dados.

[17:25] O problema é que cada fabricante criou sua própria variação. ANSI e ISO padronizaram, dando origem ao **ANSI-SQL**.

---

## Bancos de Dados Existentes

[18:23] Exemplos pagos:

- Oracle
    
- IBM DB2
    
- dBase
    
- Microsoft SQL Server
    

[19:00] Exemplos gratuitos:

- MySQL (foco do curso)
    
- MariaDB (fork do MySQL)
    
- Firebird
    
- PostgreSQL
    

---

## Encerramento

[20:21] E é isso, meu querido gafanhoto! Essa foi a **primeira aula** do curso de Banco de Dados.  
Na próxima, vamos aprender como instalar a base e as ferramentas.

[21:01] Não esqueça de se inscrever no canal! No momento em que gravei esse vídeo, já passamos de 120 mil inscritos.

[21:16] Clique aqui para ver a playlist completa do curso, e aqui para acessar o site cursoemvideo.com, onde estão materiais extras.

---
