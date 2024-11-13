# Project databases

A Telosys project can define one or more **databases**.&#x20;

Each database can be used to create a **new model** based on its database schema (tables, relations, etc).

Project databases are defined in the file "<mark style="color:purple;">**TelosysTools/databases.yaml**</mark>".

This YAML file can edited with any editor or IDE.



### Commands for databases definition

* **`ldb`**  -> List databases defined in the current project&#x20;
* **`edb`** -> Edit databases file  ( databases.yaml ) with the editor defined in Telosys-CLI configuration
* **`cdb`** ->  Check database configuration (try to connect and to get meta-data)



### YAML file structure

The file contains a list of database configurations (n items in "**`databases:`**" entry)

For each database:

* Database&#x20;
  * **`id:`**   (string) a unique identifier for the database&#x20;
  * **`name:`**  (string) a name describing the database&#x20;
  * **`type:`**  (string) the database type \
    &#x20;    examples: "PostgreSQL", "MySQL", "Oracle", etc
* JDBC connection
  * **`driver:`**  (string) the JDBC driver to be used to connect to the database (driver Java class name)  \
    &#x20;    examples:  "org.postgresql.Driver"
  * **`url:`**    (string)  the JDBC URL for connection  \
    &#x20;    examples:    "jdbc:postgresql://{HOST}:{PORT}/{DATABASE}"&#x20;
  * **`user:`**  (string)  the database user name&#x20;
  * **`password:`** (string)  the database user password
* What metadata to retrieve &#x20;
  * **`catalog:`**  (string)  the database catalog to use or  '!' for none &#x20;
  * schema: (string)  the database schema to use or  '!' for none
* tableNamePattern:&#x20;
* tableNameInclude:&#x20;
* tableNameExclude:&#x20;
* tableTypes: TABLE # DB model creation dbModelName: # Telosys DSL model creation linksManyToOne: true linksOneToMany: false # linksManyToMany: false dbComment: false dbCatalog : false dbSchema : false dbTable : false dbView : false dbName : false\
  dbType : false\
  dbDefaultValue: false
