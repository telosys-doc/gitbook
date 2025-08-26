# SQLite database

### Structure

**Database file(s)** (main/temp/attached) → Tables/Objects

<div align="left"><figure><img src="../.gitbook/assets/image (3).png" alt="" width="314"><figcaption></figcaption></figure></div>

* **Database**: SQLite is just a **single-file database**. When you connect, you are in one database. There’s no concept of multiple independent databases inside one connection.
*   **Schema**:  There is no concept of "schema" in SQLite, but it can be simulated by "attaching" databases.\
    SQLite supports:&#x20;

    * **main** (the connected file)
    * **temp** (temporary objects)
    * any **attached databases** (via `ATTACH DATABASE 'file2.db' AS otherdb;`)

    These act "_like schemas"_ in terms of naming (`main.table1`, `otherdb.table2`), but they’re really separate database files.\


### Telosys typical configuration for a SQLite database

```yaml
  - id: sqlite
    name: SQLite DB on 'localhost'
    type: SQLITE 
    # JDBC config 
    driver: org.sqlite.JDBC
    url: jdbc:sqlite:D:\Z\DB-DATA\SQLite-data\sqlite-db-example.db
    # user: 
    # password: 
    # Metadata parameters
    tableNamePattern: '%'
    tableTypes: TABLE
```



### JDBC driver&#x20;

Download from [https://github.com/xerial/sqlite-jdbc](https://github.com/xerial/sqlite-jdbc)&#x20;

