# Project databases

A Telosys project can define one or more **databases**.&#x20;

Each database can be used to create a **new model** based on its database schema (tables, relations, etc).

Project databases are defined in the file "<mark style="color:purple;">**TelosysTools/databases.yaml**</mark>".

This YAML file can be edited with any editor or IDE.



### Commands for databases definition

* **`ldb`**  -> List databases defined in the current project&#x20;
* **`edb`** -> Edit "databases.yaml" file with the editor defined in Telosys-CLI configuration
* **`cdb`** ->  Check database configuration (try to connect and to get meta-data)



### YAML file structure

The file contains a list of database configurations (n items in "**`databases:`**" entry)

For each database entry:

* Database identification:&#x20;
  * **`id:`**   (string) a unique identifier for the database&#x20;
  * **`name:`**  (string) a name describing the database&#x20;
  * **`type:`**  (string) the database type \
    &#x20;    examples: "PostgreSQL", "MySQL", "Oracle", etc
* JDBC connection:
  * **`driver:`**  (string) the JDBC driver to use to connect to the database (driver Java class name)  \
    &#x20;    examples:  "org.postgresql.Driver",  "org.mariadb.jdbc.Driver"
  * **`url:`**    (string)  the JDBC URL for connection  \
    &#x20;    examples:    "jdbc:postgresql://{HOST}:{PORT}/{DATABASE}"&#x20;
  * **`user:`**  (string)  the database user name&#x20;
  * **`password:`** (string)  the database user password&#x20;
* What tables to retrieve - first level filter:
  * **`catalog:`**  (string)  the database catalog to use or  '!' for none &#x20;
  * **`schema:`** (string)  the database schema to use or  '!' for none
  * **`tableNamePattern:`**  (string) pattern used as table name filter \
    &#x20;    examples:  "%",   "ABC%",  ...&#x20;
  * **`tableTypes:`**  (string)  types to retrieve, separated by blanks \
    &#x20;    examples: "TABLE" (only tables),  "VIEW" (only views),  "TABLE VIEW" (tables and views)
* What tables to retrieve - second level filter (applied on the result of the first level filter)
  * **`tableNameExclude:`**  (string)  regular expression used to exclude tables
  * **`tableNameInclude:`**  (string)  regular expression used to include tables
* Options for Telosys model creation ("boolean" type for all):
  * **`linksManyToOne:`**  (default = true)  create "**ManyToOne**" **links** in model entities
  * **`linksOneToMany:`** (default = false)  create "**OneToMany**" **links** in model entities
  * **`linksManyToMany:`** ( default = false)  create "**ManyToMany**" **links** in model entities
  * **`dbComment:`** (default = true)  create **@DbComment(...)** annotation (entity & attribute level)
  * **`dbCatalog:`** (default = true)  create **@DbCatalog(...)** annotation (entity level)
  * **`dbSchema:`** (default = true) create **@DbSchema(...)** annotation (entity level)
  * **`dbTable:`** (default = true) create **@DbTable(...)** annotation (entity level)
  * **`dbView:`** (default = true) create **@DbView(...)** annotation (entity level)
  * **`dbName:`** (default = true) create **@DbName(...)** annotation (attribute level)
  * **`dbType:`** (default = true)  create **@DbType(...)** annotation (attribute level)
  * **`dbDefaultValue:`** (default = true) create **@DbDefaultValue(...)** annotation (attribute level)



### Setting up the JDBC driver library

After defining the database in "databases.yaml" you also need to set up the **Java library** containing the **JDBC driver**.

The Java library is the "**.jar**" file (sometimes ".zip") provided by the database supplier.

JDBC library files examples:\
&#x20;   \-  `postgresql-42.2.26.jre7.jar` \
&#x20;   \-  `mariadb-java-client-3.1.0.jar`

Put the "**.jar**" file in  "<mark style="color:purple;">**TelosysTools/lib**</mark>" directory so that Telosys can use it.



### Check database configuration

Once a database has been defined in "databases.yaml", it is recommended to test the database configuration using the "**cdb**" command.

* Check if it is possible to connect to the database\
  &#xNAN;**`cdb <dbid>`**
* Check **tables** retrieved ->  **`-t`**\
  &#xNAN;**`cdb <dbid>`**<mark style="color:purple;">**`-t`**</mark>
* Check **columns** retrieved ->  **`-c`**\
  &#xNAN;**`cdb <dbid>`**<mark style="color:purple;">**`-c`**</mark>
* Check **primary keys** retrieved ->  **`-pk`**\
  &#xNAN;**`cdb <dbid>`**<mark style="color:purple;">**`-pk`**</mark>
* Check **foreign keys** retrieved ->  **`-fk`**\
  &#xNAN;**`cdb <dbid>`**<mark style="color:purple;">**`-fk`**</mark>
* Get database **shemas**  ->  **`-s`**\
  &#xNAN;**`cdb <dbid>`**<mark style="color:purple;">**`-s`**</mark>
* Get database **catalogs** ->  **`-cat`**\
  &#xNAN;**`cdb <dbid>`**<mark style="color:purple;">**`-cat`**</mark>

When all checks are OK, you are ready to create a model from the database.



### Create a new model from a database

To create a new model from one of the databases defined in "databases.yaml" you just have to use the "nm" (New Model) command.

See "[Model creation](../models/model-creation.md)"
