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

A instrução ``INSERT INTO`` é usada para inserir novos registros em uma tabela.

**INSERT INTO Sintaxe:**

É possível escrever a declaração ``INSERT INTO`` de duas maneiras.

1. Especificando os nomes das colunas e os valores a serem inseridos:
    ```
    INSERT INTO table_name (column1, column2, column3, ...)
    VALUES (value1, value2, value3, ...);
    ```

2. Adicionando valores para todas as colunas da tabela, não é preciso especificar os nomes das colunas na consulta SQL. No entanto, certifique-se de que a ordem dos valores esteja na mesma ordem das colunas da tabela. Aqui, a sintaxe do ``INSERT INTO`` seria a seguinte:
    ```
    INSERT INTO table_name
    VALUES (value1, value2, value3, ...);
    ```

### Exemplo INSERT INTO:

A instrução SQL a seguir insere um novo registro na tabela "Customers":

```
INSERT INTO Customers (CustomerName, ContactName, Address, City, PostalCode, Country)
VALUES ('Cardinal', 'Tom B. Erichsen', 'Skagen 21', 'Stavanger', '4006', 'Norway');
```

> **Nota**: Não foi inserido nenhum número no campo _CustomerID_, pois essa coluna é um campo de **auto-incremento** e será gerado automaticamente quando um novo registro for inserido na tabela.

### Inserir dados apenas nas colunas especificadas:

Também é possível inserir dados apenas em colunas específicas.

A seguinte instrução SQL irá inserir um novo registro, mas apenas inserir dados nas colunas "CustomerName", "City" e "Country" ("CustomerID" será atualizado automaticamente):

```
INSERT INTO Customers (CustomerName, City, Country)
VALUES ('Cardinal', 'Stavanger', 'Norway');
```

> **Nota**: As colunas que não foram especificadas, receberam os valores **``null``**.

---

## SQL Null Values

### O que é um valor NULL?

Um campo com valor ``NULL`` é um _campo sem valor_.

Se um campo em uma tabela for opcional, é possível inserir um novo registro ou atualizar um registro sem adicionar um valor a este campo. Em seguida, o campo será salvo com um valor ``NULL``.

> **Observação**: Um valor ``NULL`` é diferente de um valor zero ou de um campo que contém espaços. Um campo com valor ``NULL`` é aquele que foi deixado em branco durante a criação do registro.

### Como testar valores NULL?

Não é possível testar valores ``NULL`` com operadores de comparação, como =, < ou <>. Tem que usar os operadores ``IS NULL`` e ``IS NOT NULL``.

**Sintaxe IS NULL:**

```
SELECT column_names
FROM table_name
WHERE column_name IS NULL;
```

**Sintaxe IS NOT NULL:**

```
SELECT column_names
FROM table_name
WHERE column_name IS NOT NULL;
```

### O operador IS NULL:

O operador ``IS NULL`` é usada para testar valores vazios (valores ``NULL``).

O SQL a seguir lista todos os clientes com um valor ``NULL`` no campo "Address":

```
SELECT CustomerName, ContactName, Address
FROM Customers
WHERE Address IS NULL;
```

> **Dica**: Sempre utilize ``IS NULL`` para procurar valores **``NULL``**.

### O operador IS NOT NULL:

O operador ``IS NOT NULL`` é usado para testar valores não vazios (valores ``NOT NULL``).

O SQL a seguir lista todos os clientes com um valor no campo "Address":

```
SELECT CustomerName, ContactName, Address
FROM Customers
WHERE Address IS NOT NULL;
```

---

## SQL Update

A instrução ``UPDATE`` é usada para modificar os registros existentes em uma tabela.

**Sintaxe UPDATE:**

```
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;
```

> **Nota**: Tenha cuidado ao atualizar registros em uma tabela! Observe a cláusula ``WHERE`` na declaração ``UPDATE``. A cláusula ``WHERE`` especifica quais registros devem ser atualizados. Se omitido a cláusula ``WHERE``, todos os registros da tabela serão atualizados!

### Tabela UPDATE:

A instrução SQL a seguir atualiza o primeiro cliente ("CustomerID = 1") com uma nova "ContactName" e uma nova "City".

```
UPDATE Customers
SET ContactName='Alfred Schmidt', City='Frankfurt'
WHERE CustomerID = 1; 
```

### Múltiplos Registros UPDATE:

É a cláusula ``WHERE`` que determina quantos registros serão atualizados.

A instrução SQL a seguir atualizará o "ContactName" para "Juan" para todos os registros em que o "Country" é "Mexico":

```
UPDATE Customers
SET ContactName='Juan'
WHERE Country='Mexico';
```

### Aviso de UPDATE!

> **Nota**: Cuidado ao atualizar registros. Se omitido a cláusula ``WHERE``, _TODOS_ os registros serão atualizados!

```
UPDATE Customers
SET ContactName='Juan';
```

---

## SQL Delete

A instrução ``DELETE`` é usada para excluir registros existentes em uma tabela.

**Sintaxe DELETE:**

```
DELETE FROM table_name WHERE condition;
```

> **Nota**: Cuidado ao excluir registros em uma tabela! Observe a cláusula ``WHERE`` na declaração ``DELETE``. A cláusula ``WHERE`` especifica quais registros devem ser excluidos. Se omitido a cláusula ``WHERE``, todos os registros da tabela serão excluidos!

### Exemplo SQL DELETE:

A instrução SQL a seguir exclui o cliente "Alfreds Futterkiste" da tabela "Customers":

```
DELETE FROM Customers WHERE CustomerName='Alfreds Futterkiste';
```

### Excluir todos os registros:

É possível excluir todas as linhas de uma tabela sem excluir a tabela. Isso significa que a estrutura, os atributos e os índices da tabela estarão intactos:

```
DELETE FROM table_name;
```

A instrução SQL a seguir exclui todas as linhas da tabela "Customers", sem excluir a tabela:

```
DELETE FROM Customers;
```

---

## SQL Select Top

A cláusula ``SELECT TOP`` é usada para especificar o número de registros a serem retornados.

A cláusula ``SELECT TOP`` é útil em tabelas grandes com milhares de registros. Retornar um grande número de registros pode afetar o desempenho.

> **Observação**: Nem todos os sistemas de banco de dados suportam a cláusula ``SELECT TOP``. O **MySQL** suporta a cláusula ``LIMIT`` para selecionar um número limitado de registros, enquanto o Oracle usa ``FETCH FIRST n ROWS ONLY`` and ``ROWNUM``.

**Sintaxe do SQL Server | MS Access:**

```
SELECT TOP number|percent column_name(s)
FROM table_name
WHERE condition;
```

**Sintaxe do MySQL:**

```
SELECT column_name(s)
FROM table_name
WHERE condition
LIMIT number;
```

**Sintaxe do Oracle 12:**

```
SELECT column_name(s)
FROM table_name
ORDER BY column_name(s)
FETCH FIRST number ROWS ONLY;
```

**Sintaxe do Oracle mais antigo:**

```
SELECT column_name(s)
FROM table_name
WHERE ROWNUM <= number;
```

**Sintaxe Oracle mais antiga (com ORDER BY):**

```
SELECT *
FROM (SELECT column_name(s) FROM table_name ORDER BY column_name(s))
WHERE ROWNUM <= number;
```

### Exemplos SQL TOP, LIMIT e FETCH FIRST:

A instrução SQL a seguir seleciona os três primeiros registros da tabela "Customers" (para SQL Server | MS Access):

```
SELECT TOP 3 * FROM Customers;
```

A instrução SQL a seguir mostra o exemplo equivalente para MySQL:

```
SELECT * FROM Customers
LIMIT 3;
```

A instrução SQL a seguir mostra o exemplo equivalente para Oracle:

```
SELECT * FROM Customers
FETCH FIRST 3 ROWS ONLY;
```

### Exemplo SQL TOP PERCENT:

A instrução SQL a seguir seleciona os primeiros 50% dos registros da tabela "Customers" (para SQL Server | MS Access):

```
SELECT TOP 50 PERCENT * FROM Customers;
```

A instrução SQL a seguir mostra o exemplo equivalente para Oracle:

```
SELECT * FROM Customers
FETCH FIRST 50 PERCENT ROWS ONLY;
```

### Adicione uma cláusula WHERE:

A instrução SQL a seguir seleciona os três primeiros registros da tabela "Customers", onde o país é "Germany" (para SQL Server | MS Access): 

```
SELECT TOP 3 * FROM Customers
WHERE Country='Germany';
```

A instrução SQL a seguir mostra o exemplo equivalente para MySQL:

```
SELECT * FROM Customers
WHERE Country='Germany'
LIMIT 3;
```

A instrução SQL a seguir mostra o exemplo equivalente para Oracle:

```
SELECT * FROM Customers
WHERE Country='Germany'
FETCH FIRST 3 ROWS ONLY;
```

---

## SQL Min and Max

- A função ``MIN()`` retorna o menor valor da coluna selecionada.
- A função ``MAX()`` retorna o maior valor da coluna selecionada.

**Sintaxe MIN():**

```
SELECT MIN(column_name)
FROM table_name
WHERE condition;
```

**Sintaxe MAX():**

```
SELECT MAX(column_name)
FROM table_name
WHERE condition;
```

### Exemplo MIN():

A instrução SQL a seguir localiza o preço do produto mais barato:

```
SELECT MIN(Price) AS SmallestPrice
FROM Products;
```

### Exemplo MAX():

A instrução SQL a seguir encontra o preço do produto mais caro:

```
SELECT MAX(Price) AS LargestPrice
FROM Products;
```

---

## SQL Count, Avg, Sum

A função ``COUNT()`` retorna o número de linhas que correspondem a um critério especificado.

**Sintaxe COUNT():**

```
SELECT COUNT(column_name)
FROM table_name
WHERE condition;
```

A função ``AVG()`` retorna o valor médio de uma coluna numérica.

**Sintaxe AVG():**

```
SELECT AVG(column_name)
FROM table_name
WHERE condition;
```

A função ``SUM()`` retorna a soma total de uma coluna numérica.

**Sintaxe SUM():**

```
SELECT SUM(column_name)
FROM table_name
WHERE condition;
```

### Exemplo COUNT():

A instrução SQL a seguir localiza o número de produtos:

```
SELECT COUNT(ProductID)
FROM Products;
```

> **Observação**: Os valores ``NULL`` não são contados.

### Exemplo AVG():

A instrução SQL a seguir localiza o preço médio de todos os produtos:

```
SELECT AVG(Price)
FROM Products;
```

> **Observação**: Os valores ``NULL`` são ignorados.

### Exemplo SUM():

A instrução SQL a seguir localiza a soma dos campos "Quantity" na tabela "OrderDetails":

```
SELECT SUM(Quantity)
FROM OrderDetails;
```

> **Observação**: Os valores ``NULL`` são ignorados.

---

## SQL Like
