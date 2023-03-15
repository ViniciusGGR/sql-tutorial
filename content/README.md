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


