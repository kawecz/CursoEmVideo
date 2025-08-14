
---
## O que é o MySQL?

O MySQL é o sistema de gerenciamento de banco de dados de código aberto mais conhecido no mundo. Os [bancos de dados](https://www.oracle.com/br/database/what-is-database/) são os repositórios de dados essenciais para todas as aplicações de software. Por exemplo, sempre que alguém realiza uma pesquisa na Web, faz login em uma conta ou conclui uma transação, um banco de dados armazena as informações para que elas possam ser acessadas no futuro. O MySQL se destaca nessa tarefa.

SQL, que significa [linguagem de consulta estruturada em inglês](https://docs.oracle.com/en/database/oracle/oracle-database/19/sqlrf/Introduction-to-Oracle-SQL.html#GUID-049B7AE8-11E1-4110-B3E4-D117907D77AC), é uma linguagem de programação usada para recuperar, atualizar, excluir e manipular dados em bancos de dados relacionais. Oficialmente, "SQL" deve ser lido como uma sigla, mas é comumente usado como um acrônimo. Como o nome sugere, o MySQL é um banco de dados relacional [baseado em SQL](https://www.oracle.com/br/database/technologies/appdev/sql.html) projetado para armazenar e gerenciar dados estruturados. No entanto, nos últimos anos, a Oracle adicionou suporte adicional, inclusive para o popular tipo de dados JSON.

**Principais conclusões**

- Em 2024, o MySQL mantém seu título de banco de dados de código aberto mais popular do mundo.
- Como um sistema de banco de dados relacional, MySQL armazena dados em linhas e colunas definidas por esquemas.
- O MySQL deriva parte de seu nome da linguagem SQL, que é usada para gerenciar e consultar dados em bancos de dados.
- Ele oferece transações ACID completas e pode lidar com um alto volume de conexões simultâneas.

### Explicação do MySQL

O MySQL é um RDBMS de código aberto que usa SQL para criar e gerenciar bancos de dados. Como um banco de dados relacional, o MySQL armazena dados em tabelas de linhas e colunas organizadas em esquemas. Um esquema define como os dados são organizados e armazenados e descreve o relacionamento entre várias tabelas. Com esse formato, os desenvolvedores podem facilmente armazenar, recuperar e analisar diversos tipos de dados, incluindo texto simples, números, datas, horas e, mais recentemente, JSON e [vetores](https://blogs.oracle.com/mysql/post/become-an-ai-developer-with-mysql-heatwave).

Como o MySQL é de código aberto, ele inclui vários recursos desenvolvidos em estreita cooperação com uma comunidade de usuários há mais de 30 anos. Dois recursos em que os desenvolvedores confiam são o suporte do MySQL para transações ACID e a capacidade de escalabilidade do MySQL. ACID significa “atomicidade, consistência, isolamento e durabilidade”, as quatro propriedades que garantem que as transações do banco de dados sejam processadas de forma confiável e precisa. Com transações ACID, o MySQL pode garantir que todas as modificações de dados sejam feitas de forma consistente e confiável, mesmo em caso de falha no sistema. O MySQL pode ser ampliado para oferecer suporte a bancos de dados muito grandes e pode lidar com um alto volume de conexões simultâneas.

O desempenho, a facilidade de uso e o baixo custo do MySQL, combinados com sua capacidade de dimensionar de forma confiável à medida que uma empresa cresce, o tornaram o banco de dados de código aberto mais popular do mundo.

### MySQL: Distinguindo-o do SQL

O acrônimo “SQL” significa Structured Query Language (linguagem de consulta estruturada), um tipo de linguagem de programação usada para manipular informações em um banco de dados. O MySQL usa a linguagem SQL para gerenciar e consultar informações em bancos de dados e, por isso, usa a sigla como parte de seu nome. Se você tiver dados armazenados em um RDBMS do MySQL, poderá gravar prompts SQL simples para adicionar, pesquisar, analisar e recuperar dados.

## Compreendendo o MySQL: recursos e popularidade

A capacidade do MySQL de armazenar e analisar com eficiência grandes quantidades de dados significa que ele pode ajudar em diferentes tarefas, como informar decisões empresariais complexas e até encontrar um restaurante local para um encontro à noite. Veja as principais funcionalidades que tornam o MySQL tão difundido no cenário tecnológico atual.

### Um sistema abrangente de banco de dados relacional

O MySQL é conhecido como um sistema de gerenciamento de banco de dados flexível e fácil de usar. Verá que ele é usado por desenvolvedores autônomos que buscam um banco de dados de código aberto para um projeto pequeno até por sites e aplicações mais acessados do mundo. O MySQL vem evoluindo para acompanhar a demanda há quase 30 anos e oferece transações ACID que garantem que as modificações de dados sejam feitas de forma consistente, mesmo ao suportar um alto volume de conexões simultâneas.

---

### A vantagem do código aberto do MySQL

O MySQL é de [código aberto](https://www.oracle.com/br/developer/open-source-developers/), o que significa que qualquer pessoa pode fazer download do software MySQL pela internet e usá-lo gratuitamente. As organizações também podem alterar seu código de origem para atender às suas necessidades. O software MySQL usa a [Licença Pública Geral GNU](https://www.gnu.org/licenses/license-list.html) (GNU General Public License, GPL), que é um conjunto comum de regras para definir o que pode ou não ser feito com o software em várias situações. Se uma organização não se sentir confortável com a GNU GPL ou desejar incorporar o código do MySQL em uma aplicação comercial, ela poderá comprar uma versão licenciada comercialmente. Consulte a página [Políticas legais do MySQL](https://www.mysql.com/about/legal/) para obter mais informações sobre licenciamento.

### Por que os desenvolvedores preferem o desempenho e a flexibilidade do MySQL

O MySQL é conhecido por ser fácil de configurar e usar, mas confiável e escalável o suficiente para organizações com conjuntos de dados muito grandes e um grande número de usuários. A arquitetura de replicação nativa do MySQL permite que organizações como o Facebook escalonem aplicações para dar suporte a bilhões de usuários.

Outros fatores importantes na popularidade do MySQL incluem recursos de aprendizagem abundantes e a vibrante [comunidade global](https://dev.mysql.com/community/) do software.

---

## Como o MySQL Funciona?

Cada aplicação de software precisa de um repositório para armazenar dados para que as informações possam ser acessadas, atualizadas e analisadas no futuro. Um [banco de dados relacional](https://www.oracle.com/br/database/what-is-a-relational-database/) como o MySQL armazena dados em tabelas separadas, em vez de colocar todos os dados em um só lugar. A estrutura do banco de dados é organizada em arquivos otimizados para que os dados possam ser acessados rapidamente. Esse modelo de dados lógico, com objetos como tabelas de dados, exibições, linhas e colunas, oferece aos desenvolvedores e administradores de banco de dados um ambiente de programação flexível. Eles podem configurar regras que controlam as relações entre diferentes campos de dados, como um para um, um para muitos, exclusivo, obrigatório ou opcional, e adicionar "apontadores" entre diferentes tabelas. O sistema aplica essas regras para que, com um banco de dados bem projetado, a aplicação nunca veja dados inconsistentes, duplicados, órfãos ou desatualizados.

O MySQL Database é um sistema cliente/servidor que consiste em um servidor SQL de vários threads que suporta diferentes backends, vários programas e bibliotecas clientes, uma opção de ferramentas administrativas e uma ampla variedade de interfaces de programação de aplicações (APIs). O MySQL está disponível como uma biblioteca de vários threads integrada que os desenvolvedores podem vincular a aplicações para obter um produto independente menor, mais rápido e mais fácil de gerenciar.

SQL é a linguagem de programação padronizada mais comum usada para acessar bancos de dados. Dependendo do ambiente de programação, um desenvolvedor pode inserir SQL diretamente, por exemplo, para gerar relatórios. Também é possível incorporar instruções SQL ao código gravado em outra linguagem de programação, ou usar uma API específica da linguagem que oculte a sintaxe SQL.

---

## Por que o MySQL é importante?

O MySQL é importante devido à sua onipresença e ao papel fundamental dos bancos de dados à medida que a quantidade de dados aumenta exponencialmente e alimenta a IA. O MySQL sustenta uma grande variedade de sites e aplicações, e ajuda empresas no mundo todo a organizar, analisar e proteger seus dados.

Outros fatores também ajudam a manter a popularidade duradoura do MySQL.

- **Código aberto com amplo suporte da comunidade**
    
    Durante as quase três décadas do MySQL como o principal RDBMS de código aberto, uma comunidade global vibrante cresceu em torno dele. Isso é importante porque a comunidade fornece uma riqueza de conhecimentos e recursos, como tutoriais, dicas em fóruns e muito mais. Ao testar o software em vários cenários de casos de uso, a comunidade também ajudou a descobrir e corrigir bugs, tornando o MySQL altamente confiável.
    
    O compartilhamento de conhecimento, a solução de problemas e a inovação contínua da comunidade de código aberto mantêm os usuários do MySQL na vanguarda dos avanços tecnológicos.
    
- **Alto desempenho e confiabilidade**
    
    O MySQL consegue se adaptar a diferentes ambientes, incluindo projetos de desenvolvedores individuais e aplicações de missão crítica que exigem estabilidade consistente. O RDBMS de código aberto pode lidar com altos volumes de dados e conexões simultâneas, além de fornecer operações ininterruptas em circunstâncias críticas. Em parte, isso se deve aos mecanismos robustos de replicação e failover do MySQL, que ajudam a minimizar o risco de perda de dados.
    
- **Facilidade de uso e compatibilidade**
    
    O MySQL é frequentemente elogiado por ser fácil de usar e por oferecer [ampla compatibilidade](https://www.mysql.com/support/supportedplatforms/database.html) com plataformas tecnológicas e linguagens de programação, incluindo Java, Python, PHP e JavaScript. Ele também oferece suporte à replicação de uma versão para a posterior, portanto, uma aplicação que executa o MySQL 5.7 pode facilmente replicá-la para o MySQL 8.0.
    
    Além disso, o MySQL oferece flexibilidade no desenvolvimento de aplicações de banco de dados tradicionais SQL e NoSQL sem esquema. Isso significa que os desenvolvedores podem misturar e combinar dados relacionais e documentos JSON no mesmo banco de dados e aplicação.
    
- **Economia e escalabilidade**
    
    Como o MySQL é de código aberto, ele está disponível gratuitamente, além do hardware on-premises no qual é executado e do treinamento sobre como usá-lo. Uma comunidade global de usuários do MySQL fornece acesso econômico a recursos de aprendizagem e experiência em solução de problemas. A Oracle também oferece [uma ampla gama de cursos de treinamento](https://www.mysql.com/training/).
    
    Quando é hora de expandir, o MySQL oferece suporte ao multithreading para lidar com grandes volumes de dados de forma eficiente. Os recursos de failover automatizado ajudam a reduzir os custos potenciais de tempo de inatividade não planejado.

---
    

## Benefícios do MySQL

O MySQL é rápido, confiável, escalável e fácil de usar. Ele foi originalmente desenvolvido para processar bancos de dados grandes rapidamente e é usado em ambientes de produção altamente exigentes por muitos anos. O MySQL oferece um conjunto abrangente e útil de funções, e está em constante desenvolvimento pela Oracle, para acompanhar as novas demandas tecnológicas e comerciais. A conectividade, a velocidade e a segurança do MySQL o tornam altamente adequado para acessar bancos de dados na internet.

Os principais benefícios do MySQL incluem:

- **Fácil de usar.** Os desenvolvedores podem instalar o MySQL em minutos e o banco de dados é fácil de gerenciar.
- **Confiabilidade.** É um dos bancos de dados mais maduros e amplamente utilizados. Foi testado em uma ampla variedade de cenários por quase 30 anos, inclusive por muitas das maiores empresas do mundo. As organizações dependem do MySQL para executar aplicações essenciais para os negócios por causa de sua confiabilidade.
- **Escalabilidade.** O MySQL é escalonado para atender às demandas das aplicações mais acessadas. A arquitetura de replicação nativa do MySQL permite que organizações, incluindo Facebook, Netflix e Uber, dimensionem aplicações para oferecer suporte a dezenas de milhões de usuários ou mais.
- **Desempenho.** O MySQL é um sistema de banco de dados comprovado de alto desempenho e administração zero, e vem em [uma variedade de edições](https://www.mysql.com/products/) para atender a praticamente qualquer demanda. O [HeatWave MySQL](https://www.oracle.com/br/mysql/) baseado em nuvem fornece desempenho e custo-benefício incomparáveis, de acordo com benchmarks do setor, incluindo TPC-H, TPC-DS e CH-benCHmark.
- **Alta disponibilidade.** O MySQL oferece um conjunto completo de tecnologias de replicação nativas e totalmente integradas para alta disponibilidade e recuperação de desastres. Para aplicações essenciais aos negócios e compromissos de acordo de nível de serviço, os clientes podem atingir o objetivo de ponto de recuperação zero (perda zero de dados) e o objetivo de tempo de recuperação zero segundos (failover automático).
- **Segurança.** A [segurança de dados](https://www.oracle.com/br/security/database-security/what-is-data-security/) envolve proteção e conformidade com as regulamentações do setor e do governo, incluindo o Regulamento Geral de Proteção de Dados da União Europeia, o Padrão de Segurança de Dados do Setor de Cartões de Pagamento, a Lei de Portabilidade e Responsabilidade de Seguro de Saúde e os Guias de Implementação Técnica de Segurança da Agência de Sistemas de Informação de Defesa. O [MySQL Enterprise Edition](https://www.oracle.com/br/mysql/enterprise/) fornece recursos avançados de segurança, incluindo autenticação/autorização, criptografia transparente de dados, auditoria, mascaramento de dados e um firewall de banco de dados.
- **Flexibilidade.** O Armazenamento de Documentos do MySQL oferece aos usuários flexibilidade máxima no desenvolvimento de aplicações de banco de dados tradicionais sem esquema SQL e NoSQL. Os desenvolvedores podem misturar e combinar dados relacionais e documentos JSON no mesmo banco de dados e aplicação.

---

### O que é o HeatWave MySQL?

HeatWave é um acelerador de consultas na memória para o MySQL Database. O HeatWave MySQL é o único serviço de banco de dados em nuvem MySQL que oferece essa aceleração e combina transações com análises em tempo real, eliminando a complexidade, a latência, o custo e o risco de duplicação de extração, transformação e carregamento (ETL).

Como resultado, os usuários podem ver aumentos de ordens de magnitude no desempenho do MySQL para análises e cargas de trabalho mistas. Além disso, o HeatWave AutoML permite que desenvolvedores e analistas de dados criem, treinem, implementem e expliquem as saídas de modelos de [machine learning](https://www.oracle.com/br/data-science/machine-learning/what-is-machine-learning/) no HeatWave MySQL de maneira totalmente automatizada. Eles também podem se beneficiar da IA ​​generativa integrada e automatizada usando o [HeatWave GenAI](https://www.oracle.com/br/heatwave/genai/).

---

### Principais recursos do HeatWave MySQL

O HeatWave MySQL pode ajudar a melhorar significativamente o desempenho da consulta MySQL e permite que as organizações acessem análises em tempo real em seus dados transacionais sem movê-los para um banco de dados de análise separado. Aumente a segurança dos dados e implemente aplicações com tecnologia do HeatWave MySQL na Oracle Cloud Infrastructure (OCI), na Amazon Web Services (AWS) ou no Microsoft Azure.

O HeatWave MySQL é o único serviço de nuvem MySQL que integra o HeatWave, um mecanismo de processamento de consultas colunar híbrido, massivamente paralelo e na memória. É o único serviço de nuvem MySQL desenvolvido no MySQL Enterprise Edition. Recursos avançados fornecem medidas de segurança adicionais para ajudar as empresas a proteger dados ao longo do seu ciclo de vida e atender aos requisitos regulatórios. Além disso, o HeatWave Autopilot incorporado ajuda a melhorar automaticamente o desempenho do MySQL e a reduzir os custos com a automação baseada em machine learning, sem exigir conhecimento especializado em ajuste de banco de dados. O Autopilot pode ajudar a aumentar a produtividade de desenvolvedores e DBAs e ajudar a eliminar erros humanos.

O HeatWave MySQL também permite que você aproveite um conjunto mais amplo de recursos integrados do HeatWave, incluindo:

- **[HeatWave Lakehouse](https://www.oracle.com/br/heatwave/lakehouse/).** Consulte dados no armazenamento de objetos em vários formatos de arquivo, incluindo CSV, Parquet, Avro e JSON. Exporte arquivos de outros bancos de dados usando sintaxe SQL padrão. Você também pode combiná-los com dados transacionais em bancos de dados MySQL.
- **[HeatWave AutoML](https://www.oracle.com/br/heatwave/automl/).** Crie, treine, implemente e explique modelos de machine learning de forma rápida e fácil em HeatWave MySQL. Não há necessidade de mover os dados para um serviço de nuvem de machine learning separado, nem ser especialista em machine learning.
- **[HeatWave GenAI](https://www.oracle.com/br/heatwave/genai/).** Obtenha IA generativa integrada e automatizada com grandes modelos de linguagem (LLMs) no banco de dados, armazenamento automatizado de vetores no banco de dados, processamento de vetores em larga escala e a capacidade de ter conversas contextuais em linguagem natural. Agora, as empresas podem aproveitar a IA generativa sem experiência em IA, movimentação de dados ou custos adicionais.

---

## Casos de uso do MySQL

Os casos de uso do MySQL incluem o gerenciamento de dados de clientes e produtos para sites de comércio eletrônico, a ajuda dos sistemas de gerenciamento de conteúdo a fornecer conteúdo da web, o rastreamento seguro de transações e dados financeiros e a capacitação de sites de redes sociais armazenando perfis e interações de usuários.

A capacidade do MySQL de lidar com grandes conjuntos de dados e consultas complexas o torna uma tecnologia essencial em todos os setores e casos de uso, incluindo:

- **E-commerce.** Muitas das maiores aplicações de comércio eletrônico do mundo, incluindo Uber e Booking.com, executam seus sistemas transacionais no MySQL. É uma escolha popular para gerenciar perfis de usuário, credenciais, conteúdo do usuário e dados financeiros, como pagamentos, além da detecção de fraude.
- **Plataformas sociais.** Facebook, X (antigo Twitter) e LinkedIn estão entre as maiores redes sociais do mundo, e todas dependem do MySQL.
- **Gerenciamento de conteúdo.** Ao contrário dos bancos de dados de documentos de finalidade única, o MySQL ativa SQL e NoSQL com um único banco de dados. O Armazenamento de Documentos MySQL permite operações CRUD e usa o poder do SQL para consultar dados de documentos JSON para relatórios e análises.
- **SaaS e ISVs.** Mais de 2.000 ISVs, OEMs e VARs, incluindo Ericsson e IBM, contam com o MySQL como banco de dados integrado para tornar suas aplicações, hardware e appliances mais competitivos; comercializar produtos mais rápido e reduzir o custo dos produtos vendidos. O MySQL também é o banco de dados por trás de aplicações SaaS populares, como Zendesk. Outras aplicações populares que usam o MySQL incluem aplicativos de jogos online, marketing digital, sistemas de ponto de venda de varejo e sistemas de monitoramento da Internet das Coisas.
- **Aplicações on-premises com o MySQL Enterprise Edition.** O MySQL Enterprise Edition inclui o conjunto mais abrangente de recursos avançados, juntamente com ferramentas de gerenciamento e suporte técnico, permitindo que as organizações atinjam os mais altos níveis de escalabilidade, segurança, confiabilidade e tempo de atividade do MySQL. Ele reduz os riscos, os custos e a complexidade ao desenvolver, implementar e gerenciar aplicativos MySQL essenciais para os negócios. Ele fornece recursos de segurança, incluindo MySQL Enterprise Backup, Monitor, Firewall, Auditoria, Criptografia Transparente de Dados e Autenticação, para ajudar os clientes a proteger dados e obter conformidade regulatória e do setor.

O MySQL é o banco de dados de código aberto mais popular do mundo, e é o segundo entre todos os bancos de dados, atrás apenas do Oracle Database, por um motivo. Além de ser confiável e rápido, milhares de sites e aplicações dependem do seu desempenho. Com ele, é possível manipular uma grande quantidade de dados e consultas sem diminuir a velocidade. Conta com uma grande e entusiasta comunidade de código aberto. Tudo isso, além do baixo custo e da facilidade de uso, faz do MySQL a melhor opção para muitos desenvolvedores e empresas.

---
## Perguntas frequentes sobre o MySQL

**O que é MySQL e por que é usado?**

O MySQL é o banco de dados de código aberto mais conhecido no mundo. Desenvolvedores e administradores de banco de dados usam o MySQL nas aplicações e também para armazenar, atualizar e analisar dados.

**Qual é a diferença entre SQL e MySQL?**

SQL, que significa Structured Query Language (linguagem de consulta estruturada), é uma linguagem de programação projetada para gerenciar e analisar dados armazenados em bancos de dados. O MySQL é um sistema de gerenciamento de banco de dados que recebe parte de seu nome do SQL e o usa para gerenciar dados em bancos de dados.

**Existe uma versão em nuvem do MySQL?**

O [HeatWave MySQL](https://www.oracle.com/br/mysql/) é um serviço de banco de dados totalmente gerenciado e o único serviço de nuvem desenvolvido no MySQL Enterprise Edition. Ele fornece recursos de segurança avançados para criptografia, mascaramento de dados, autenticação e um firewall de banco de dados. O HeatWave melhora o desempenho da consulta no MySQL em ordens de magnitude e permite análises em tempo real de dados transacionais no MySQL sem a complexidade, a latência, os riscos e o custo da duplicação de ETL para um banco de dados de análise separado. Disponível na OCI, na AWS e no Microsoft Azure.

**Como o MySQL se compara a outros bancos de dados?**

MySQL é um banco de dados relacional de código aberto. Isso significa que ele armazena dados em linhas e colunas e define relacionamentos entre essas linhas e colunas em esquemas. Existem outros bancos de dados relacionais populares que não são de código aberto, como o [Oracle Database](https://www.oracle.com/br/database/), bem como bancos de dados populares que não são bancos de dados relacionais. Isso inclui bancos de dados NoSQL, como MongoDB.