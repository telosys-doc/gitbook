# CLI commands

Telosys-CLI uses a set of short commands (based on 2 or 3 characters) to identify the action to be launched.

Most commands start with a letter which designates the **action**&#x20;

* **`"e"`** for "edit"
* **`"l"`** for "list"
* **`"d"`** for "delete"
* **`"n"`** for "new" ( "creation" )
* **`"c"`** for "check"
* **`"i"`** for "install"

and the second letter is used to specify **on what** the action is applied

* **`"m"`** for "model"
* **`"e"`** for "entity"
* **`"b"`** for "bundle of templates"
* **`"t"`** for "template" etc

Examples :

* **`"nm"`** for "**n**ew **m**odel"
* **`"dm"`** for "**d**elete **m**odel"
* **`"ib"`** for "**i**nstall **b**undle"
* **`"le"`** for "**l**ist **e**ntities"
* **`"eb"`** for "**e**dit **b**undle"

Just press **`"?"`** to see all the available commands

Example of commands available in Telosys 4.2.0:

```
telosys#> ?
General commands :
. ?    Help : Print help (list of all available commands)
. cd   Change Directory : Change the current directory
. ls   List : List the content of a directory
. mkdir Make Directory : Create a new directory in the current location
. pwd  Print Working Directory : Print the current working directory
. e    Edit : Open an external editor
. fx   File Explorer : Open a file explorer in the current directory
. err  Error : Print details about the last error
. env  Environment : Environment state
. proxy Proxy configuration : Get current proxy configuration
. ver  Versions : Versions information
. q    Quit : Quit Telosys command line interface
. exit Exit : Exit Telosys command line interface
Project commands :
. h    Home : Print or set the 'HOME' directory
. init Initialization : Init the Telosys directory with all required files
. cfg  Configuration : Print project configuration (folders, variables, etc.)
. ecfg Edit Configuration : Open an editor to edit 'telosys-tools.cfg'
Database commands :
. ldb  List Databases : List the databases configurations
. edb  Edit Databases : Open an editor to edit 'databases.yaml' file
. cdb  Check Database : Check database configuration : try to connect and get metadata
Model commands :
. m    Model : Set/print the current model
. lm   List Models : List the project models
. lmd  List Models in Depot : List models available in the depot
. im   Install Model(s) : Install model(s) from the depot
. nm   New Model : Create a new Telosys model (optionally from a database)
. em   Edit Model : Edit the current/given model
. cm   Check Model : Check the current/given model
. dm   Delete Model : Delete the current/given model
Entity commands :
. le   List Entities : List the entities defined in the current model
. ee   Edit Entity : Edit an entity file
. ne   New Entity : Create a new entity in the current model
. de   Delete Entity : Delete the given entity in the current model
Bundle of templates commands :
. b    Bundle : Print or set the current bundle
. lb   List Bundles : List the project bundles
. lbd  List Bundles in Depot : List bundles of templates available in the depot
. ib   Install Bundle(s) : Install bundle(s) of templates available in the depot
. eb   Edit Bundle : Edit the 'templates.cfg' file of the given bundle
. db   Delete Bundle : Delete the current/given bundle
Template commands :
. lt   List Templates : List the templates for the current bundle
. et   Edit Template : Edit a template (.vm) file
Generation commands :
. gen  Generate : Generate the given targets for the given entities
. genb Generation in batch mode : Launch generation for many models and many bundles
GitHub commands :
. ght  GitHub Token : Set or remove the current GitHub personal access token (PAT)
. cgh  Check GitHub : Check GitHub accessibility and get API rate limit

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







