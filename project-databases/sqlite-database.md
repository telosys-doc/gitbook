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
    name: SQLite database 
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

JAR file example:  `sqlite-jdbc-3.50.3.0.jar`



### Notes

* **Authentication**:  \
  By default, SQLite databases are just files (.db or .sqlite) on disk.\
  Anyone who can read/write the file has full access to the database.
* **No "catalog" and "schema"**\
  There is no concept of schema and catalog in SQLite  \
  When Telosys retrieves the database model, 'catalog' and 'schema' are always 'null'.
*   **In-memory database**\
    It's possible to work only "in-memory"    \
    To do so use JDBC URL like this:  `"jdbc:sqlite::memory:"`\
    NB: \
    &#x20; \- The database exists only in RAM, not on disk

    &#x20; \- As soon as the **connection** is closed, the entire database (all tables) disappears

