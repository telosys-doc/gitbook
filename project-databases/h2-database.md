# H2 database

### Structure

**Database** → **Schema** → Tables/Objects

<div align="left"><figure><img src="../.gitbook/assets/image (2).png" alt="" width="246"><figcaption></figcaption></figure></div>

* **Database**: In H2, the "database" is basically the connection (in-memory or file). \
  There’s only one database per connection.
* **Schema**: H2 supports schemas, similar to PostgreSQL and SQL Server. Default schema is `PUBLIC`. You can create others (`CREATE SCHEMA sales;`). Objects belong to schemas.

### H2 case conversion rules

* **Unquoted identifiers**
  * Always **converted to UPPERCASE**, following the SQL standard.
  * Applies to both **table names** and **column names**.
* **Quoted identifiers**
  * Case is **preserved exactly as written**
  * They are **case-sensitive** in SQL requests

### H2 modes

H2 can run in **3 main modes**:

1. **Embedded**  (in-process)
   * URL with data storage **in memory**:\
     `jdbc:h2:`**`mem`**`:{database-name}`
   * URL with data storage **in file**: \
     `jdbc:h2:`**`{dir-path}`**`/{database-name}`
2.  **Remote Server mode** (accepting external connections)

    * URL with data storage **in memory**:\
      `jdbc:h2:`<mark style="color:red;">**`tcp`**</mark><mark style="color:red;">`://{host}:{port}`</mark>`/`**`mem`**`:{database-name}`
    * URL with data storage **in file**: \
      `jdbc:h2:`<mark style="color:red;">**`tcp`**</mark><mark style="color:red;">`://{host}:{port}`</mark>`/`**`{dir-path}`**`/{database-name}`

    For "SSL" replace "tcp" by "ssl"
3. **Mixed mode** (embedded + server at the same time)



### Telosys typical configuration for a H2 database in "server" mode with file storage

```yaml
  - id: h2-srv
    name: my H2 database server with storage in file
    type: H2 
    # JDBC connection 
    url: jdbc:h2:tcp://localhost:9092/D:/Z/db-data/mydatabase
    driver: org.h2.Driver
    user: sa
    password: sa
    # Metadata parameters (schema name in UPPER CASE)
    catalog: '!'
    schema: 'CARS'
    tableNamePattern: '%'
    tableTypes: TABLE

```



### JDBC driver

The H2 JDBC driver is located in the single JAR provided by H2.

JAR file example:  `h2-2.3.232.jar`
