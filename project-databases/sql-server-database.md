# SQL Server database

## Telosys database configuration

Below are examples of typical configurations for a **SQL Server** database.

### Since Telosys 4.3

```yaml
  - id: sqlsrv
    name: SQL Server database 
    type: SQLSERVER
    # JDBC configuration
    url: jdbc:sqlserver://localhost:1433;databaseName=MyDB
    user: john_doe
    password: not_to_reveal
    # Metadata parameters
    schema: cars
```

### Before Telosys 4.3

```yaml
  - id: sqlsrv
    name: SQL Server database 
    type: SQLSERVER
    # JDBC configuration
    driver: com.microsoft.sqlserver.jdbc.SQLServerDriver
    url: jdbc:sqlserver://localhost:1433;databaseName=MyDB
    user: john_doe
    password: not_to_reveal
    # Metadata parameters
    catalog: '!'
    schema: cars
    tableNamePattern: '%'
    tableTypes: TABLE    
```

### Other JDBC URL examples

```
jdbc:sqlserver://localhost:1433;databaseName=TestDB;encrypt=true;trustServerCertificate=true;

```

### JDBC driver

* Download:  [https://learn.microsoft.com/en-us/sql/connect/jdbc/download-microsoft-jdbc-driver-for-sql-server](https://learn.microsoft.com/en-us/sql/connect/jdbc/download-microsoft-jdbc-driver-for-sql-server)&#x20;
* JAR file examples : &#x20;
  * mssql-jdbc-13.2.1.jre8.jar&#x20;
  * mssql-jdbc-13.2.1.jre11.jar
* Driver class name : **com.microsoft.sqlserver.jdbc.SQLServerDriver**&#x20;



## Technical information about SQL Server

### Structure

Server (instance) → **Database** → **Schema** → Tables/Objects&#x20;

<div align="left"><figure><img src="../.gitbook/assets/image (4).png" alt="" width="287"><figcaption></figcaption></figure></div>

* **Database**: A physical database (similar to PostgreSQL). You must connect to a specific database. Each database is isolated, though cross-database queries are possible (`db1.dbo.table1`).
* **Schema**: A namespace _within a database_. Default schema is usually `dbo`. Users can own schemas, and schemas provide organizational and security boundaries.

