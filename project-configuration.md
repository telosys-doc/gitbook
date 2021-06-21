# Configuration & variables

The project configuration is centralized in a single file :  
**TelosysTools/telosys-tools.cfg**

This file is a "properties file" \(i.e. a file containing parameters with their value\).

Each line has the following syntax :

```text
name = value
```

Each line starting with a "\#" is a comment :

```text
# this is a comment
```

Each parameter can be :

* a standard variable
* a specific variable
* a specific location \(a folder where to get the templates or where to generate the files\)
* a network proxy setting \(for templates installation via http\)

With Telosys-CLI you can print the current configuration using the `cfg` command.

### Variables 

By convention, the variables defined at the project level are always in upper case. All the defined variables \(standard & specific\) are visible and usable in templates \(".vm" files\). They can also be used in the "templates.cfg" file in bundles of templates. 



### Standard variables 

A "standard variable" is a variable which is supposed to be defined in most cases \(for all types of projects\).

Examples :

```text
# -------------------------------------------
# STANDARD VARIABLES 
# -------------------------------------------
# --- Folders 
SRC      = src/main/java
RES      = src/main/resources
WEB      = src/main/webapp
TEST_SRC = src/test/java
TEST_RES = src/test/resources
DOC      = doc
TMP      = tmp
# --- Packages
ROOT_PKG = org.foo.bar
```

### Specific project variables 

A "project-specific variable" is a variable defined specifically for the current project. For example, a project variable can be defined in a project to generate PHP code and not defined in another project which aims to generate Python code.

Note : a project variable cannot override a standard variable.

Examples :

```text
# -------------------------------------------
# SPECIFIC VARIABLES 
# -------------------------------------------
# Project configuration :
ProjectVariable.PROJECT_NAME    = cool-project
ProjectVariable.MAIN_ENTITY     = Employee
ProjectVariable.PROJECT_VERSION = 1.0.0-SNAPSHOT
ProjectVariable.MAVEN_GROUP_ID  = com.foo.bar

# Modules directories :
ProjectVariable.MICROSERVICE_DIR  = employee-ms
ProjectVariable.APPLICATION_DIR   = application
ProjectVariable.COMMONS_DIR       = commons
```

### Specific folders

In the configuration file you can define the following specic folders :

* **SpecificTemplatesFolder** : Specific location for templates
* **SpecificDestinationFolder**  : Specific destination for code generation

Examples :

```text
#-- Specific location for templates (Windows) :
SpecificTemplatesFolder=C\:\\dir1\\dir2

#-- Specific location for templates (Linux) :
SpecificTemplatesFolder=/dir1/dir2

#-- Specific destination for code generation (Windows) :
SpecificDestinationFolder=C\:\\dir1\\dir2

#-- Specific destination for code generation (Linux) :
SpecificDestinationFolder=/dir1/dir2
```







