# New model from database

This page describes how to create a new Telosys model from an existing relational database.

Telosys connects to the database, retrieves the database schema (structure of all tables) and creates an entity for each table with 1-N and/or N-1 links (depending on the configuration).

The auto-created model is a "raw model", you can then adjust it to your needs after creation.

### Configure your database

If your Telosys project has been correctly initialized (with "init" command) you have a "**databases.yaml**" file in the home directory.

This file contains all the configuration required to connect to one or more databases (you can have multiple databases if you want to manage multiple modes in your project).&#x20;

As a "yaml" file it can be edited with any text editor.\
You can use the "**edb**" (Edit DB) command to edit this file with the default Telosys editor.

### List the defined databases&#x20;

To see all databases currently defined you can use the "**ldb**" command (List DB)

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
