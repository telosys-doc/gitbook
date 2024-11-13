# Project databases

A Telosys project can define one or more **databases**.&#x20;

Each database can be used to create a **new model** based on its database schema (tables, relations, etc).

Project databases are defined in the file "<mark style="color:purple;">**TelosysTools/databases.yaml**</mark>".

This YAML file can edited with any editor or IDE.



### Commands for databases definition

* **`ldb`**  -> List databases defined in the current project&#x20;
* **`edb`** -> Edit "databases.yaml" file with the editor defined in Telosys-CLI configuration
* **`cdb`** ->  Check database configuration (try to connect and to get meta-data)



### YAML file structure

The file contains a list of database configurations (n items in "**`databases:`**" entry)

For each database:

* Database identification:&#x20;
  * **`id:`**   (string) a unique identifier for the database&#x20;
  * **`name:`**  (string) a name describing the database&#x20;
  * **`type:`**  (string) the database type \
    &#x20;    examples: "PostgreSQL", "MySQL", "Oracle", etc
* JDBC connection:
  * **`driver:`**  (string) the JDBC driver to use to connect to the database (driver Java class name)  \
    &#x20;    examples:  "org.postgresql.Driver"
  * **`url:`**    (string)  the JDBC URL for connection  \
    &#x20;    examples:    "jdbc:postgresql://{HOST}:{PORT}/{DATABASE}"&#x20;
  * **`user:`**  (string)  the database user name&#x20;
  * **`password:`** (string)  the database user password&#x20;
* What metadata to retrieve:
  * **`catalog:`**  (string)  the database catalog to use or  '!' for none &#x20;
  * **`schema:`** (string)  the database schema to use or  '!' for none
  * **`tableNamePattern:`**  (string) pattern used as table name filter \
    &#x20;    examples:  "%",   "ABC%",  ...&#x20;
  * **`tableNameInclude:`**  (string)  pattern used to include tables
  * **`tableNameExclude:`**  (string)  pattern used to exclude tables
  * **`tableTypes:`**  (string)  types to retrieve, separated by blanks \
    &#x20;    examples: "TABLE" (only tables),  "VIEW" (only views),  "TABLE VIEW" (tables and views)
* Options for Telosys model creation (boolean type for all):
  * **`linksManyToOne:`**  (true/false)&#x20;
  * **`linksOneToMany:`** (true/false)&#x20;
  * **`linksManyToMany:`** (true/false)&#x20;
  * **`dbComment:`** (true/false)&#x20;
  * **`dbCatalog:`** (true/false)&#x20;
  * **`dbSchema:`** (true/false)&#x20;
  * **`dbTable:`** (true/false)&#x20;
  * **`dbView:`** (true/false)&#x20;
  * **`dbName:`** (true/false)&#x20;
  * **`dbType:`** (true/false)&#x20;
  * **`dbDefaultValue:`** (true/false)&#x20;
