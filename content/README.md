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

## SQL Select Distinct

A instrução ``SELECT DISTINCT`` é usada para retornar apenas valores distintos (diferentes).

Dentro de uma tabela, uma coluna geralmente contém muitos valores duplicados, e às vezes você deseja apenas listar os valores diferentes (distintos).

```
SELECT DISTINCT column1, column2, ...
FROM table_name;
```

### Exemplo de SELECT sem DISTINCT:

A instrução SQL a seguir seleciona todos os valores (incluindo os duplicados) da coluna "Country" na tabela "Customers":

```
SELECT Country FROM Customers;
```

### Exemplos de SELECT DISTINCT:

A instrução SQL a seguir seleciona apenas os valores DISTINCT da coluna "Country" na tabela "Customers":

```
SELECT DISTINCT Country FROM Customers;
```

A instrução SQL a seguir lista o número de "Country" diferentes (distintos) na tabela "Customers":

```
SELECT COUNT(DISTINCT Country) FROM Customers;
```

---

## SQL Where

A cláusula ``WHERE`` é usada para filtrar registros. Ele é usado para extrair apenas os registros que atendem a uma condição especificada.

```
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```

> **Nota**: A cláusula ``WHERE`` não é usada apenas em declarações ``SELECT``, ela também é usada em ``UPDATE``, ``DELETE``, etc.

### Exemplo de Cláusula WHERE:

A instrução SQL a seguir seleciona todos os cliente do país "Mexico", na tabela "Customers":

```
SELECT * FROM Customers
WHERE Country='Mexico';
```

### Campos de Texto vs. Campos Numéricos:

SQL requer aspas simples em torno de valores de texto (a maioria dos sistemas de banco de dados também permite aspas duplas).

No entanto, os **_campos numéricos não devem ser colocados entre aspas_**:

```
SELECT * FROM Customers
WHERE CustomerID=1;
```

### Operadores na cláusula WHERE:

Os seguintes operadores podem ser usados na cláusula ``WHERE``:

| Operadores | Descrição                                                  |
| ---------- | ---------------------------------------------------------- |
| =          | Igual.                                                     |
| >          | Maior que.                                                 |
| <          | Menor que.                                                 |
| >=         | Maior ou igual.                                            |
| <=         | Menor ou igual.                                            |
| <>         | Não igual.                                                 |
| BETWEEN    | Entre um determinado intervalo.                            |
| LIKE       | Pesquisar um padrão.                                       |
| IN         | Para especificar vários valores possíveis para uma coluna. |

> **Nota**: Em algumas versões do SQL, o operador **Não igual (<>)** pode ser escrito como **!=**.

---

## SQL And, Or, Not

A cláusula ``WHERE`` pode ser combinada com os operadores ``AND``, ``OR`` e ``NOT``.

Os operadores ``AND`` e ``OR`` são usados para filtrar registros com base em mais de uma condição:

- O operador ``AND`` exibe um registro se todas as condições separadas por ``AND`` forem **TRUE**.
- O operador ``OR`` exibe um registro se alguma das condições separadas por ``OR`` for **TRUE**.

O operador ``NOT`` exibe um registro se a(s) condição(ões) NÃO FOR(EM) VERDADEIRA(S).

**Sintaxe AND**:

```
SELECT column1, column2, ...
FROM table_name
WHERE condition1 AND condition2 AND condition3 ...;
```

**Sintaxe OR**:

```
SELECT column1, column2, ...
FROM table_name
WHERE condition1 OR condition2 OR condition3 ...;
```

**Sintaxe NOT**:

```
SELECT column1, column2, ...
FROM table_name
WHERE NOT condition;
```

### Exemplo AND:

A instrução SQL a seguir seleciona todos os campos de "Customers" em que o país é "Germany" AND (**E**) a cidade é "Berlin":

```
SELECT * FROM Customers
WHERE Country='Germany' AND City='Berlin';
```

### Exemplo OR:

A instrução SQL a seguir seleciona todos os campos de "Customers" onde a cidade é "Berlin" OR (**OU**) "München":

```
SELECT * FROM Customers
WHERE City='Berlin' OR City='München';
```

A instrução SQL a seguir seleciona todos os campos de "Customers" onde o país é "Germany" OR (**OU**) "Spain":

```
SELECT * FROM Customers
WHERE Country='Germany' OR Country='Spain';
```

### Exemplo NOT:

A instrução SQL a seguir seleciona todos os campos de "Customers" onde o país NÃO é "Germany":

```
SELECT * FROM Customers
WHERE NOT Country='Germany';
```

### Combinando AND, OR e NOT:

Também é possível combinar os operadores ``AND``, ``OR`` e ``NOT``.

A instrução SQL a seguir seleciona todos os campos de "Customers" onde o país é "Germany" AND (**E**) a cidade deve ser "Berlin" OR (**OU**) "München" (usando parênteses para formar expressões complexas):

```
SELECT * FROM Customers
WHERE Country='Germany' AND (City='Berlin' OR City='München');
```

A instrução SQL a seguir seleciona todos os campos de "Customers" onde o país NOT (**NÃO**) é "Germany" e NOT (**NÃO**) "USA":

```
SELECT * FROM Customers
WHERE NOT Country='Germany' AND NOT Country='USA';
```

---

## SQL Order By

A palavra-chave ``ORDER BY`` é usada para classificar o conjunto de resultados em ordem crescente ou decrescente.

A palavra-chave ``ORDER BY`` _classifica os registros em ordem crescente por padrão_. Para classificar os registros em ordem decrescente, basta utilizar a palavra-chave ``DESC``.

```
SELECT column1, column2, ...
FROM table_name
ORDER BY column1, column2, ... ASC|DESC;
```

### Exemplo ORDER BY:

A instrução SQL a seguir seleciona todos os clientes da tabela "Customers", classificados pela coluna "Country":

```
SELECT * FROM Customers
ORDER BY Country;
```

### Exemplo ORDER BY DESC:

A instrução SQL a seguir seleciona todos os clientes da tabela "Customers", classificados em ordem DECRESCENTE pela coluna "Country":

```
SELECT * FROM Customers
ORDER BY Country DESC;
```

### Exemplo ORDER BY Várias Colunas:

A instrução SQL a seguir seleciona todos os clientes da tabela "Customers", classificados pela coluna "Country" e "CustomerName". Isso significa que ele ordena por país, mas se algumas linhas tiverem o mesmo "Country", ele as ordena por "CustomerName":

```
SELECT * FROM Customers
ORDER BY Country, CustomerName;
```

A instrução SQL a seguir seleciona todos os clientes da tabela "Customers", classificados em ordem crescente pelo "Country" e decrescente pela coluna "CustomerName":

```
SELECT * FROM Customers
ORDER BY Country ASC, CustomerName DESC;
```

---

## SQL Insert Into


