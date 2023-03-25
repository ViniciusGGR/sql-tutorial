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

As _constraints_ (restrições) SQL são usadas para especificar regras para dados em uma tabela.

### SQL Create Constraints:

As _constraints_ (restrições) podem ser especificadas quando a tabela é criada com a instrução ``CREATE TABLE`` ou depois que a tabela é criada com a instrução ``ALTER TABLE``.

**Sintaxe:**

```
CREATE TABLE table_name (
    column1 datatype constraint,
    column2 datatype constraint,
    column3 datatype constraint,
    ...
);
```

### SQL Constraints:

As _constraints_ (restrições) são usadas para especificar regras para os dados em uma tabela.

As _constraints_ (restrições) são usadas para limitar o tipo de dados que podem entrar em uma tabela. Isso garante a precisão e a confiabilidade dos dados na tabela. Se houver alguma violação entre a restrição e a ação de dados, a ação será abortada.

As _constraints_ (restrições) podem ser **nível de coluna** ou **nível de tabela**. As restrições de nível de coluna se aplicam a uma coluna e as restrições de nível de tabela se aplicam a toda a tabela.

- As _constraints_ (restrições) que são comumente usadas em SQL:
    - ``NOT NULL`` - Garante que uma coluna não pode ter um valor **NULL**.
    - ``UNIQUE`` - Garante que todos os valores em uma coluna sejam diferentes.
    - ``PRIMARY KEY`` - Uma combinação de ``NOT NULL`` e ``UNIQUE``. Identifica exclusivamente cada linha em uma tabela.
    - ``FOREIGN KEY`` - Impede ações que destruiriam links entre tabelas.
    - ``CHECK`` - Garante que os valores em uma coluna satisfaçam uma condição específica.
    - ``DEFAULT`` - Define um valor padrão para uma coluna se nenhum valor for especificado.
    - ``CREATE INDEX`` - Usado para criar e recuperar dados do banco de dados muito rapidamente.

---

## SQL Not Null

Por padrão, uma coluna pode conter valores **NULL**.

A _constraint_ (restrição) ``NOT NULL`` força uma coluna a **NÃO** aceitar valores **NULL**. Isso obriga um campo a sempre conter um valor, o que significa que não é possível inserir um novo registro ou atualizar um registro sem adicionar um valor a esse campo.

### SQL NOT NULL em CREATE TABLE:

- O seguinte SQL garante que as colunas "ID", "LastName" e "FirstName" **NÃO** aceitarão valores **NULL** quando a tabela "Persons" for criada:
    ```
    CREATE TABLE Persons (
        ID int NOT NULL,
        LastName varchar(255) NOT NULL,
        FirstName varchar(255) NOT NULL,
        Age int
    );
    ```

### SQL NOT NULL em ALTER TABLE:

- Para criar uma _constraint_ (restrição) ``NOT NULL`` na coluna "Age" quando a tabela "Persons" já estiver criada, basta utilizar o seguinte SQL:

**SQL Server | MS Access:**

```
ALTER TABLE Persons
ALTER COLUMN Age int NOT NULL;
```

**MySQL | Oracle (Versão anterior 10G):**

```
ALTER TABLE Persons
MODIFY COLUMN Age int NOT NULL;
```

**Oracle 10G e posterior:**

```
ALTER TABLE Persons
MODIFY Age int NOT NULL;
```

---

## SQL Unique

A _constraint_ (restrição) ``UNIQUE`` garante que todos os valores em uma coluna sejam diferentes.

As _constraints_ (restrições) ``UNIQUE`` e ``PRIMARY KEY`` fornecem uma garantia de exclusividade para uma coluna ou conjunto de colunas.

Uma _constraint_ (restrição) ``PRIMARY KEY`` tem automaticamente uma _constraint_ (restrição) ``UNIQUE``.

No entanto, é possível ter **MUITAS** _constraints_ (restrições) ``UNIQUE`` por tabela, mas apenas **UMA** _constraint_ (restrição) ``PRIMARY KEY`` por tabela.

### SQL UNIQUE Constraint em CREATE TABLE:

O SQL a seguir cria uma _constraint_ (restrição) ``UNIQUE`` na coluna "ID" quando a tabela "Persons" é criada:

**SQL Server | Oracle | MS Access:**

```
CREATE TABLE Persons (
    ID int NOT NULL UNIQUE,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int
);
```

**MySQL:**

```
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    UNIQUE (ID)
);
```

- Para nomear uma _constraint_ (restrição) ``UNIQUE`` e definir uma _constraint_ (restrição) ``UNIQUE`` em várias colunas, basta utilizar a seguinte sintaxe SQL:  

    **MySQL | SQL Server | Oracle | MS Access:**
    ```
    CREATE TABLE Persons (
        ID int NOT NULL,
        LastName varchar(255) NOT NULL,
        FirstName varchar(255),
        Age int,
        CONSTRAINT UC_Person UNIQUE (ID, LastName)
    );
    ```

### SQL UNIQUE Constraint em ALTER TABLE:

- Para criar uma _constraint_ (restrição) ``UNIQUE`` na coluna "ID" quando a tabela já estiver criada, basta utilizar o seguinte SQL:  

    **MySQL | SQL Server | Oracle | MS Access:**
    ```
    ALTER TABLE Persons
    ADD UNIQUE (ID);
    ```

- Para nomer uma _constraint_ (restrição) ``UNIQUE`` e definir uma _constraint_ (restrição) ``UNIQUE`` em várias colunas, basta utilizar a seguinte sintaxe SQL:  

    **MySQL | SQL Server | Oracle | MS Access:**
    ```
    ALTER TABLE Persons
    ADD CONSTRAINT UC_Person UNIQUE (ID, LastName);
    ```

### DROP uma UNIQUE Constraint:

- Para descartar uma _constraint_ (restrição) ``UNIQUE``, basta utilizar o seguinte SQL:  

    **MySQL:**
    ```
    ALTER TABLE Persons
    DROP INDEX UC_Person;
    ```

    **SQL Server | Oracle | MS Access:**
    ```
    ALTER TABLE Persons
    DROP CONSTRAINT UC_Person;
    ```

---

## SQL Primary Key

A _constraint_ (restrição) ``PRIMARY KEY`` identifica exclusivamente cada registro em uma tabela.

As ``PRIMARY KEY`` devem conter valores ``UNIQUE`` e não podem conter valores **NULL**.

Uma tabela pode ter apenas **UMA** ``PRIMARY KEY``, e na tabela, essa ``PRIMARY KEY`` pode consistir em uma ou várias colunas.

### SQL PRIMARY KEY em CREATE TABLE:

- O seguinte SQL cria um ``PRIMARY KEY`` na coluna "ID" quando a tabela "Persons" é criada:  

    **MySQL:**
    ```
    CREATE TABLE Persons (
        ID int NOT NULL,
        LastName varchar(255),
        FirstName varchar(255),
        Age int,
        PRIMARY KEY (ID)
    );
    ```

    **SQL Server | Oracle | MS Access:**
    ```
    CREATE TABLE Persons (
        ID int NOT NULL PRIMARY KEY,
        LastName varchar(255),
        FirstName varchar(255),
        Age int
    );
    ```

- Para permitir a nomeação de uma _constraint_ (restrição) ``PRIMARY KEY`` e para definir uma _constraint_ (restrição) ``PRIMARY KEY`` em várias colunas, basta utilizar a seguinte sintaxe SQL:  

    **MySQL | SQL Server | Oracle | MS Access:**
    ```
    CREATE TABLE Persons (
        ID int NOT NULL,
        LastName varchar(255) NOT NULL,
        FirstName varchar(255),
        Age int,
        CONSTRAINT PK_Person PRIMARY KEY (ID, LastName)
    );
    ```

    > **Observação**: No exemplo acima existe apenas **UMA** ``PRIMARY KEY`` (**PK_Person**). Porém, o **VALOR** da ``PRIMARY KEY`` é formado por **DUAS COLUNAS** (ID + LastName).

### SQL PRIMARY KEY em ALTER TABLE:

- Para criar uma _constraint_ (restrição) ``PRIMARY KEY`` na coluna "ID" quando a tabela já estiver criada, basta utilizar o seguinte SQL:  

    **MySQL | SQL Server | Oracle | MS Access:**
    ```
    ALTER TABLE Persons
    ADD PRIMARY KEY (ID);
    ```

- Para permitir a nomeação de uma _constraint_ (restrição) ``PRIMARY KEY`` e para definir uma _constraint_ (restrição) ``PRIMARY KEY`` em várias colunas, basta utilizar a seguinte sintaxe SQL:  

    **MySQL | SQL Server | Oracle | MS Access:**
    ```
    ALTER TABLE Persons
    ADD CONSTRAINT PK_Person PRIMARY KEY (ID, LastName);
    ```

> **Nota**: Se utilizar o ``ALTER TABLE`` para adicionar uma ``PRIMARY KEY``, a(s) coluna(s) de ``PRIMARY KEY`` deve(m) ter sido declarada para não conter valores **NULL** (quando a tabela for criada pela primeira vez).

### DROP a PRIMARY KEY Constraint:

- Para _descartar_ uma _constraint_ (restrição) ``PRIMARY KEY``, basta utilizar o seguinte SQL:  

    **MySQL:**
    ```
    ALTER TABLE Persons
    DROP PRIMARY KEY;
    ```

    **SQL Server | Oracle | MS Access:**
    ```
    ALTER TABLE Persons
    DROP CONSTRAINT PK_Person;
    ```

---

## SQL Foreign Key

A _constraint_ (restrição) ``FOREIGN KEY`` é usada para evitar ações que destruam os links entre as tabelas.

A _constraint_ (restrição) ``FOREIGN KEY`` é um campo (ou coleção de campos) em uma tabela, que se refere ao ``PRIMARY KEY`` em outra tabela.

- A tabela com a ``FOREIGN KEY`` é chamada de _tabela filho_, e a tabela com a ``PRIMARY KEY`` é chamada de _tabela referênciada ou pai_.  

    **Tabela "Persons":**
    | PersonID | LastName  | FirstName | Age |
    | -------- | --------  | --------- | --- |
    | 1        | Hansen    | Ola       | 30  |
    | 2        | Svendson  | Tove      | 23  |
    | 3        | Pettersen | Kari      | 20  |

    **Tabela "Orders":**
    | OrderID | OrderNumber | PersonID |
    | ------- | ----------- | -------- |
    | 1       | 77895       | 3        |
    | 2       | 44678       | 3        |
    | 3       | 22456       | 2        |
    | 4       | 24562       | 1        |

- A coluna "PersonID" na tabela _Orders_ aponta para a coluna "PersonID" na tabela _Persons_.

- A coluna "PersonID" na tabela _Persons_ é uma coluna ``PRIMARY KEY`` na tabela _Persons_.

- A coluna "PersonID" na tabela _Orders_ é uma coluna ``FOREIGN KEY`` na tabela _Orders_.

A _constraint_ (restrição) ``FOREIGN KEY`` impede que dados inválidos sejam inseridos na coluna ``FOREIGN KEY``, porque deve ser um dos valores contidos na _tabela pai_.

### SQL FOREIGN KEY em CREATE TABLE:

- O seguinte SQL cria uma ``FOREIGN KEY`` na coluna "PersonID" quando a tabela _Orders_ é criada:  

    **MySQL:**
    ```
    CREATE TABLE Orders (
        OrderID int NOT NULL,
        OrderNumber int NOT NULL,
        PersonID int,
        PRIMARY KEY (OrderID),
        FOREIGN KEY (PersonID) REFERENCES Persons(PersonID)
    );
    ```

    **SQL Server | Oracle | MS Access:**
    ```
    CREATE TABLE Orders (
        OrderID int NOT NULL PRIMARY KEY,
        OrderNumber int NOT NULL,
        PersonID int FOREIGN KEY REFERENCES Persons(PersonID)
    );
    ```

- Para permitir a nomeação de uma _constraint_ (restrição) ``FOREIGN KEY`` e para definir uma _constraint_ (restrição) ``FOREIGN KEY`` em várias colunas, basta utilizar a seguinte sintaxe SQL:  

    **MySQL | SQL Server | Oracle | MS Access:**
    ```
    CREATE TABLE Orders (
        OrderID int NOT NULL,
        OrderNumber int NOT NULL,
        PersonID int,
        PRIMARY KEY (OrderID),
        CONSTRAINT FK_PersonOrder FOREIGN KEY (PersonID)
        REFERENCES Persons(PersonID)
    );
    ```

### SQL FOREIGN KEY em ALTER TABLE:

- Para criar uma _constraint_ (restrição) ``FOREIGN KEY`` na coluna "PersonID" quando a tabela _Orders_ já estiver criada, basta utilizar o seguinte SQL:  

    **MySQL | SQL Server | Oracle | MS Access:**
    ```
    ALTER TABLE Orders
    ADD FOREIGN KEY (PersonID) REFERENCES Persons(PersonID);
    ```

- Para permitir a nomeação de uma _constraint_ (restrição) ``FOREIGN KEY`` e para definir uma _constraint_ (restrição) ``FOREIGN KEY`` em várias colunas, basta utilizar a seguinte sintaxe SQL:  

    **MySQL | SQL Server | Oracle | MS Access:**
    ```
    ALTER TABLE Orders
    ADD CONSTRAINT FK_PersonOrder
    FOREIGN KEY (PersonID) REFERENCES Persons(PersonID);
    ```

### DROP a FOREIGN KEY Constraint:

- Para descartar uma _constraint_ (restrição) ``FOREIGN KEY``, basta utilizar o seguinte SQL:  

    **MySQL:**
    ```
    ALTER TABLE Orders
    DROP FOREIGN KEY FK_PersonOrder;
    ```

    **SQL Server | Oracle | MS Access:**
    ```
    ALTER TABLE Orders
    DROP CONSTRAINT FK_PersonOrder;
    ```

---

## SQL Check

A _constraint_ (restrição) ``CHECK`` é usada para limitar o intervalo de valores que pode ser colocado em uma coluna.

- Se definido uma _constraint_ (restrição) ``CHECK`` em uma coluna, ela permitirá apenas determinados valores para esta coluna.

- Se definido uma _constraint_ (restrição) ``CHECK`` em uma tabela, ela poderá limitar os valores em determinadas colunas com base nos valores de outras colunas na linha.

### SQL CHECK em CREATE TABLE:

- O SQL a seguir cria uma _constraint_ (restrição) ``CHECK`` na coluna "Age" quando a tabela _Persons_ é criada. A _constraint_ (restrição) ``CHECK`` garante que idade de uma pessoa deve ser 18 anos ou mais:  

    **MySQL:**
    ```
    CREATE TABLE Persons (
        ID int NOT NULL,
        LastName varchar(255),
        FirstName varchar(255),
        Age int,
        CHECK (Age>=18)
    );
    ```

    **SQL Server | Oracle | MS Access:**
    ```
    CREATE TABLE (
        ID int NOT NULL,
        LastName varchar(255) NOT NULL,
        FirstName varchar(255),
        Age int CHECK (Age>=18)
    );
    ```

- Para permitir a nomeação de uma _constraint_ (restrição) ``CHECK`` e para definir _constraint_ (restrição) ``CHECK`` em várias colunas, basta utilizar a seguinte sintaxe SQL:  

    **MySQL | SQL Server | Oracle | MS Access:**
    ```
    CREATE TABLE Persons (
        ID int NOT NULL,
        LastName varchar(255) NOT NULL,
        FirstName varchar(255),
        Age int,
        City varchar(255),
        CONSTRAINT CHK_Person CHECK (Age>=18 AND City='Sandnes')
    );
    ```

### SQL CHECK em ALTER TABLE:

- Para criar uma _constraint_ (restrição) ``CHECK`` na coluna "Age" quando a tabela já estiver criada, basta utilizar o seguinte SQL:  

    **MySQL | SQL Server | Oracle | MS Access:**
    ```
    ALTER TABLE Persons
    ADD CHECK (Age>=18);
    ```

- Para permitir a nomeação de uma _constraint_ (restrição) ``CHECK`` e para definir uma _constraint_ (restrição) ``CHECK`` em várias colunas, basta utilizar a seguinte sintaxe SQL:  

    **MySQL | SQL Server | Oracle | MS Access:**
    ```
    ALTER TABLE Persons
    ADD CONSTRAINT CHK_PersonAge CHECK (Age>=18 AND City='Sandnes');
    ```

### DROP a CHECK Constraint:

- Para descartar uma _constraint_ (restrição) ``CHECK``, basta utilizar o seguinte SQL:  

    **SQL Server | Oracle | MS Access:**
    ```
    ALTER TABLE Persons
    DROP CONSTRAINT CHK_PersonAge;
    ```

    **MySQL:**
    ```
    ALTER TABLE Persons
    DROP CHECK CHK_PersonAge;
    ```

---

## SQL Default

A _constraint_ (restrição) ``DEFAULT`` é usada para definir um valor padrão para uma coluna.

O valor padrão será adicionado a todos os novos registros, se nenhum outro valor for especificado.

### SQL DEFAULT em CREATE TABLE:

- O seguinte SQL define um valor ``DEFAULT`` para a coluna "City" quando a tabela "Persons" é criada:  

    **MySQL | SQL Server | Oracle | MS Access:**
    ```
    CREATE TABLE Persons (
        ID int NOT NULL,
        LastName varchar(255) NOT NULL,
        FirstName varchar(255),
        Age int,
        City varchar(255) DEFAULT 'Sandnes'
    );
    ```

- A _constraint_ (restrição) ``DEFAULT`` também pode ser usada para inserir valores do sistema, usando funções como ``GETDATE()``:  
    ```
    CREATE TABLE Orders (
        ID int NOT NULL,
        OrderNumber int NOT NULL,
        OrderDate date DEFAULT GETDATE()
    );
    ```

### SQL DEFAULT em ALTER TABLE:

- Para criar uma _constraint_ (restrição) ``DEFAULT`` na coluna "City" quando a tabela já estiver criada, basta utilizar o seguinte SQL:  

    **MySQL:**
    ```
    ALTER TABLE Persons
    ALTER City SET DEFAULT 'Sandnes';
    ```

    **SQL Server:**
    ```
    ALTER TABLE Persons
    ADD CONSTRAINT df_City
    DEFAULT 'Sandnes' FOR City;
    ```

    **MS Access:**
    ```
    ALTER TABLE Persons
    ALTER COLUMN City SET DEFAULT 'Sandnes';
    ```

    **Oracle:**
    ```
    ALTER TABLE Persons
    MODIFY City DEFAULT 'Sandnes';
    ```

### DROP a DEFAULT Constraint:

- Para descartar uma _constraint_ (restrição) ``DEFAULT``, basta utilizar o seguinte SQL:  

    **MySQL:**
    ```
    ALTER TABLE Persons
    ALTER City DROP DEFAULT;
    ```

    **SQL Server | Oracle | MS Access:**
    ```
    ALTER TABLE Persons
    ALTER COLUMN City DROP DEFAULT;
    ```

---

## SQL Index

A instrução ``CREATE INDEX`` é usada para criar índices em tabelas.

Os índices são usados para recuperar dados do banco de dados mais rapidamente do que de outra forma. Os usuários não podem ver os índices, eles são usados apenas para agilizar as pesquisas/consultas.

> **Nota**: Atualizar uma tabela com índices leva mais tempo do que atualizar uma tabela sem (porque os índices também precisam de uma atualização). Portanto é indicado a criação de índices _apenas em colunas_ que serão pesquisadas com mais frequência.

**Sintaxe CREATE INDEX:**

- Criar um índice em uma tabela. Valores duplicados são permitidos:  
    ```
    CREATE INDEX index_name
    ON table_name (column1, column2, ...);
    ```

**Sintaxe CREATE UNIQUE INDEX:**

- Cria um índice exclusivo em uma tabela. _Valores duplicados não são permitidos_:  
    ```
    CREATE UNIQUE INDEX index_name
    ON table_name (column1, column2, ...);
    ```

> **Nota**: A sintaxe para criar índices varia entre diferentes bancos de dados. Portanto: Verifique a sintaxe para criar índices em seu banco de dados.

### Exemplo CREATE INDEX:

- A instrução SQL abaixo cria um índice denominado "idx_lastname" na coluna "LastName" na tabela _Persons_:  
    ```
    CREATE INDEX idx_lastname
    ON Persons (LastName);
    ```

- Caso deseje criar um índice em uma combinação de colunas, pode listar os nomes das colunas entre parênteses, separados por vírgulas:  
    ```
    CREATE INDEX idx_pname
    ON Persons (LastName, FirstName);
    ```

### Instrução DROP INDEX:

- A instrução ``DROP INDEX`` é usada para excluir um índice em uma tabela:  

    **MS Access:**
    ```
    DROP INDEX index_name ON table_name;
    ```

    **SQL Server:**
    ```
    DROP INDEX table_name.index_name;
    ```

    **DB2 | Oracle:**
    ```
    DROP INDEX index_name;
    ```

    **MySQL:**
    ```
    ALTER TABLE table_name
    DROP INDEX index_name;
    ```

---

## SQL Auto Increment


