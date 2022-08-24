# New model from database

This page describes how to create a new Telosys model from an existing relational database.

Telosys connects to the database, retrieves the database schema (structure of all tables) and creates an entity for each table with 1-N and/or N-1 links (depending on the configuration).

The auto-created model is a "raw model", you can then adjust it to your needs after creation.

### Configure your database

If your Telosys project has been correctly initialized (with "init" command) you have a "**databases.yaml**" file in the home directory.

This file contains all the configuration required to connect to one or more databases (you can have multiple databases if you want to manage multiple modes in your project).&#x20;

As a "yaml" file it can be edited with any text editor.\
You can use the "**edb**" (Edit DB) command to edit this file with the default Telosys editor.

#### Configuration attributes for each database :&#x20;

Database id and information

* **id**  : a string that identifies the database (required, must be unique)
* **name** : the database name (optional, just for information)&#x20;
* **type** : the database type (optional, just for information)&#x20;

Database JDBC configuration :&#x20;

* **driver** : the JDBC driver class name (required)
* **url** : the JDBC URL to access the database (required)
* **user** : the database user (required)
* **password** :  the database user's password (required)

Database metadata configuration :&#x20;

* **catalog** :  the catalog where to search the metadata (optional) \
  catalog name or "!" for "null"  ("null" is sometimes needed for certain types of databases)
* **schema** :  the schema where to search the metadata  (optional)  \
  schema name or "!" for "null"  ("null" is sometimes needed for certain types of databases)
* **tableTypes** : types of table to retrieve, separated by blanks (optional)\
  examples : "TABLE" = only tables,   "TABLE VIEW" = tables and views&#x20;
* **tableNamePattern** : the pattern used as table name filter (optional)\
  examples : "%",  "A%", ...
* **tableNameExclude** : the pattern used to exclude some tables (optional)
* **tableNameInclude** : the pattern used to include some tables (optional)



### List the defined databases&#x20;

To see all databases currently defined you can use the "**ldb**" command (List DB).

The configuration is printed for each defined database.

### Provide the JDBC driver&#x20;

Telosys needs a JDBC driver to be able to connect to the database. \
So put the "**.jar**" file containing the **JDBC driver** class in the "lib" folder. \
For example, for a "Derby" database put the "derbylient.jar" in "**TelosysTools/lib**".

### Check the database connection

Once the database is defined in the "databases.yaml" file and its driver .jar file is available in the "lib" folder you can check the connection.&#x20;

To check the connection use the "**cdb**" command (Check DB) \
Example :&#x20;

```
telosys#>cdb mydb
Checking database 'mydb'...
```

### Create the new model from the database schema

Once you have validated the connection to the database you are ready to create a new model from the database.

To do this, use the "**nm**" ("New Model") command with the database-id as an argument (the database-id defined in "databases.yaml").\
Example :&#x20;

```
telosys#>nm mymodel mydb
```

The created model is a standard Telosys model with exactly the same syntax as if it has been created manually.

You can see the result with commands "lm" and "le".

### Adapt the created model

Once the "raw model" has been created by Telosys, you can check it and adapt it if necessary.
