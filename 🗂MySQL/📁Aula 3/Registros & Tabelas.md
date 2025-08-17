
---
# [[03 - Criando Banco de Dados MySQL.pdf#page=10&selection=10,0,12,2|Registros]]

No contexto de um [banco de dados relacional](https://pt.wikipedia.org/wiki/Banco_de_dados_relacional "Banco de dados relacional"), um **registro** - também chamado de **linha** (do inglês **row**) - representa um único item implícito de [dados](https://pt.wikipedia.org/wiki/Dado "Dado") estruturados em uma [tabela](https://pt.wikipedia.org/wiki/Tabela "Tabela"). Em termos simples, uma tabela de banco de dados pode ser imaginada como consistindo de _linhas_ e _[colunas](https://pt.wikipedia.org/wiki/Coluna "Coluna")_ ou campos. Cada linha em uma tabela representa um conjunto de dados relacionados e toda linha na tabela possui a mesma estrutura.

Por exemplo, em uma tabela que representa companhias, cada linha representaria uma única companhia. Colunas poderiam representar coisas como o nome da companhia, endereço da companhia, se a companhia é de capital aberto, seu [número IVA](https://pt.wikipedia.org/w/index.php?title=N%C3%BAmero_IVA&action=edit&redlink=1 "Número IVA (página não existe)"), etc. Em uma tabela que representa _a associação_ de empregados com departamentos, cada linha associaria um empregado com um departamento.

Em uma utilização menos formal, por exemplo, para um banco de dados que não é formalmente relacional, um registro é equivalente a uma linha como descrita acima, mas não é usualmente referenciada como uma linha.

A estrutura implícita de uma linha, e o significado dos valores dos dados em uma linha, necessita que a linha seja compreendida como proporcionando uma sucessão de valores de dados, um em cada coluna da tabela. A linha é então interpretada como um [relvar](https://pt.wikipedia.org/w/index.php?title=Relvar&action=edit&redlink=1 "Relvar (página não existe)") composto de um conjunto de [tuplas](https://pt.wikipedia.org/wiki/Tupla "Tupla"), com cada tupla consistindo de dois itens: o nome da coluna relevante e o valor que esta linha fornece para aquela coluna.

Cada coluna espera um valor de dado de um [tipo](https://pt.wikipedia.org/wiki/Tipo_de_dado "Tipo de dado") particular. Por exemplo, uma coluna pode necessitar de um único [identificador](https://pt.wikipedia.org/wiki/Identificador "Identificador"), outra pode necessitar de texto que represente um nome de pessoa, outra pode necessitar que um inteiro represente o pagamento por hora em [centavos](https://pt.wikipedia.org/wiki/Centavos "Centavos").

---
# [[03 - Criando Banco de Dados MySQL.pdf#page=10&selection=2,5,8,7&color=yellow| Tabelas]]

Uma **tabela em banco de dados é** um tipo de modelagem de dados onde se armazena uma informação coletada por um sistema. Ou seja, são objetos ou estruturas que contêm os dados organizados em **linhas e colunas**. Cada linha representa um registro único, e cada coluna um campo dentro do registro.
## Estrutura de uma tabela em banco de dados

Agora que sabemos **o que é uma tabela em banco de dados**, vamos perguntar: Como são compostas? Toda tabela tem dois componentes básicos: o **nome do campo** e do registro:

- Campos: O campo é o **nome da coluna**. É um dado único e recebe um único tipo de dado.
- Registros: Os registros são cada uma das linhas. Aqui se armazenam ou carregam os dados que guardamos. Alguns desses dados podem ser nulos.

É importante esclarecer alguns temas operacionais. Ao registrar algum campo, temos que ter especial cuidado de que exista um campo único, atribuído a um tipo de dado específico.

Outra propriedade dos campos é a implementação de **propriedades especiais que afetam** diretamente os registros que são adicionados àquela coluna. Por fim, é importante que ao carregar uma tabela no nosso banco de dados, lhe seja atribuído um nome único e um alias, como vemos no exemplo do sistema gestor de banco de dados da SAP HANA.
## Tipos de tabelas em banco de dados

Com a resposta à pergunta **o que é uma tabela em banco de dados** bem clara, vamos revisar seus principais tipos.

### 1. Tabelas comuns

Com o **conceito de tabela de banco de dados** ainda em mente, vamos aprender seus tipos. Essas tabelas comuns são as que menos sobrecarregam um banco de dados. Servem como elo entre um arquivo e alguma tarefa específica à qual estão designados.

### 2. Tabelas largas

As tabelas largas são as que mais capacidade têm dentro de um sistema. Podem se expandir para 30.000 colunas. Uma única linha dessas tabelas pode conter 8 bytes de informação.

### 3. Tabelas do sistema

Já se perguntou como um servidor armazena informação? Isso é possível graças aos **SQL Servers**. Eles coletam os arquivos para que um determinado servidor funcione corretamente. A característica mais relevante é o acesso. Ninguém pode acessar essas tabelas, muito menos modificá-las. Somente aqueles que criaram o servidor terão acesso.

### 4. Tabelas com partições

Saber **o que é uma tabela de dados** e como operam nos facilita a compreensão de como trabalham os diferentes tipos de tabelas. A particularidade das tabelas segmentadas é que se subdividem horizontalmente a cada componente que se adiciona. Isso permite que, a cada modificação, possamos incluir dados em outro servidor ou em outro banco de dados. O MySQL permite trabalhar com partições de forma ordenada e rápida.

### 5. Tabelas temporais

A tarefa central das **tabelas temporárias** é guardar informações durante um período de tempo. Elas são armazenadas sob o nome de _tempdb_, e só estão disponíveis até que os usuários se desconectem do banco de dados ou do servidor.




