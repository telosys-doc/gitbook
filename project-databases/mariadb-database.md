# MariaDB database

## Telosys database configuration

Below are examples of typical configurations for a **MariaDB** database.

### Since Telosys 4.3

```yaml
  - id: mariadb
    name: MariaDB 'cars' database 
    type: MARIADB 
    # URL jdbc:mariadb://<host>:<port>/<database>?<options>
    url: jdbc:mariadb://myhost:3305/carsdb
    user: john_doe
    password: not_to_reveal
```

### Before Telosys 4.3

```yaml
  - id: mariadb
    name: MariaDB 'cars' database 
    type: MARIADB 
    # JDBC driver 
    driver: org.mariadb.jdbc.Driver
    # URL jdbc:mariadb://<host>:<port>/<database>?<options>
    url: jdbc:mariadb://myhost:3305/carsdb
    user: john_doe
    password: not_to_reveal
    # Metadata parameters
    tableNamePattern: '%'
    tableTypes: TABLE
```

### JDBC driver

* Name:  **MariaDB Connector/J** - lightweight JDBC driver (Type 4) for Java
* Download:&#x20;
  * Web site:  [https://mariadb.com/downloads/connectors/connectors-data-access/](https://mariadb.com/downloads/connectors/connectors-data-access/)&#x20;
  * MVN Repository: [https://mvnrepository.com/search?q=mariadb](https://mvnrepository.com/search?q=mariadb)&#x20;
* JAR file example:  `mariadb-java-client-3.5.6.jar`
* Driver class name:  **org.mariadb.jdbc.Driver**

## Technical information about MariaDB

### Structure

Server → **Database** (= **Schema**) → Tables/Objects

<div align="left"><figure><img src="../.gitbook/assets/image (1).png" alt="" width="242"><figcaption></figcaption></figure></div>

* **Database**: The main organizational unit. \
  In practice, a "**database**" is what most people think of as a "**schema**". \
  When you run `CREATE DATABASE`, it’s like creating a schema.
* **Schema**: Synonymous with database. \
  `CREATE DATABASE foo;`   and  `CREATE SCHEMA foo;`  are the same operation.
* **Cross-database** queries (cross-schema) are allowed within the same server instance (`db1.table1 JOIN db2.table2`)

### Case conversion rules

* **column name**: \
  in MariaDB, column names are **not case-sensitive**, \
  whether the identifiers are in quotes or not.
* **table name** (file system rules matter):\
  \- on **Linux**: may be case-sensitive only if  `lower_case_table_names=0`\
  \- on **Windows**/**macOS**:  case-insensitive.



