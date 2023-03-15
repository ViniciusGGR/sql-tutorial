# SQL Tutorial

SQL é uma linguagem padrão para armazenar, manipular e recuperar dados em bancos de dados.

SQL em: MySQL, SQL Server, MS Access, Oracle, Sybase, Informix, Postgres e outros sistemas de bancos de dados.

---

## SQL Intro

SQL é uma linguagem padrão para acessar e manipular bancos de dados.

### O que é SQL?

- SQL significa _Structured Query Language_.
- SQL permite acessar e manipular bancos de dados.
- SQL tornou-se um padrão do American National Standards Institute (ANSI) em 1986 e da International Organization for Standardization (ISO) em 1987.

### O que o SQL pode fazer?

- SQL pode executar consultas em um banco de dados.
- SQL pode recuperar dados de um banco de dados.
- SQL pode inserir registros em um banco de dados.
- SQL pode atualizar registros em um banco de dados.
- SQL pode excluir registros de um banco de dados.
- SQL pode criar novos bancos de dados.
- SQL pode criar novas tabelas em um banco de dados.
- SQL pode criar procedimentos armazenados em um banco de dados.
- SQL pode criar visualizações em um banco de dados.
- SQL pode definir permissões em tabelas, procedimentos e exibições.

### SQL é um padrão - MAS...

O SQL é um padrão ANSI/ISO, mas existem diferentes versões da linguagem SQL.

No entanto, para estar em conformidade com o padrão ANSI, todos eles suportam pelo menos os principais comandos (como ``SELECT``, ``UPDATE``, ``DELETE``, ``INSERT``, ``WHERE``) de maneira semelhante.

> **Nota**: A maioria dos programas de banco de dados SQL também possui suas próprias extensões proprietárias além do padrão SQL!

### RDBMS:

RDBMS significa _Relational Database Management System_.

O RDBMS é a base do SQL e de todos os sistemas de banco de dados modernos, como MS SQL Server, IBM DB2, Oracle, MySQL e Microsoft Access.

Os dados no RDBMS são armazenados em objetos de banco de dados chamados tabelas. Uma tabela é uma coleção de entradas de dados relacionadas e consiste em colunas e linhas.

- Tabela "Customers"/Clientes:

```
SELECT * FROM Customers;
```

Cada tabela é dividida em entidades menores chamadas campos. Um _campo é uma coluna_ em uma tabela projetada para manter informações específicas sobre cada registro na tabela. Uma **coluna é uma entidade vertical em uma tabela** que contém todas as informações associadas a um campo específico em uma tabela.

Um _registro, também chamado de linha_, é cada entrada individual que existe em uma tabela. Um **registro é uma entidade horizontal em uma tabela**.

---

## SQL Syntax

Um banco de dados geralmente contém uma ou mais tabelas. Cada tabela é identificada por um nome (por exemplo, "Customers" ou "Orders"). As tabelas contêm registros (linhas) com dados.

### Instruções SQL:

A maioria das ações executadas em um banco de dados é feita com instruções SQL. A instrução SQL a seguir seleciona todos os registros na tabela "Customers":

```
SELECT * FROM Customers;
```

### Tenha em mente que...

- As palavras-chave SQL **NÃO** diferenciam maiúsculas de minúsculas: ``select`` é o mesmo que ``SELECT``.

> **Nota**: Por convenção, todas as palavras-chave SQL normalmente são em _letras maiúsculas_.

### Ponto e vírgula após instruções SQL?

Alguns sistemas de banco de dados requerem um ponto e vírgula no final de cada instrução SQL.

O ponto e vírgula é a forma padrão de separar cada instrução SQL em sistemas de banco de dados que permitem que mais de uma instrução SQL seja executada na mesma chamada para o servidor.

> **Nota**: Por convenção, normalmente é utilizado o ponto e vírgula no final de cada instrução SQL.

### Alguns dos comandos SQL mais importantes:

- **``SELECT``** - Extrai dados de um banco de dados.
- **``UPDATE``** - Atualiza dados em um banco de dados.
- **``DELETE``** - Exclui dados de um banco de dados.
- **``INSERT INTO``** - Insere novos dados em um banco de dados.
- **``CREATE DATABASE``** - Cria um novo banco de dados.
- **``ALTER DATABASE``** - Modifica um banco de dados.
- **``CREATE TABLE``** - Cria uma nova tabela.
- **``ALTER TABLE``** - Modifica uma tabela.
- **``DROP TABLE``** - Exclui uma tabela.
- **``CREATE INDEX``** - Cria um índice (chave de pesquisa)
- **``DROP INDEX``** - Exclui um índice.

---

## SQL Select

A instrução ``SELECT`` é usada para selecionar dados de um banco de dados.

Os dados retornados são armazenados em uma tabela de resultados, chamada conjunto de resultados.

```
SELECT column1, column2, ...
FROM table_name;
```

- _column1_, _column2_ ... são os nomes dos campos da tabela da qual se deseja selecionar os dados. Caso queira selecionar todos os campos disponíveis na tabela, utilize a seguinte sintaxe:

```
SELECT * FROM table_name;
```

### Exemplo de Coluna SELECT:

A instrução SQL a seguir seleciona as colunas "CustomerName" e "City" da tabela "Customers":

```
SELECT CustomerName, City FROM Customers;
```

### SELECT * Exemplo:

A instrução SQL a seguir seleciona todas as colunas da tabela "Customers":

```
SELECT * FROM Customers;
```

---




