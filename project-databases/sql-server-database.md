# SQL Server database

### Structure

Server (instance) → **Database** → **Schema** → Tables/Objects&#x20;

* **Database**: A physical database (similar to PostgreSQL). You must connect to a specific database. Each database is isolated, though cross-database queries are possible (`db1.dbo.table1`).
* **Schema**: A namespace _within a database_. Default schema is usually `dbo`. Users can own schemas, and schemas provide organizational and security boundaries.

### Telosys typical configuration for a SQL Server database

```yaml
xxx

```

