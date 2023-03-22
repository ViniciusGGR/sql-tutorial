# SQL Database

---

## SQL Create DB

A instrução ``CREATE DATABASE`` é usada para criar um novo banco de dados SQL.

**Sintaxe:**

```
CREATE DATABASE databasename;
```

### Exemplo CREATE DATABASE:

- A instrução SQL a seguir cria um banco de dados chamado "**testDB**":
    ```
    CREATE DATABASE testDB;
    ```

> **Dica**: Certifique-se de ter _privilégios de administrador_ antes de criar qualquer banco de dados. Depois que um banco de dados é criado, é possível verificá-lo na lista de bancos de dados com o seguinte comando SQL: ``SHOW DATABASES``.

---

## SQL Drop DB

A instrução ``DROP DATABASE`` é usada para descartar um banco de dados SQL existente.

**Sintaxe:**

```
DROP DATABASE databasename;
```

> **Nota**: Tenha cuidado antes de descartar um banco de dados. Excluir um banco de dados resultará na perda de informações completas armazenadas no banco de dados.

### Exemplo DROP DATABASE:

- A instrução SQL a seguir descarta o banco de dados existente "**testDB**":
    ```
    DROP DATABASE testDB;
    ```

> **Dica**: Certifique-se de ter _privilégios de administrador_ antes de criar qualquer banco de dados. Depois que um banco de dados é descartado, é possível verificá-lo na lista de bancos de dados com o seguinte comando SQL: ``SHOW DATABASES``.

---

## SQL Backup DB

A instrução ``BACKUP DATABASE`` é usada no SQL Server para criar um backup completo de um banco de dados SQL existente.

**Sintaxe:**

```
BACKUP DATABASE databasename
TO DISK = 'filepath';
```

### A instrução SQL BACKUP WITH DIFFERENTIAL:

- Um _backup diferencial_ faz backup apenas das partes do banco de dados que foram alteradas desde o último backup completo do banco de dados.

**Sintaxe:**

```
BACKUP DATABASE databasename
TO DISK = 'filepath'
WITH DIFFERENTIAL
```

### Exemplo BACKUP DATABASE:

- A instrução SQL a seguir cria um backup completo do banco de dados existente "**testDB**" para o disco D:
    ```
    BACKUP DATABASE testDB
    TO DISK = 'D:\backups\testDB.bak';
    ```

> **Dica**: Sempre faça backup do banco de dados em uma unidade diferente do banco de dados real. Assim, se ocorrer uma falha no disco, não perderá o arquivo de backup junto com o banco de dados.

### Exemplo BACKUP WITH DIFFERENTIAL:

- A instrução SQL a seguir cria um _backup diferencial_ do banco de dados "**testDB**":
    ```
    BACKUP DATABASE testDB
    TO DISK = 'D:\backups\testDB.bak'
    WITH DIFFERENTIAL;
    ```

> **Dica**: Um _backup diferencial_ reduz o tempo de backup (já que apenas as alterações são copiadas).

---

## SQL Create Table

A instrução ``CREATE TABLE`` é usada para criar uma nova tabela em um banco de dados.

**Sintaxe:**

```
CREATE TABLE table_name (
    column1 datatype,
    column2 datatype,
    column3 datatype,
    ...
);
```

Os parâmetros _column_ especificam os nomes das colunas da tabela.

O parâmetro _datatype_ especifica o **tipo de dados** que a coluna pode conter (por exemplo: varchar, integer, date, etc.).

### Exemplo SQL CREATE TABLE:

- O exemplo a seguir cria uma tabela chamada "Persons" que contém cinco colunas: "PersonID", "LastName", "FirstName", "Address" e "City":
    ```
    CREATE TABLE Persons (
        PersonID int,
        LastName varchar(255),
        FirstName varchar(255),
        Address varchar(255),
        City varchar(255)
    );
    ```

    - A coluna "PersonID" é do tipo **int** e conterá um número inteiro.
    - As colunas "LastName", "FirstName", "Address" e "City" são do tipo **varchar** e conterão caracteres, e o comprimento máximo para esses campos é de 255 caracteres.

    > **Dica**: A tabela "Persons" vazia agora pode ser preenchida com dados com a instrução SQL ``INSERT INTO``.

### Criar tabela usando outra tabela:

Uma cópia de uma tabela existente também pode ser criada usando ``CREATE TABLE``.

A nova tabela obtém as mesmas definições de coluna. Todas as colunas ou colunas específicas podem ser selecionadas.

Se criada uma nova tabela usando uma tabela existente, a nova tabela será preenchida com os valores existentes da tabela antiga.

**Sintaxe:**

```
CREATE TABLE new_table AS
    SELECT column1, column2, ...
    FROM existing_table_name
    WHERE ...;
```

- O SQL a seguir cria uma nova tabela chamada "TestTable" (que é uma cópia da tabela "Customers"):
    ```
    CREATE TABLE TestTable AS
    SELECT CustomerName, ContactName
    FROM Customers;
    ```

---

## SQL Drop Table

A instrução ``DROP TABLE`` é usada para descartar uma tabela existente em um banco de dados.

**Sintaxe:**

```
DROP TABLE table_name;
```

> **Nota**: Cuidado antes de deletar uma tabela. Excluir uma tabela resultará na perda de informações completas armazenadas na tabela.

### Exemplo SQL DROP TABLE:

- A seguinte instrução SQL _remove_ a tabela existente "Shippers":
    ```
    DROP TABLE Shippers;
    ```

### SQL TRUNCATE TABLE:

A instrução ``TRUNCATE TABLE`` é usada para excluir os dados dentro de uma tabela, mas não a própria tabela.

**Sintaxe:**

```
TRUNCATE TABLE table_name;
```

---

## SQL Alter Table

A instrução ``ALTER TABLE`` é usada para adicionar, excluir ou modificar colunas em uma tabela existente.

A instrução ``ALTER TABLE`` também é usada para adicionar e remover várias restrições em uma tabela existente.

### ALTER TABLE - ADD Coluna:

- Para adicionar uma coluna em um tabela, basta utilizar a seguinte sintaxe:
    ```
    ALTER TABLE table_name
    ADD column_name datatype;
    ```

- O SQL a seguir adiciona uma coluna "Email" à tabela "Customers":
    ```
    ALTER TABLE Customers
    ADD Email varchar(255);
    ```

### ALTER TABLE - DROP Coluna:

- Para excluir uma coluna em uma tabela, basta utilizar a seguinte sintaxe (alguns sistemas de banco de dados não permitem a exclusão de uma coluna):
    ```
    ALTER TABLE table_name
    DROP COLUMN column_name;
    ```

- O SQL a seguir exclui a coluna "Email" da tabela "Customers":
    ```
    ALTER TABLE Customers
    DROP COLUMN Email;
    ```

### ALTER TABLE - RENAME Coluna:

- Para renomear uma coluna em uma tabela, basta utilizar a seguinte sintaxe:
    ```
    ALTER TABLE table_name
    RENAME COLUMN old_name to new_name;
    ```

### ALTER TABLE - ALTER/MODIFY Tipo de Dados:

Para alterar o tipo de dados de uma coluna em uma tabela, basta utilizar a seguinte sintaxe:

- **SQL Server | MS Access:**
    ```
    ALTER TABLE table_name
    ALTER COLUMN column_name datatype;
    ```

- **MySQL | Oracle (Versão anterior 10G):**
    ```
    ALTER TABLE table_name
    MODIFY COLUMN column_name datatype;
    ```

- **Oracle 10G e posterior:**
    ```
    ALTER TABLE table_name
    MODIFY column_name datatype;
    ```

### Exemplo SQL ALTER TABLE:

- Tabela "Persons":

| ID | LastName  | FirstName | Address      | City      |
| -- | --------- | --------- | ------------ | --------- |
| 1  | Hansen    | Ola       | Timoteivn 10 | Sandnes   |
| 2  | Svendson  | Tove      | Borgvn 23    | Sandnes   |
| 3  | Pettersen | Kari      | Storgt 20    | Stavanger |

- Adicionando uma coluna chamada "DateOfBirth" na tabela "Persons":
    ```
    ALTER TABLE Persons
    ADD DateOfBirth date;
    ```

> **Observação**: A nova coluna "_DateOfBirth_" é do tipo **date** (data) e vai conter uma data. O tipo de dados especifica qual o tipo de dados a coluna pode conter.

- Tabela "Persons" com a nova coluna:

| ID | LastName  | FirstName | Address      | City      | DateOfBirth |
| -- | --------- | --------- | ------------ | --------- | ----------- |
| 1  | Hansen    | Ola       | Timoteivn 10 | Sandnes   |             |
| 2  | Svendson  | Tove      | Borgvn 23    | Sandnes   |             |
| 3  | Pettersen | Kari      | Storgt 20    | Stavanger |             |

- Alterando o tipo de dados da coluna "DateOfBirth" na tabela "Persons":
    ```
    ALTER TABLE Persons
    ALTER COLUMN DateOfBirth year;
    ```

> **Observação**: A coluna "_DateOfBirth_" agora é do tipo **year** (ano) e conterá um ano em um formato de dois ou quatro dígitos.

- Excluindo a coluna "DateOfBirth" na tabela "Persons":
    ```
    ALTER TABLE Persons
    DROP COLUMN DateOfBirth;
    ```

- Tabela "Persons" sem a coluna:

| ID | LastName  | FirstName | Address      | City      |
| -- | --------- | --------- | ------------ | --------- |
| 1  | Hansen    | Ola       | Timoteivn 10 | Sandnes   |
| 2  | Svendson  | Tove      | Borgvn 23    | Sandnes   |
| 3  | Pettersen | Kari      | Storgt 20    | Stavanger |

---

## SQL Constraints


