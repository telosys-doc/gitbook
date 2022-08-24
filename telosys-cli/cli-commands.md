# CLI commands

Telosys-CLI uses a set of short commands (based on 2 or 3 characters) to identify the action to be launched.

Most commands start with a letter which designates the action :

* **`"e"`** for "edit"
* **`"l"`** for "list"
* **`"d"`** for "delete"
* **`"n"`** for "new" ( "creation" )
* **`"c"`** for "check"
* **`"i"`** for "install"

and the second letter is used to specify on what the action is applied

* **`"m"`** for "model"
* **`"e"`** for "entity"
* **`"b"`** for "bundle of templates"
* **`"t"`** for "template" etc

Examples :

* **`"nm"`** for "new model"
* **`"dm"`** for "delete model"
* **`"ib"`** for "install bundle"
* **`"le"`** for "list entities"
* **`"eb"`** for "edit bundle"

Just press **`"?"`** to see all the available commands

Example of commands available in Telosys 4.0 :

```
telosys#> ?
General commands :
. ?    Help : Print help (list of all available commands)
. cd   Change Directory : Change the current directory
. ls   List : List the content of a directory
. mkdir Make Directory : Create a new directory in the current location
. pwd  Print Working Directory : Print the current working directory
. e    Edit : Open an external editor
. err  Error : Print details about the last error
. env  Environment : Environment state
. ver  Versions : Versions information
. q    Quit : Quit Telosys command line interface
Project commands :
. h    Home : Print or set the 'HOME' directory
. init Initialization : Init the Telosys directory with all required files
. cfg  Configuration : Print project configuration (folders, variables, etc.)
. ecfg Edit Configuration : Open an editor to edit 'telosys-tools.cfg'
Database commands :
. ldb  List Databases : List the databases
. edb  Edit Databases : Open an editor to edit 'databases.yaml' file
. cdb  Check Database : Check the current/given database
Model commands :
. m    Model : Set/print the current model
. nm   New Model : Create a new Telosys model (optionally from a database)
. lm   List Models : List the models
. em   Edit Model : Edit the current/given model
. cm   Check Model : Check the current/given model
. dm   Delete Model : Delete the current/given model
Entity commands :
. ne   New Entity : Create a new entity in the current model
. le   List Entities : List the entities defined in the current model
. ee   Edit Entity : Edit an entity file
. de   Delete Entity : Delete the given entity in the current model
GitHub commands :
. gh   GitHub : Print/Set/Reset the GitHub store name
. ghu  GitHub user : Print/Set/Clear the current GitHub user
. lgh  List GitHub : List the content of the GitHub store
. cgh  Check GitHub : Check GitHub accessibility and get API rate limit
Bundle commands :
. ib   Install Bundle : Install templates bundles from GitHub
. b    Bundle : Print or set the current bundle
. lb   List Bundles : List the installed bundles
. eb   Edit Bundle : Edit the 'templates.cfg' file of the given bundle
. db   Delete Bundle : Delete the current/given bundle
Template commands :
. lt   List Templates : List the templates for the current bundle
. et   Edit Template : Edit a template (.vm) file
Generation commands :
. gen  Generate : Generate the given targets for the given entities

```



For more information about a specific command, just press **`"? command-name"`**

For example **`"? nm"`**

```
telosys#>? nm
nm : New Model
Description :
  Create a new Telosys model (optionally from a database)
Usage :
  nm model-name [database-id]
```







