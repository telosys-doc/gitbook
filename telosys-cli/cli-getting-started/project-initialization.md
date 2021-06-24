# Project initialization

### At the beginning

When Telosys-CLI starts nothing is defined \( no "home directory", no "model", no "bundle", etc...\)

You can use the **`env`** command to see the current Telosys environment.

With the command **`h`** you can see that the "home directory" is not yet defined.

### Set the "home directory"

When Telosys-CLI starts its current directory is the directory where it has been launched

Use **`pwd`** to print the current working directory

Use **`cd`** to change the current directory

Once your are in the correct directory \(the directory where you want to work with Telosys\) you can use the **`h`** command to set the project's home

Examples :

**`h .`** : HOME is set to the current directory

**`h foo`** : HOME is set to the "foo" subdirectory

### Initialize the Telosys environment 

Once the "home directory" is defined, you can initialize the Telosys projet.

For that just run the **`init`** command

This command creates the "**TelosysTools**" folder containing all the Telosys files and subfolders.



### Configure the project 

Each project can be configured, for example, to define project-specific variables or to define the directory where the generated files must be created.

All the configuration of a Telosys project is defined in the "**TelosysTools/telosys-tools.cfg**" file. You can edit the "telosys-tools.cfg" file with your favorite text editor. 

To print the current configuration, use the **`cfg`** command.

To edit the configuration file with the Telosys-CLI default editor use **`ecfg`** command.

For more information about project configuration see [Configuration & variables](../../configuration-and-variables.md)



