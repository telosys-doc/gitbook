# SQLite database

### Structure

**Database file(s)** (main/temp/attached) → Tables/Objects

* **Database**: SQLite is just a **single-file database**. When you connect, you are in one database. There’s no concept of multiple independent databases inside one connection.
*   **Schema**:  the notion of "schema" can be simulated by "attaching" databases.\
    SQLite supports:&#x20;

    * **main** (the connected file),&#x20;
    * **temp** (temporary objects),&#x20;
    * any **attached databases** (via `ATTACH DATABASE 'file2.db' AS otherdb;`).

    These act "_like schemas"_ in terms of naming (`main.table1`, `otherdb.table2`), but they’re really separate database files.\


### Telosys typical configuration for a SQLite database

```yaml
xxx
```
