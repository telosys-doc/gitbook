# Model creation

There are 2 ways to create a Telosys model :&#x20;

* **creation from scratch** \
  to create an empty model in which you can then create the entities you need&#x20;
* **creation from an existing relational database** \
  to create a model from a database with an entity for each table



### Creating a model from scratch&#x20;

**Step #1 - Create a void model**

To create a model from scratch use the "**nm**" (New Model) command.

Syntaxe:

**`nm  <model-name>`**&#x20;

&#x20;     \<model-name>   -> the name of the new model to create

This command creates a new model with the given name.

This model is void, it does not contain any entity.

**Step #2 - Add entities to the model**

To add entities, use the "ne" (New Entity) command.

Syntaxe:

**`ne  <entity-name>`**&#x20;

This command creates a new entity with the given name -> a file "**entity-name.entity**"

You can now edit the ".entity" files of the model with any editor or IDE to define the attributes and links.

You can also "copy/paste" certain files if you have similarities between entities.



### Creating a model from a database

If you have a relational database with tables and links based on foreign keys then you have a relationship model.  Telosys is able to build its own model from this  database model.

To do so, you just have to define your database -> see the page "[Project databases](../project-databases.md)"

Once you have define the database and check the configuration with "cdb" command you can create a Telosys model from this database with the "**nm**" command.

Syntaxe:

**`nm  <model-name>  <database-id>`**

&#x20;     \<model-name>   -> the name of the new model to create

&#x20;     \<database-id>   -> the id of a database defined in "databases.yaml"

An entity will be created for each table matching the patterns defined in the database configuration.

You can check the entities created and if necessary you can customize them by editing the ".entity" files.&#x20;



