
---

## 1. Contexto inicial

- O professor reforça: **não pule etapas** → precisa entender a teoria básica antes de praticar.
    
- Público-alvo: **iniciantes** em bancos de dados (mesmo que já conheça Access, Oracle etc.).
    
- Foco: **MySQL** e a **linguagem SQL**.
    

---

## 2. Conceitos introdutórios com analogias

- **Godofredo, Dolores e Godolores** → exemplo de pessoas com características comuns:
    
    - Nome
        
    - Idade
        
    - Sexo
        
    - Peso
        
    - Altura
        
    - Nacionalidade
        

📌 **Gramática de BD**:

- Cada pessoa = **instância** (registro).
    
- As características (nome, idade etc.) = **campos** (atributos).
    
- Grupo de pessoas = **tabela**.
    
- Conjunto de tabelas = **banco de dados**.
    

### Metáfora usada:

- **Container** → tabela (agrupa instâncias de mesmo tipo).
    
- **Navio** → banco de dados (contém containers/tabelas).
    

---

## 3. Criando o primeiro banco de dados

### Comando SQL:

```sql
create database cadastro;
```

- Ambiente usado: **WAMP Server** + **MySQL Workbench**.
    
- Passos:
    
    1. Abrir o WAMP (esperar o ícone ficar **verde**).
        
    2. Abrir o **Workbench**.
        
    3. Executar o comando no editor.
        
    4. Verificar em **Schemas** se o banco foi criado.
        

---

## 4. Criando a primeira tabela

### Estrutura:

- **Tabela pessoas** → contém os campos:
    
    - nome
        
    - idade
        
    - sexo
        
    - peso
        
    - altura
        
    - nacionalidade
        

### Sintaxe:

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

📌 Observações importantes:

- Último campo **não leva vírgula**.
    
- Cada campo precisa ter um **tipo primitivo**.
    

---

## 5. Tipos primitivos no MySQL

O MySQL tem **famílias de tipos**:

1. **Numéricos**
    
    - Inteiros → `TinyInt`, `SmallInt`, `Int`, `MediumInt`, `BigInt`
        
    - Reais → `Decimal`, `Float`, `Double`
        
    - Lógicos → `Bit`, `Boolean`
        
2. **Data/Tempo**
    
    - `Date`, `DateTime`, `TimeStamp`, `Time`, `Year`
        
3. **Literais**
    
    - Caracteres → `Char`, `VarChar`
        
    - Texto → `TinyText`, `Text`, `MediumText`, `LongText`
        
    - Binário → `TinyBlob`, `Blob`, `MediumBlob`, `LongBlob`
        
    - Coleções → `Enum`, `Set`
        
4. **Espaciais (GIS)**
    
    - `Geometry`, `Point`, `Polygon`, `MultiPolygon`
        

⚡ **Regras práticas**:

- `Char(n)` = ocupa espaço fixo (sempre n caracteres).
    
- `VarChar(n)` = ocupa apenas o espaço necessário até n.
    
- Use **TinyInt** para idades (economiza memória).
    
- **Blob** pode guardar imagens, mas não é recomendado.
    

---

## 6. Gramática aplicada (para TI + inglês técnico)

- **Nouns (Substantivos de TI)**:
    
    - database, table, record, field, schema, server, query, command, instance, container.
        
- **Verbs (Ações em BD/SQL)**:
    
    - create, execute, open, store, save, update, group, separate, organize.
        
- **Adjectives (Adjetivos usados em TI)**:
    
    - relational, primitive, logical, numeric, textual, optional, fixed, variable.
        

📌 Em SQL, **os verbos viram comandos** → `CREATE`, `SELECT`, `INSERT`, `UPDATE`, `DELETE`.

---

# 🎯 Resumo Final

- Banco de dados = **navio**.
    
- Tabelas = **containers**.
    
- Registros = **pessoas (instâncias)**.
    
- Campos = **características**.
    
- Primeiro comando aprendido:
    
    - Criar banco → `create database nome;`
        
    - Criar tabela → `create table nome (...)`
        
- Tipos primitivos → escolha correta garante **eficiência**.
    
