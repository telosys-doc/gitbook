# Derby database

### Structure

**Database** → **Schema** → Tables/Objects

* **Database**: In Derby, the "database" is basically the connection. \
  There’s only one database per connection (each connection is tied to a single database).\
  A **database** is essentially a **directory** on disk.
* **Schema**: Derby supports schemas, similar to PostgreSQL and SQL Server. \
  In Derby, a schema is a namespace within a database.\
  A schema contains tables, views, indexes, triggers, and procedures.\
  Derby defaults schema = current user name (uppercased), \
  for example if user = "sa" ⇒ schema is "SA".\
  If connecting without credentials (no user) the default schema "APP" will be used&#x20;



### Telosys typical configuration for a Derby database

```yaml
  - id: derby
    name: my Derby server database
    type: Derby 
    # JDBC connection
    driver: org.apache.derby.jdbc.ClientDriver 
    url: jdbc:derby://localhost:1527/telosysdb;create=true
    user: foo
    password: xxxxx
    # Metadata parameters
    schema: '!'
    # catalog: '!'
    tableNamePattern: '%'
    tableTypes: TABLE
```

* "_catalog_" is not required
* "_schema_" can be a schema name or '!' for all schemas&#x20;
* if authentication is not enabled then "_user_" and "_password_" can have any value



### JDBC driver

Download:  [https://db.apache.org/derby/derby\_downloads.html](https://db.apache.org/derby/derby_downloads.html)&#x20;

JAR files required to connect:

* &#x20;**`derbyclient.jar`**  &#x20;
* **`derbyshared.jar`**  &#x20;
* **`derbytools.jar`** &#x20;



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

