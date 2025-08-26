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

