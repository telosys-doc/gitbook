# Oracle database

## Telosys database configuration

Below are examples of typical configurations for **Oracle** database.

### Since Telosys 4.3

```yaml
  - id: oracle
    name: Oracle database
    type: ORACLE
    # JDBC connection
    #   url for SID:     jdbc:oracle:thin:@[HOST][:PORT]:SID     (older format)
    #   url for SERVICE: jdbc:oracle:thin:@[HOST][:PORT]/SERVICE (newer format)
    url: jdbc:oracle:thin:@localhost:1521/MYDBSERVICE
    user: SCOTT
    password: TIGER
    # Metadata parameters
    schema: MYSCHEMA
```

### Before Telosys 4.3

```yaml
  - id: oracle
    name: Oracle database
    type: ORACLE
    # JDBC driver 
    driver: oracle.jdbc.OracleDriver
    # JDBC connection
    #   url for SID:     jdbc:oracle:thin:@[HOST][:PORT]:SID     (older format)
    #   url for SERVICE: jdbc:oracle:thin:@[HOST][:PORT]/SERVICE (newer format)
    url: jdbc:oracle:thin:@localhost:1521/MYDBSERVICE
    user: SCOTT
    password: TIGER
    # Metadata parameters
    catalog: '!'
    schema: MYSCHEMA
    tableNamePattern: '%'
    tableNameInclude:
    tableNameExclude:
    tableTypes: TABLE
```

### JDBC driver

* Download:
  * Web site: [https://www.oracle.com/fr/database/technologies/appdev/jdbc-downloads.html](https://www.oracle.com/fr/database/technologies/appdev/jdbc-downloads.html)&#x20;
  * MVN Repository: [https://mvnrepository.com/search?q=oracle](https://mvnrepository.com/search?q=oracle)&#x20;
* JAR for Oracle versions 21c, 19c, 18c, and 12.2:
  * **ojdbc11.jar** ( JDBC 4.3 / JDK11 and JDK17 )&#x20;
  * **ojdbc10.jar** ( JDBC 4.3 / JDK11 )
  * **ojdbc8.jar** ( JDBC 4.2 / JDK8 and JDK11 )
* Driver class name:  **oracle.jdbc.OracleDriver**



## Technical information about Oracle

### Structure

Server (instance) → **Database** → **User=Schema** → Tables/Objects&#x20;

<div align="left"><figure><img src="../.gitbook/assets/image (5).png" alt="" width="301"><figcaption></figcaption></figure></div>

* **Database**: In Oracle, the "database" is the entire system of data files, control files, redo logs, etc. A database is tied to an **instance** (set of processes + memory structures). Usually, one instance ↔ one database, though RAC can have multiple instances for one database.
*   **Schema**: In Oracle, a schema is essentially **a user account**.

    When you create a user (`CREATE USER foo IDENTIFIED BY ...`), Oracle automatically creates a schema with the same name. That schema contains all objects owned by that user (tables, views, procedures, etc.).

    There isn’t a concept of multiple schemas under one user; it’s a **1:1 mapping** (**user = schema**).

    It is possible to query another user's objects (cross-schema access) if you have the permissions

### Boolean type

Unlike PostgreSQL or MySQL, **Oracle** has **no native BOOLEAN column type** (only PL/SQL supports it).\
That’s a very common pain point with Oracle.

The most common approach is to store boolean values in a column of type **NUMBER(1)**\
This is the simplest, portable, and recommended way.\
For example it allows to use Hibernate without specific converter.







