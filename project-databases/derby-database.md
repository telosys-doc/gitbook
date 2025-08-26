# Derby database

### Structure

**Database** → **Schema** → Tables/Objects

* **Database**: In Derby, the "database" is basically the connection. \
  There’s only one database per connection (each connection is tied to a single database).\
  A **database** is essentially a **directory** on disk.
* **Schema**: Derby supports schemas, similar to PostgreSQL and SQL Server. \
  In Derby, a schema is a namespace within a database.\
  A schema contains tables, views, indexes, triggers, and procedures.\
  Default schema is the database username, usually `APP`  (in uppercase) &#x20;



### Telosys typical configuration for a Derby database

```yaml
  - id: derbydb
    name: Derby 
    type: DERBY
    # JDBC configuration
    driver: xxxx 
    url: xxxxx
    user: john_doe
    password: not_to_reveal
    # Metadata parameters
    catalog: '!'
    schema: xxx
    tableNamePattern: '%'
    tableTypes: TABLE
```



### JDBC driver

Download:  [https://db.apache.org/derby/derby\_downloads.html](https://db.apache.org/derby/derby_downloads.html)&#x20;

JAR file example:   **`derbyclient.jar`**   (JDBC client for network server mode)



### Server Launch

Just launch  **`bin/startNetworkServer`**  ( default port = 1527 )



### Derby types of use

Derby is written in Java, so it's possible to connect via **JDBC** with all **JVM languages**:

* **Java** &#x20;
* **Kotlin**
* **Scala**
* **Groovy**  &#x20;

And also with some other languages:

* **Python**  with **JayDeBeApi**  that allows to connect from Python code to databases using Java JDBC
* **C# / .NET** via **ODBC** with a DB2-compatible driver or via **JDBC** with **IKVM.NET** (though that’s less common)
* **Node.js**  via **JDBC bridges** (e.g., node-jdbc) with Derby’s JDBC driver

