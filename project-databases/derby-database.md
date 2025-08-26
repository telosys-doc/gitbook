# Derby database

### Structure

**Database** → **Schema** → Tables/Objects



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

Download: xxxxx

JAR file example :  `xxxxxx`



### Types of use

Derby is written in Java, so it's possible to connect via **JDBC** with all **JVM languages**:

* **Java** &#x20;
* **Kotlin**
* **Scala**
* **Groovy**  &#x20;

And also with some other languages:

* **Python**  with **JayDeBeApi**  that allows to connect from Python code to databases using Java JDBC
* **C# / .NET** via **ODBC** with a DB2-compatible driver or via **JDBC** with **IKVM.NET** (though that’s less common)
* **Node.js**  via **JDBC bridges** (e.g., node-jdbc) with Derby’s JDBC driver

