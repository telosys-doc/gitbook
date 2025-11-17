# SQLite database

## Telosys database configuration

Below are examples of typical configurations for a **SQLite** database.

### Since Telosys 4.3

```yaml
  - id: sqlite
    name: SQLite database 
    type: SQLITE 
    # JDBC config 
    url: jdbc:sqlite:D:\Z\DB-DATA\SQLite-data\sqlite-db-example.db
    # no user 
    # no password
```

### Before Telosys 4.3

```yaml
  - id: sqlite
    name: SQLite database 
    type: SQLITE 
    # JDBC config 
    driver: org.sqlite.JDBC
    url: jdbc:sqlite:D:\Z\DB-DATA\SQLite-data\sqlite-db-example.db
    # no user  
    # no password
    # Metadata parameters
    tableNamePattern: '%'
    tableTypes: TABLE
```

### JDBC driver&#x20;

* Download from [https://github.com/xerial/sqlite-jdbc](https://github.com/xerial/sqlite-jdbc) &#x20;
* JAR file example:  `sqlite-jdbc-3.50.3.0.jar` &#x20;
* Driver class name:  **org.sqlite.JDBC**

## Technical information about SQLite

### Structure

**Database file(s)** (main/temp/attached) → Tables/Objects

<div align="left"><figure><img src="../.gitbook/assets/image (3).png" alt="" width="314"><figcaption></figcaption></figure></div>

* **Database**: SQLite is just a **single-file database**. When you connect, you are in one database. \
  There’s no concept of multiple independent databases inside one connection.\
  SQLite is an embedded database. There is no database server, no user accounts, and no network authentication.
*   **Schema**:  There is no concept of "schema" in SQLite, but it can be simulated by "attaching" databases.\
    SQLite supports:&#x20;

    * **main** (the connected file)
    * **temp** (temporary objects)
    * any **attached databases** (via `ATTACH DATABASE 'file2.db' AS otherdb;`)

    These act "_like schemas"_ in terms of naming (`main.table1`, `otherdb.table2`), but they’re really separate database files.

### Boolean type

SQLite **does not have a native BOOLEAN type**.

It uses dynamic typing: a column can store any value regardless of declared type.\
Conventionally, booleans are stored as:  **0 →  false**  and  **1 →  true**\
You can declare a column as BOOLEAN, INTEGER, or NUMERIC; \
SQLite just treats it as an affinity, not a strict type.

If you use **Hibernate** with **SQLite dialect**, a boolean or Boolean in your entity is usually mapped to INTEGER (or NUMERIC) in the DB.\
Hibernate automatically persists:  true → 1  and false → 0\
Reading from the column is automatically converted back to boolean.\
So no converter is needed for standard 0/1 boolean storage.

### Notes

* **Authentication**:  \
  By default, SQLite databases are just files (.db or .sqlite) on disk.\
  Anyone who can read/write the file has full access to the database.
* **No "catalog" and "schema"**\
  There is no concept of schema and catalog in SQLite  \
  When Telosys retrieves the database model, 'catalog' and 'schema' are always 'null'.
* **In-memory database**\
  It's possible to work only "in-memory".\
  The database exists only in RAM, not on disk.  \
  To do so use JDBC URL like this:  `"jdbc:sqlite::memory:"`\
  NB: duration=connexion, as soon as the **connection** is closed, the entire database (all tables) disappears. SQLite supports a mode that allows multiple connections to share the same in-memory database: `"jdbc:sqlite:file:memdb1?mode=memory&cache=shared"`\
  it will create an in-memory database named "memdb1" (this will not create any files on disk)\
  But even with this mode a shared in-memory database only exists while **at least one connection to it is still open**. As soon as the last connection closes, SQLite frees the memory, and all tables vanish.

