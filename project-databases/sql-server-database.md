# SQL Server database

## Telosys database configuration

Below are examples of typical configurations for a **SQL Server** database.

### Since Telosys 4.3

```yaml
  
```

### Before Telosys 4.3

```yaml
  
```

### JDBC driver

* Download: &#x20;
* JAR file example :  xx
* Driver class name : **xxxx**



## Technical information about SQL Server

### Structure

Server (instance) → **Database** → **Schema** → Tables/Objects&#x20;

<div align="left"><figure><img src="../.gitbook/assets/image (4).png" alt="" width="287"><figcaption></figcaption></figure></div>

* **Database**: A physical database (similar to PostgreSQL). You must connect to a specific database. Each database is isolated, though cross-database queries are possible (`db1.dbo.table1`).
* **Schema**: A namespace _within a database_. Default schema is usually `dbo`. Users can own schemas, and schemas provide organizational and security boundaries.

