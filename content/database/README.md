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

