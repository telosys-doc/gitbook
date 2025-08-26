# PostgreSQL database

### Structure

Server (cluster) → **Database** → **Schema** → Tables/Objects&#x20;

<div align="left"><figure><img src="../.gitbook/assets/image.png" alt="" width="287"><figcaption></figcaption></figure></div>

* **Database**: A physical database (separate catalog). Connections are always made to a specific database. Databases are isolated — you can’t query across them without special tools (like `dblink` or FDWs).
* **Schema**: A logical namespace _inside a database_. A database can have multiple schemas (e.g., `public`, `sales`, `hr`). Objects (tables, views, etc.) live inside schemas. You can query across schemas in the same database (`sales.orders`, `hr.employees`).

### PostgreSQL case conversion rules

* **Unquoted identifiers**
  * Always **converted to LOWERCASE**
  * Applies to both **table names** and **column names**.
* **Quoted identifiers**
  * Case is **preserved exactly as written**
  * They are **case-sensitive** in SQL requests

### Telosys typical configuration for a PostgreSQL database

```yaml
  - id: pgcars
    name: PostgreSQL 'cars' schema on 'localhost'
    type: POSTGRESQL 
    # JDBC configuration
    driver: org.postgresql.Driver 
    url: jdbc:postgresql://myhost:5432/mydatabase
    user: john_doe
    password: not_to_reveal
    # Metadata parameters
    catalog: '!'
    schema: cars
    tableNamePattern: '%'
    tableTypes: TABLE
```



### JDBC driver

Download: [https://jdbc.postgresql.org/](https://jdbc.postgresql.org/)&#x20;

JAR file example :  `postgresql-42.7.7.jar`

