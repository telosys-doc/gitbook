# Database model

This step describe how to create a new model from an existing database.

Before continuing ensure your home directory is defined and the project has been initialized.

### Configure your database

Edit the **`databases.dbcfg`** XML file to define a new database configuration.

Launch the external editor with the **`edb`** (**Edit DB**) command in Telosys-CLI or if you are in your prefered editor (Atom, VSCode, etc) just open the **`databases.dbcfg`** file.

In **`databases.dbcfg`** add a new **`<db>`** tag with all the expected information (use the examples of databases configuration available in the commented lines of the file).

For each database you must define the following attributes :

* **`id`** an integer that identifies the database (from 0 to N)
* **`name`** the database name (just for information, you can use any name)
* **`driver`** the JDBC driver class name
* **`url`** the JDBC URL to access the database

If you plan to generate code for JPA you can also define :

* **`typeName`** the type of database (eg "POSTGRESQL", "DERBY", "H2", "ORACLE", etc)
* **`dialect`** the JPA dialect (eg "org.hibernate.dialect.MySQLDialect")

Set the following JDBC properties ( in a **`<property>`** tag ) :

* property name **`user`** the database user
* property name **`password`** the database user's password
* if necessary you can define any other JDBC specific properties required by your database

Define the following information used to retrieve the JDBC METADATA ( in the **`<metadata>`** tag ):

* **`catalog`** the database catalog to be used if any ("" for void, "!" for null)
* **`schema`** the database schema containing the tables you want to use ("" for void, "!" for null)
* **`table-name-pattern`** the pattern to filter the tables names (eg "%" for all tables )
* **`table-types`** the type of tables to be used (eg "TABLE VIEW", "TABLE", "VIEW")
* **`table-name-exclude`** a pattern to exclude some tables (usually void)
* **`table-name-include`** a pattern to include some tables (usually void)

### List the defined databases

To see all databases currently defined you can use the **`ldb`** command (**List DB**)

### Provide the JDBC driver

Telosys needs a JDBC driver to be able to connect to the database.

So put the **".jar" file** containing the **JDBC driver class** in the **"lib"** folder.

For example, for a "Derby" database put the "derbylient.jar" in "TelosysTools/lib".

### Check the database connection

Once the database is defined in the **`databases.dbcfg`** file and its driver **`.jar`** file is available in the **"lib"** folder you can check the connection.

To check the connection use the **`cdb`** command (**Check DB**)

You can use **`cdb`** with or without the database id :

* **`cdb`** without argument will check the default database
* **`cdb 2`** with argument "2" will check the database with id "2"

### Create your model from the database schema

Once you have validated the connection to the database you are ready to generate the model.

To create a new "db model" use the **`ndbm`** command (**New DB Model**)

You can use **`ndbm`** with or without the database id :

* **`ndbm`** without argument will create a model from the default database
* **`ndbm 2`** with argument "2" will create a model from the database with id "2"

### Commands summary

* **`edb`** Edit DB
* **`ldb`** List DB
* **`cdb`** Check DB
* **`ndbm`** New DB Model

Use **`? command-name`** to get help
