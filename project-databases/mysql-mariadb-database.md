# MySQL/MariaDB database

### Structure

Server → **Database** (= **Schema**) → Tables/Objects

<div align="left"><figure><img src="../.gitbook/assets/image (1).png" alt="" width="242"><figcaption></figcaption></figure></div>

* **Database**: The main organizational unit. In practice, a "**database**" in MySQL is what most people think of as a "**schema**". When you run `CREATE DATABASE`, it’s like creating a schema.
* **Schema**: Synonymous with database. \
  MySQL treats `CREATE DATABASE foo;` and `CREATE SCHEMA foo;` as the same operation.
* Cross-database queries are allowed within the same server instance (`db1.table1 JOIN db2.table2`)

### Case conversion rules

* **column name**: \
  in MySQL/MariaDB, column names are **not case-sensitive**, \
  whether the identifiers are in quotes or not.
* **table name**: \
  \- on **Linux**: may be case-sensitive only if  `lower_case_table_names=0`\
  \- on **Windows**/**macOS**:  case-insensitive.

### Telosys typical configuration for a MariaDB database

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

### Telosys typical configuration for a MySQL database

```yaml
  - id: mysqldb
    name: MySQL 'employees' database 
    type: MYSQL 
    # JDBC driver 
    driver: com.mysql.cj.jdbc.Driver
    # URL jdbc:mysql://<host>:<port>/<database>?<options>
    url: jdbc:mysql://myhost:3306/employeesdb
    user: john_doe
    password: not_to_reveal
    # Metadata parameters
    tableNamePattern: '%'
    tableTypes: TABLE

```

### JDBC driver&#x20;

#### MariaDB

* Name:  **MariaDB Connector/J** - lightweight JDBC driver (Type 4) for Java
* Download:  [https://mariadb.com/downloads/connectors/connectors-data-access/](https://mariadb.com/downloads/connectors/connectors-data-access/)&#x20;
* Driver class name:  **org.mariadb.jdbc.Driver**

#### MySQL

* Name:  **MySQL Connector/J**&#x20;
* Download:  [https://dev.mysql.com/downloads/connector/j/](https://dev.mysql.com/downloads/connector/j/) &#x20;
* Driver class name:  **com.mysql.cj.jdbc.Driver**  (since Connector/J 8.0)\
  (old versions used **com.mysql.jdbc.Driver**)

