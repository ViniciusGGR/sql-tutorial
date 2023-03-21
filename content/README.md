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

O operador ``LIKE`` é usado em uma cláusula ``WHERE`` para pesquisar um padrão especificado em uma coluna.

Existem dois curingas frequentemente usados em conjunto com o operador ``LIKE``:
- O _sinal de porcentagem_ (%) representa zero, um ou vários caracteres.
- O _sinal de sublinhado_ (_) representa um único caractere.

> **Observação**: O MS Access usa um asterisco (*) em vez do sinal de porcentagem (%) e um ponto de interrogação (?) em vez do sublinhado (_).

O sinal de porcentagem (%) e o sublinhado (_) também podem ser usados em combinações!

**Sintaxe LIKE:**

```
SELECT column1, column2, ...
FROM table_name
WHERE columnN LIKE pattern;
```

> **Dica**: Também é possível combinar qualquer número de condições usando operadores ``AND`` ou ``OR``.

Alguns exemplos mostrando diferentes operadores ``LIKE`` com curingas '%' e '_':

| Operador LIKE                  | Descrição
| ------------------------------ | ----------------
| WHERE CustomerName LIKE 'a%'   | Encontra todos os valores que começam com "a".
| WHERE CustomerName LIKE '%a'   | Encontra todos os valores que terminam com "a".
| WHERE CustomerName LIKE '%or%' | Localiza quaisquer valores que tenham "or" em qualquer posição.
| WHERE CustomerName LIKE '_r%'  | Localiza quaisquer valores que tenham "r" na segunda posição.
| WHERE CustomerName LIKE 'a_%'  | Localiza todos os valores que começam com "a" e têm pelo menos 2 caracteres de comprimento.
| WHERE CustomerName LIKE 'a__%' | Localiza todos os valores que começam com "a" e têm pelo menos 3 caracteres de comprimento.
| WHERE CustomerName LIKE 'a%o'  | Encontra todos os valores que começam com "a" e terminam com "o".

### Exemplos de SQL LIKE:

- A instrução SQL a seguir seleciona todos os clientes com um _CustomerName_ começando com "a":
    ```
    SELECT * FROM Customers
    WHERE CustomerName LIKE 'a%';
    ```

- A instrução SQL a seguir seleciona todos os clientes com um _CustomerName_ terminando com "a":
    ```
    SELECT * FROM Customers
    WHERE CustomerName LIKE '%a';
    ```

- A instrução SQL a seguir seleciona todos os clientes com um _CustomerName_ que tenham "or" em qualquer posição:
    ```
    SELECT * FROM Customers
    WHERE CustomerName LIKE '%or%';
    ```

- A instrução SQL a seguir seleciona todos os clientes com um _CustomerName_ que tenha "r" na segunda posição:
    ```
    SELECT * FROM Customers
    WHERE CustomerName LIKE '_r%';
    ```

- A instrução SQL a seguir seleciona todos os clientes com um _CustomerName_ que começa com "a" e tem pelo menos 3 caracteres:
    ```
    SELECT * FROM Customers
    WHERE CustomerName LIKE 'a__%';
    ```

- A instrução SQL a seguir seleciona todos os clientes com um _CustomerName_ que começa com "a" e termina com "o":
    ```
    SELECT * FROM Customers
    WHERE CustomerName LIKE 'a%o';
    ```

- A instrução SQL a seguir seleciona todos os clientes com um _CustomerName_ que **NÃO** começa com "a":
    ```
    SELECT * FROM Customers
    WHERE CustomerName NOT LIKE 'a%';
    ```

---

## SQL Wildcards

Um _caractere curinga_ é usado para substituir um ou mais caracteres em uma string.

Os _caracteres curinga_ são usados com o operador ``LIKE``. O operador ``LIKE`` é usado em uma cláusula ``WHERE`` para pesquisar um padrão especificado em uma coluna.

**_Caracteres curinga_ no MS Access:**

``*`` - Representa zero ou mais caracteres. - ``bl*`` localiza _black_, _blue_ e _blob_.  
``?`` - Representa um único caractere. - ``h?t`` localiza _hot_, _hat_ e _hit_.  
``[]`` - Representa qualquer caractere único dentro dos colchetes. - ``h[oa]t`` localiza _hot_ e _hat_, mas não _hit_.  
``!`` - Representa qualquer caractere que não esteja entre colchetes. - ``h[!oa]t`` localiza _hit_, mas não _hot_ e _hat_.  
``-`` - Representa qualquer caractere único dentro do intervalo especificado. - ``c[a-b]t`` localiza _cat_ e _cbt_.  
``#`` - Representa qualquer caractere numérico único. - ``2#5`` localiza 205, 215, 225, 235, 245, 255, 265, 275, 285 e 295.  

**_Caracteres curinga_ no SQL Server:**

``%`` - Representa zero ou mais caracteres. - ``bl%`` localiza _black_, _blue_ e _blob_.  
``_`` - Representa um único caractere. - ``h_t`` localiza _hot_, _hat_ e _hit_.  
``[]`` - Representa qualquer caractere único dentro dos colchetes. - ``h[oa]t`` localiza _hot_ e _hat_, mas não _hit_.  
``^`` - Representa qualquer caractere que não esteja entre colchetes. - ``h[^oa]t`` localiza _hit_, mas não _hot_ e _hat_.  
``-`` - Representa qualquer caractere único dentro do intervalo especificado. - ``c[a-b]t`` localiza _cat_ e _cbt_.  

Todos os _curingas_ também podem ser usados em combinações!

- Alguns exemplos mostrando diferentes operadores ``LIKE`` com curingas '%' e '_':

| Operador LIKE                  | Descrição
| ------------------------------ | -----------------
| WHERE CustomerName LIKE 'a%'   | Encontra todos os valores que começam com "a".
| WHERE CustomerName LIKE '%a'   | Encontra todos os valores que terminam com "a".
| WHERE CustomerName LIKE '%or%' | Localiza quaisquer valores que tenham "or" em qualquer posição.
| WHERE CustomerName LIKE '_r%'  | Localiza quaisquer valores que tenham "r" na segunda posição.
| WHERE CustomerName LIKE 'a__%' | Encontra todos os valores que começam com "a" e têm pelo menos 3 caracteres de comprimento.
| WHERE CustomerName LIKE 'a%o'  | Encontra todos os valores que começam com "a" e terminam com "o".

### Usando o curinga %:

- A instrução SQL a seguir seleciona todos os clientes com uma cidade começando com "ber":
    ```
    SELECT * FROM Customers
    WHERE City LIKE 'ber%';
    ```

- A instrução SQL a seguir seleciona todos os clientes com uma cidade contendo o padrão "es":
    ```
    SELECT * FROM Customers
    WHERE City LIKE '%es%';
    ```

### Usando o curinga _:

- A instrução SQL a seguir seleciona todos os clientes com uma cidade começando com qualquer caractere, seguido de "ondon":
    ```
    SELECT * FROM Customers
    WHERE City LIKE '_ondon';
    ```

- A instrução SQL a seguir seleciona todos os clientes com uma cidade começando com "L", seguido de qualquer caractere, seguido de "n", seguido de qualquer caractere, seguido de "on":
    ```
    SELECT * FROM Customers
    WHERE City LIKE 'L_n_on';
    ```

### Usando o curinga [charlist]:

- A instrução SQL a seguir seleciona todos os clientes com uma cidade começando com "b", "s" ou "p":
    ```
    SELECT * FROM Customers
    WHERE City LIKE '[bsp]%';
    ```

- A instrução SQL a seguir seleciona todos os clientes com uma cidade começando com "a", "b" ou "c":
    ```
    SELECT * FROM Customers
    WHERE City LIKE '[a-c]%';
    ```

### Usando o curinga [!charlist]:

- As duas instruções SQL a seguir selecionam todos os clientes com uma cidade **NÃO** começando com "b", "s" ou "p":
    ```
    SELECT * FROM Customers
    WHERE City LIKE '[!bsp]%';
    ```

    ```
    SELECT * FROM Customers
    WHERE City NOT LIKE '[bsp]%';
    ```

---

## SQL In

O operador ``IN`` permite especificar vários valores em uma cláusula ``WHERE``. O operador ``IN`` é um atalho para várias condições ``OR``.

**Sintaxe IN:**

```
SELECT column_name(s)
FROM table_name
WHERE column_name IN (value1, value2, ...);
```

```
SELECT column_name(s)
FROM table_name
WHERE column_name IN (SELECT STATEMENT);
```

### Exemplos do Operador IN:

- A instrução SQL a seguir seleciona todos os clientes localizados nos países "Germany", "France" ou "UK":
    ```
    SELECT * FROM Customers
    WHERE Country IN ('Germany', 'France', 'UK');
    ```

- A instrução SQL a seguir seleciona todos os clientes que **NÃO** estão localizados nos países "Germany", "France" ou "UK":
    ```
    SELECT * FROM Customers
    WHERE Country NOT IN ('Germany', 'France', 'UK');
    ```

- A instrução SQL a seguir seleciona todos os clientes que são dos mesmos  países que os fornecedores:
    ```
    SELECT * FROM Customers
    WHERE Country IN (SELECT Country FROM Suppliers);
    ```

---

## SQL Between

O operador ``BETWEEN`` seleciona valores dentro de um determinado intervalo. Os valores podem ser números, texto ou datas. O operador ``BETWEEN`` é _inclusivo_: os valores inicial e final são incluídos.

**Sintaxe BETWEEN:**

```
SELECT column_name(s)
FROM table_name
WHERE column_name BETWEEN value1 AND value2;
```

### Exemplo BETWEEN:

- A instrução SQL a seguir seleciona todos os produtos com preço **entre** 10 e 20:
    ```
    SELECT * FROM Products
    WHERE Price BETWEEN 10 AND 20;
    ```

### Exemplo NOT BETWEEN:

- Para exibir os produtos fora do intervalo do exemplo anterior, utilize ``NOT BETWEEN``:
    ```
    SELECT * FROM Products
    WHERE Price NOT BETWEEN 10 AND 20;
    ```

### Exemplo BETWEEN com IN:

- A instrução SQL a seguir seleciona todos os produtos com preço **entre** 10 e 20. Além disso, não mostre produtos com um "CategoryID" de 1, 2 ou 3:
    ```
    SELECT * FROM Products
    WHERE Price BETWEEN 10 AND 20
    AND CategoryID NOT IN (1,2,3);
    ```

### Exemplo BETWEEN com Valores Textuais:

- A instrução SQL a seguir seleciona todos os produtos com um "ProductName" **entre** _Carnarvon Tigers_ e _Mozzarella di Giovanni_:
    ```
    SELECT * FROM Products
    WHERE ProductName BETWEEN 'Carnarvon Tigers' AND 'Mozzarella di Giovanni'
    ORDER BY ProductName;
    ```

- A instrução SQL a seguir seleciona todos os produtos com um "ProductName" **entre** _Carnarvon Tigers_ e _Chef Anton's Cajun Seasoning_:
    ```
    SELECT * FROM Products
    WHERE ProductName BETWEEN "Carnarvon Tigers" AND "Chef Anton's Cajun Seasoning"
    ORDER BY ProductName;
    ```

### Exemplo NOT BETWEEN com Valores Textuais:

- A instrução SQL a seguir seleciona todos os produtos com um "ProductName" **não entre** _Carnarvon Tigers_ e _Mozzarella di Giovanni_:
    ```
    SELECT * FROM Products
    WHERE ProductName NOT BETWEEN 'Carnarvon Tigers' AND 'Mozzarella di Giovanni'
    ORDER BY ProductName;
    ```

### Exemplo BETWEEN com Datas:

- A instrução SQL a seguir seleciona todos os pedidos com OrderDate **entre** '01-July-1996' e '31-July-1996':
    ```
    SELECT * FROM Orders
    WHERE OrderDate BETWEEN #07/01/1996# AND #07/31/1996#;
    ```

    ```
    SELECT * FROM Orders
    WHERE OrderDate BETWEEN '1996-07-01' AND '1996-07-31';
    ```

---

## SQL Aliases

**SQL Aliases** são usados para dar a uma tabela, ou uma coluna em uma tabela, um nome temporário.

Os **Aliases** costumam ser usados para tornar os nomes das colunas mais legíveis.

- Um **alias** só existe durante essa consulta em específico.
- Um **alias** é criado com a palavra-chave ``AS``.

**Sintaxe da Coluna Alias:**

```
SELECT column_name AS alias_name
FROM table_name;
```

**Sintaxe da Tabela Alias:**

```
SELECT column_name(s)
FROM table_name AS alias_name;
```

### Exemplos de Colunas com Alias:

- A instrução SQL a seguir cria dois **aliases**, um para a coluna "CustomerID" e outro para a coluna "CustomerName":
    ```
    SELECT CustomerID AS ID, CustomerName AS Customer
    FROM Customers;
    ```

- A instrução SQL a seguir cria dois **aliases**, um para a coluna "CustomerName" e outro para a coluna "ContactName". **Observação**: Requer _aspas duplas_ ou _colchetes_ se o nome do **alias** contiver espaços:
    ```
    SELECT CustomerName AS Customer, ContactName AS [Contact Person]
    FROM Customers;
    ```

- A instrução SQL a seguir cria um **alias** denominado "Address" que combina quatro colunas (Address, PostalCode, City e Country):
    ```
    SELECT CustomerName, Address + ', ' + PostalCode + ' ' + City + ', ' + Country AS Address
    FROM Customers;
    ```

    > **Observação**: Para que a instrução SQL acima funcione no _MySQL_, use o seguinte:

    ```
    SELECT CustomerName, CONCAT(Address,', ',PostalCode,', ',City,', ',Country) AS Address
    FROM Customers;
    ```

    > **Observação**: Para que a instrução SQL acima funcione no _Oracle_, use o seguinte:

    ```
    SELECT CustomerName, (Address || ', ' || PostalCode || ' ' || City || ', ' || Country) AS Address
    FROM Customers;
    ```

### Exemplos de Tabelas com Alias:

- A instrução SQL a seguir seleciona todos os pedidos do cliente com "CustomerID=4" (_Around the Horn_). Foi utilizado as tabelas "Customers" e "Orders" e foi dado a elas os **aliases** de "c" e "o" respectivamente (os **aliases** foram utilizados para tornar o SQL mais curto):
    ```
    SELECT o.OrderID, o.OrderDate, c.CustomerName
    FROM Customers AS c, Orders AS o
    WHERE c.CustomerName='Around the Horn' AND c.CustomerID=o.CustomerID;
    ```

- A instrução SQL a seguir é igual à anterior, mas sem **aliases**:
    ```
    SELECT Orders.OrderID, Orders.OrderDate, Customers.CustomerName
    FROM Customers, Orders
    WHERE Customers.CustomerName='Around the Horn' AND Customers.CustomerID=Orders.CustomerID;
    ```

**Aliases** podem ser úteis quando:
- Há mais de uma tabela envolvida em uma consulta.
- As funções são usadas na consulta.
- Os nomes das colunas são grandes ou não muito legíveis.
- Duas ou mais colunas são combinadas.

---

## SQL Joins

Uma cláusula ``JOIN`` é usada para combinar linhas de duas ou mais tabelas, com base em uma coluna relacionada entre elas.

Duas tabelas, sendo uma "Orders" e outra "Customers", onde a coluna "CustomerID" na tabela "Orders" se refere ao "CustomerID" na tabela "Customers". Portanto, a relação entre as duas tabelas acima é a coluna "CustomerID".

Com isso, é possível criar a seguinte instrução SQL (que contém um ``INNER JOIN``), que seleciona os registros que possuem valores correspondentes em ambas as tabelas.

```
SELECT Orders.OrderID, Customers.CustomerName, Orders.OrderDate
FROM Orders
INNER JOIN Customers ON Orders.CustomerID=Customers.CustomerID;
```

### Diferentes tipos de SQL JOINs:

Diferentes tipos de ``JOIN(s)`` no SQL:
- ``(INNER) JOIN``: Retorna registros que possuem valores correspondentes em ambas as tabelas.
- ``LEFT (OUTER) JOIN``: Retorna todos os registros da tabela da esquerda e os registros correspondentes da tabela da direita.
- ``RIGHT (OUTER) JOIN``: Retorna todos os registros da tabela da direita e os registros correspondentes da tabela da esquerda.
- ``FULL (OUTER) JOIN``: Retorna todos os registros quando há uma correspondência na tabela esquerda ou direita.

---

## SQL Inner Join

A palavra-chave ``INNER JOIN`` seleciona registros que possuem valores correspondentes em ambas as tabelas.

**Sintaxe do INNER JOIN:**

```
SELECT column_name(s)
FROM table1
INNER JOIN table2 ON table1.column_name = table2.column_name;
```

### Exemplo SQL INNER JOIN:

- A instrução SQL a seguir seleciona todos os pedidos com informações do cliente:
    ```
    SELECT Orders.OrderID, Customers.CustomerName
    FROM Orders
    INNER JOIN Customers ON Orders.CustomerID = Customers.CustomerID;
    ```

    > **Observação**: A palavra-chave ``INNER JOIN`` seleciona todas as linhas de ambas as tabelas, desde que haja uma correspondência entre as colunas. Caso existam registros na tabela "Orders" que não possuam correspondências em "Customers", estes pedidos não serão mostrados!

### JOIN Três Tabelas:

- A instrução SQL a seguir seleciona todos os pedidos com informações do cliente e do remetente:
    ```
    SELECT Orders.OrderID, Customers.CustomerName, Shippers.ShipperName
    FROM ((Orders
    INNER JOIN Customers ON Orders.CustomerID = Customers.CustomerID)
    INNER JOIN Shippers ON Orders.ShipperID = Shippers.ShipperID);
    ```

---

## SQL Left Join

A palavra-chave ``LEFT JOIN`` retorna todos os registros da tabela à esquerda e os registros correspondentes da tabela à direita. O resultado é _0 registros_ do lado direito, se não houver correspondência.

**Sintaxe LEFT JOIN:**

```
SELECT column_name(s)
FROM table1
LEFT JOIN table2 ON table1.column_name = table2.column_name;
```

> **Nota**: Em alguns bancos de dados, ``LEFT JOIN`` é chamado de ``LEFT OUTER JOIN``.

### Exemplo SQL LEFT JOIN:

- A instrução SQL a seguir selecionará todos os clientes e quaisquer pedidos que eles possam ter:
    ```
    SELECT Customers.CustomerName, Orders.OrderID
    FROM Customers
    LEFT JOIN Orders ON Customers.CustomerID = Orders.CustomerID
    ORDER BY Customers.CustomerName;
    ```

    > **Nota**: A palavra-chave ``LEFT JOIN`` retorna todos os registros da tabela da esquerda (Customers), mesmo que não haja correspondências na tabela da direita (Orders).

---

## SQL Right Join

A palavra-chave ``RIGHT JOIN`` retorna todos os registros da tabela à direita e os registros correspondentes da tabela à esquerda. O resultado é _0 registros_ do lado esquerdo, se não houver correspondência.

**Sintaxe RIGHT JOIN:**

```
SELECT column_name(s)
FROM table1
RIGHT JOIN table2 ON table1.column_name = table2.column_name;
```

> **Nota**: Em alguns bancos de dados ``RIGHT JOIN`` é chamado de ``RIGHT OUTER JOIN``.

### Exemplo SQL RIGHT JOIN:

- A instrução SQL a seguir retornará todos os funcionários e quaisquer pedidos que eles possam ter feito:
    ```
    SELECT Orders.OrderID, Employees.LastName, Employees.FirstName
    FROM Orders
    RIGHT JOIN Employees ON Orders.EmployeeID = Employees.EmployeeID
    ORDER BY Orders.OrderID;
    ```

    > **Nota**: A palavra-chave ``RIGHT JOIN`` retorna todos os registros da tabela da direita (Employees), mesmo que não haja correspondências na tabela da esquerda (Orders).

---

## SQL Full Join

A palavra-chave ``FULL OUTER JOIN`` retorna todos os registros quando há uma correspondência nos registros da tabela à esquerda ou à direita.

> **Dica**: ``FULL OUTER JOIN`` e ``FULL JOIN`` são iguais.

**Sintaxe FULL OUTER JOIN:**

```
SELECT column_name(s)
FROM table1
FULL OUTER JOIN table2 ON table1.column_name = table2.column_name
WHERE condition;
```

> **Nota**: ``FULL OUTER JOIN`` pode _potencialmente_ retornar conjuntos de resultados muito grandes!

### Exemplo SQL FULL OUTER JOIN:

- A instrução SQL a seguir seleciona todos os clientes e todos os pedidos:
    ```
    SELECT Customers.CustomerName, Orders.OrderID
    FROM Customers
    FULL OUTER JOIN Orders ON Customers.CustomerID = Orders.CustomerID
    ORDER BY Customers.CustomerName;
    ```

    > **Observação**: A palavra-chave ``FULL OUTER JOIN`` retorna todos os registros correspondentes de ambas as tabelas, independentemente de a outra tabela corresponder ou não. Portanto, se houver linhas em "Customers" que não correspondam a "Orders" ou se houver linhas em "Orders" que não correspondam a "Customers", essas linhas também serão listadas.

---

## SQL Self Join

Uma self join (junção automática) é uma _junção regular_, mas a tabela é unida a si mesma.

**Sintaxe Self Join:**

```
SELECT column_name(s)
FROM table1 T1, table1 T2
WHERE condition;
```

_T1_ e _T2_ são **aliases** de tabela diferentes para a mesma tabela.

### Exemplo SQL Self Join:

- A instrução SQL a seguir corresponde a clientes da mesma cidade:
    ```
    SELECT A.CustomerName AS CustomerName1, B.CustomerName AS CustomerName2, A.City
    FROM Customers A, Customers B
    WHERE A.CustomerID <> B.CustomerID AND A.City = B.City
    ORDER BY A.City;
    ```

---

## SQL Union

O operador ``UNION`` é usado para combinar o conjunto de resultados de duas ou mais instruções ``SELECT``.
- Cada instrução ``SELECT`` dentro de ``UNION`` deve ter o mesmo número de colunas.
- As colunas também devem ter tipos de dados semelhantes.
- As colunas em cada instrução ``SELECT`` também devem estar na mesma ordem.

**Sintaxe UNION:**

```
SELECT column_name(s) FROM table1
UNION
SELECT column_name(s) FROM table2;
```

**Sintaxe UNION ALL:**

O operador ``UNION`` seleciona apenas valores distintos por padrão. Para permitir valores duplicados, use ``UNION ALL``:

```
SELECT column_name(s) FROM table1
UNION ALL
SELECT column_name(s) FROM table2;
```

> **Observação**: Os nomes das colunas no conjunto de resultados geralmente são iguais aos nomes das colunas na primeira instrução ``SELECT``.

### Exemplo SQL UNION:

- A instrução SQL a seguir retorna as cidades (_somente valores distintos_) das tabelas "Customers" e "Suppliers":
    ```
    SELECT City FROM Customers
    UNION
    SELECT City FROM Suppliers
    ORDER BY City;
    ```

    > **Observação**: Caso alguns clientes ou fornecedores tenham a mesma cidade, cada cidade será listada apenas uma vez, pois ``UNION`` seleciona apenas valores distintos. Use ``UNION ALL`` também para selecionar valores duplicados!

### Exemplo SQL UNION ALL:

- A instrução SQL a seguir retorna as cidades (_valores duplicados também_) das tabelas "Customers" e "Suppliers":
    ```
    SELECT City FROM Customers
    UNION ALL
    SELECT City FROM Suppliers
    ORDER BY City;
    ```

### SQL UNION com WHERE:

- A instrução SQL a seguir retorna as cidades alemãs (_somente valores distintos_) das tabelas "Customers" e "Suppliers":
    ```
    SELECT City, Country FROM Customers
    WHERE Country='Germany'
    UNION
    SELECT City, Country FROM Suppliers
    WHERE Country='Germany'
    ORDER BY City;
    ```

### SQL UNION ALL com WHERE:

- A instrução SQL a seguir retorna as cidades alemãs (_valores duplicados também_) das tabelas "Customers" e "Suppliers":
    ```
    SELECT City, Country FROM Customers
    WHERE Country='Germany'
    UNION ALL
    SELECT City, Country FROM Suppliers
    WHERE Country='Germany'
    ORDER BY City;
    ```

### Outro exemplo UNION:

- A instrução SQL a seguir lista todos os clientes e fornecedores:
    ```
    SELECT 'Customer' AS Type, ContactName, City, Country
    FROM Customers
    UNION
    SELECT 'Supplier', ContactName, City, Country
    FROM Suppliers;
    ```

    > **Observação**: O tipo ``AS`` acima é um **alias**. _SQL Aliases_ são usados para dar um nome temporário a uma tabela ou coluna. Um **alias** só existe durante a consulta. Portanto, nesse exemplo foi _criada uma coluna temporária chamada_ **"Type"**, que lista se a pessoa de contato é um "Customer" ou um "Supplier".

---

## SQL Group By

A instrução ``GROUP BY`` agrupa linhas que têm os mesmos valores em linhas de resumo, como "encontre o número de clientes em cada país".

A instrução ``GROUP BY`` geralmente é usada com funções de agregação (``COUNT()``, ``MAX()``, ``MIN()``, ``SUM()``, ``AVG()``) para agrupar o conjunto de resultados em uma ou mais colunas.

**Sintaxe GROUP BY:**

```
SELECT column_name(s)
FROM table_name
WHERE condition
GROUP BY column_name(s)
ORDER BY column_name(s);
```

### Exemplos SQL GROUP BY:

- A instrução SQL a seguir lista o número de clientes em cada país:
    ```
    SELECT COUNT(CustomerID), Country
    FROM Customers
    GROUP BY Country;
    ```

- A instrução SQL a seguir lista o número de clientes em cada país, classificados de cima para baixo:
    ```
    SELECT COUNT(CustomerID), Country
    FROM Customers
    GROUP BY Country
    ORDER BY COUNT(CustomerID) DESC;
    ```

### Exemplo GROUP BY com JOIN:

- A instrução SQL a seguir lista o número de pedidos enviados por cada remetente:
    ```
    SELECT Shippers.ShipperName, COUNT(Orders.OrderID) AS NumberOfOrders FROM Orders
    LEFT JOIN Shippers ON Orders.ShipperID = Shippers.ShipperID
    GROUP BY ShipperName;
    ```

---

## SQL Having

A cláusula ``HAVING`` foi adicionada ao SQL porque a palavra-chave ``WHERE`` não pode ser usada com funções agregadas.

**Sintaxe HAVING:**

```
SELECT column_name(s)
FROM table_name
WHERE condition
GROUP BY column_name(s)
HAVING condition
ORDER BY column_name(s);
```

### Exemplos SQL HAVING:

- A instrução SQL a seguir lista o número de clientes em cada país. Inclui apenas países com mais de 5 clientes:
    ```
    SELECT COUNT(CustomerID), Country
    FROM Customers
    GROUP BY Country
    HAVING COUNT(CustomerID) > 5;
    ```

- A instrução SQL a seguir lista o número de clientes em cada país, classificados de cima para baixo. Inclui apenas países com mais de 5 clientes:
    ```
    SELECT COUNT(CustomerID), Country
    FROM Customers
    GROUP BY Country
    HAVING COUNT(CustomerID) > 5
    ORDER BY COUNT(CustomerID) DESC;
    ```

### Mais exemplos de HAVING:

- A instrução SQL a seguir lista os funcionários que registraram mais de 10 pedidos:
    ```
    SELECT Employees.LastName, COUNT(Orders.OrderID) AS NumberOfOrders
    FROM (Orders
    INNER JOIN Employees ON Orders.EmployeeID = Employees.EmployeeID)
    GROUP BY LastName
    HAVING COUNT(Orders.OrderID) > 10;
    ```

- A instrução SQL a seguir lista se os funcionários "Davolio" ou "Fuller" registraram mais de 25 pedidos:
    ```
    SELECT Employees.LastName, COUNT(Orders.OrderID) AS NumberOfOrders
    FROM Orders
    INNER JOIN Employees ON Orders.EmployeeID = Employees.EmployeeID
    WHERE LastName = 'Davolio' OR LastName = 'Fuller'
    GROUP BY LastName
    HAVING COUNT(Orders.OrderID) > 25;
    ```

---

## SQL Exists

O operador ``EXISTS`` é usado para testar a existência de qualquer registro em uma subconsulta.

O operador ``EXISTS`` retorna **TRUE** se a subconsulta retornar um ou mais registros.

**Sintaxe EXISTS:**

```
SELECT column_name(s)
FROM table_name
WHERE EXISTS (SELECT column_name FROM table_name WHERE condition);
```

### Exemplos SQL EXISTS:

- A instrução SQL a seguir retorna **TRUE** e lista os fornecedores com preço de produto inferior a 20:
    ```
    SELECT SupplierName
    FROM Suppliers
    WHERE EXISTS (SELECT ProductName FROM Products WHERE Products.SupplierID = Suppliers.SupplierID AND Price < 20);
    ```

- A instrução SQL a seguir retorna **TRUE** e lista os fornecedores com preço de produto igual a 22:
    ```
    SELECT SupplierName
    FROM Suppliers
    WHERE EXISTS (SELECT ProductName FROM Products WHERE Products.SupplierID = Suppliers.SupplierID AND Price = 22);
    ```

---

## SQL Any, All

Os operadores ``ANY`` e ``ALL`` permitem realizar uma comparação entre um único valor de coluna e um intervalo de outros valores.

### O operador SQL ANY:

O operador ``ANY``:
- Retorna um valor booleano como resultado.
- Retorna **TRUE** se **QUALQUER** um dos valores da subconsulta atender à condição.

``ANY`` significa que a condição será verdadeira se a operação for verdadeira para qualquer um dos valores no intervalo.

**Sintaxe ANY:**

```
SELECT column_name(s)
FROM table_name
WHERE column_name operator ANY (SELECT column_name FROM table_name WHERE condition);
```

> **Observação**: O _operador_ deve ser um operador de comparação padrão (=, <>, !=, >, >=, < ou <=).

### O operador SQL ALL:

O operador ``ALL``:
- Retorna um valor booleano como resultado.
- Retorna **TRUE** se **TODOS** os valores da subconsulta atenderem à condição.
- É usado com declarações ``SELECT``, ``WHERE`` e ``HAVING``.

``ALL`` significa que a condição será verdadeira somente se a operação for verdadeira para todos os valores no intervalo.

**Sintaxe ALL com SELECT:**

```
SELECT ALL column_name(s)
FROM table_name
WHERE condition;
```

**Sintaxe ALL com WHERE ou HAVING:**

```
SELECT column_name(s)
FROM table_name
WHERE column_name operator ALL (SELECT column_name FROM table_name WHERE condition);
```

> **Observação**: O _operador_ deve ser um operador de comparação padrão (=, <>, !=, >, >=, < ou <=).

### Exemplos SQL ANY:

- A instrução SQL a seguir lista o "ProductName" se ele encontrar **QUALQUER** registro na tabela "OrderDetails" com _Quantidade_ igual a 10 (isso retornará **TRUE** porque a coluna _Quantity_ tem alguns valores de 10):
    ```
    SELECT ProductName
    FROM Products
    WHERE ProductID = ANY (SELECT ProductID FROM OrderDetails WHERE Quantity = 10);
    ```

- A instrução SQL a seguir lista o "ProductName" se encontrar **QUALQUER** registro na tabela "OrderDetails" com _Quantidade_ maior que 99 (isso retornará **TRUE** porque a coluna _Quantity_ tem alguns valores maiores que 99):
    ```
    SELECT ProductName
    FROM Products
    WHERE ProductID = ANY (SELECT ProductID FROM OrderDetails WHERE Quantity > 99);
    ```

- A instrução SQL a seguir lista o "ProductName" se encontrar **QUALQUER** registro na tabela "OrderDetails" com _Quantidade_ maior que 1.000 (isso retornará **FALSE** porque a coluna _Quantity_ não tem valores maiores que 1.000):
    ```
    SELECT ProductName
    FROM Products
    WHERE ProductID = ANY (SELECT ProductID FROM OrderDetails WHERE Quantity > 1000);
    ```

### Exemplos SQL ALL:

- A instrução SQL a seguir lista **TODOS** os nomes de produtos:
    ```
    SELECT ALL ProductName
    FROM Products
    WHERE TRUE;
    ```

- A instrução SQL a seguir lista o "ProductName" se **TODOS** os registros na tabela "OrderDetails" tiverem _Quantidade_ igual a 10. Isso obviamente retornará **FALSE** porque a coluna _Quantity_ tem muitos valores diferentes (não apenas o valor de 10):
    ```
    SELECT ProductName
    FROM Products
    WHERE ProductID = ALL (SELECT ProductID FROM OrderDetails WHERE Quantity = 10);
    ```

---

## SQL Select Into

A instrução ``SELECT INTO`` copia dados de uma tabela para uma nova tabela.

**Sintaxe SELECT INTO:**

- Copie todas as colunas para uma nova tabela:
    ```
    SELECT *
    INTO newtable [IN externaldb]
    FROM oldtable
    WHERE condition;
    ```

- Copie apenas algumas colunas para uma nova tabela:
    ```
    SELECT column1, column2, column3, ...
    INTO newtable [IN externaldb]
    FROM oldtable
    WHERE condition;
    ```

A nova tabela será criada com os nomes e tipos de coluna definidos na tabela antiga. É possível criar novos nomes de coluna usando a cláusula ``AS``.

### Exemplos SQL SELECT INTO:

- A instrução SQL a seguir cria uma cópia de backup de "Customers":
    ```
    SELECT * INTO CustomersBackup2017
    FROM Customers;
    ```

- A instrução SQL a seguir usa a cláusula ``IN`` para copiar a tabela em uma nova tabela em outro banco de dados:
    ```
    SELECT * INTO CustomersBackup2017 IN 'Backup.mdb'
    FROM Customers;
    ```

- A instrução SQL a seguir copia apenas algumas colunas em uma nova tabela:
    ```
    SELECT CustomerName, ContactName INTO CustomersBackup2017
    FROM Customers;
    ```

- A instrução SQL a seguir copia apenas os clientes alemães em uma nova tabela:
    ```
    SELECT * INTO CustomersGermany
    FROM Customers
    WHERE Country = 'Germany';
    ```

- A instrução SQL a seguir copia dados de mais de uma tabela para uma nova tabela:
    ```
    SELECT Customers.CustomerName, Orders.OrderID
    INTO CustomersOrderBackup2017
    FROM Customers
    LEFT JOIN Orders ON Customers.CustomerID = Orders.CustomerID;
    ```

> **Dica**: ``SELECT INTO`` também pode ser usado para criar uma nova tabela vazia usando o esquema de outra. Basta adicionar uma cláusula ``WHERE`` que faz com que a consulta não retorne nenhum dado:
    ```
    SELECT * INTO newtable
    FROM oldtable
    WHERE 1 = 0;
    ```

---

## SQL Insert Into Select

A instrução ``INSERT INTO SELECT`` copia dados de uma tabela e os insere em outra tabela.

A instrução ``INSERT INTO SELECT`` requer que os tipos de dados nas tabelas de origem e destino correspondam.

> **Observação**: Os _registros existentes na tabela de destino não são afetados_.

**Sintaxe INSERT INTO SELECT:**

- Copie todas as colunas de uma tabela para outra tabela:
    ```
    INSERT INTO table2
    SELECT * FROM table1
    WHERE condition;
    ```

- Copie apenas algumas colunas de uma tabela para outra tabela:
    ```
    INSERT INTO table2 (column1, column2, column3, ...)
    SELECT column1, column2, column3, ...
    FROM table1
    WHERE condition;
    ```

### Exemplos SQL INSERT INTO SELECT:

- A instrução SQL a seguir copia "Suppliers" em "Customers" (as colunas que não forem preechidas com dados conterão **NULL**):
    ```
    INSERT INTO Customers (CustomerName, City, Country)
    SELECT SupplierName, City, Country FROM Suppliers;
    ```

- A instrução SQL a seguir copia "Suppliers" para "Customers" (preencha todas as colunas):
    ```
    INSERT INTO Customers (CustomerName, ContactName, Address, City, PostalCode, Country)
    SELECT SupplierName, ContactName, Address, City, PostalCode, Country FROM Suppliers;
    ```

- A instrução SQL a seguir copia apenas os fornecedores alemães em "Customers":
    ```
    INSERT INTO Customers (CustomerName, City, Country)
    SELECT SupplierName, City, Country FROM Suppliers
    WHERE Country='Germany';
    ```

---

## SQL Case

A expressão ``CASE`` passa por condições e retorna um valor quando a primeira condição é atendida (como uma instrução if-then-else). Assim, quando uma condição for _verdadeira_, ele irá parar de ler e retornar o resultado. Se nenhuma condição for _verdadeira_, ele retorna o valor na cláusula ``ELSE``.

Se não houver ``ELSE`` e nenhuma condição for _verdadeira_, ele retornará **NULL**.

**Sintaxe CASE:**

```
CASE
    WHEN condition1 THEN result1
    WHEN condition2 THEN result2
    WHEN conditionN THEN resultN
    ELSE result
```

### Exemplos SQL CASE:

- O seguinte SQL passa por condições e retorna um valor quando a primeira condição é atendida:
    ```
    SELECT OrderID, Quantity,
    CASE
        WHEN Quantity > 30 THEN 'The quantity is greater than 30'
        WHEN Quantity = 30 THEN 'The quantity is 30'
        ELSE 'The quantity is under 30'
    END AS QuantityText
    FROM OrderDetails;
    ```

- O SQL a seguir ordenará os clientes por cidade. No entanto, se a cidade for **NULL**, ordene por país:
    ```
    SELECT CustomerName, City, Country
    FROM Customers
    ORDER BY
    (CASE
        WHEN City IS NULL THEN Country
        ELSE City
    END);
    ```

---

## SQL Null Functions


