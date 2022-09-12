# Project variables

Each Telosys project has a set of variables available at "**project level**".&#x20;

This is the highest level of variable definition. These variables are usable everywhere in the current project : in templates files (".vm") and in bundle configuration file ("templates.cfg").

Project variables are defined in the file "**TelosysTools/telosys-tools.cfg**".

Each line has the following syntax :

<pre><code><strong>VARIABLE_NAME = value</strong></code></pre>

Each line starting with "#" is a comment :

```
# this is a comment
```

By convention, the variables defined at project level are always in upper case.



### Standard variables&#x20;

A "standard variable" is a variable that is supposed to always be defined (for all types of projects).

Examples :

```
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



### Specific variables&#x20;

A "project-specific variable" is a variable defined for the specific needs of a project.

For example, a project variable can be defined in a project to generate PHP code and not defined in another project which aims to generate Python code.

Note : a specific variable cannot override a standard variable.

Examples :

```
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
