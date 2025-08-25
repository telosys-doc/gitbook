# PostgreSQL database

### PostgreSQL structure

Server (cluster) → **Database** → **Schema** → Tables/Objects&#x20;

* **Database**: A physical database (separate catalog). Connections are always made to a specific database. Databases are isolated — you can’t query across them without special tools (like `dblink` or FDWs).
* **Schema**: A logical namespace _inside a database_. A database can have multiple schemas (e.g., `public`, `sales`, `hr`). Objects (tables, views, etc.) live inside schemas. You can query across schemas in the same database (`sales.orders`, `hr.employees`).



### Telosys typical configuration for a PostgreSQL database

```yaml
xxx
  - id: pgcars
    name: PostgreSQL 'cars' schema on 'localhost'
    type: POSTGRESQL 
    # JDBC configuration
    driver: org.postgresql.Driver 
    url: jdbc:postgresql://localhost:5432/postgres
    user: admin
    password: 
    # Metadata parameters
    catalog: '!'
    schema: cars
    tableNamePattern: '%'
    tableTypes: TABLE
```

