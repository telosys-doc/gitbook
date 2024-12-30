# Telosys variables

Telosys provides a set of predefined variables which can be used in all template files.

## Standard variables

Standard variables have predefined names, their values are either set by Telosys or can be defined in the project configuration.

### Special characters

These variables are used to simplify the writing of templates when certain special characters are required and are difficult to mix with Velocity syntax.

These variables should be considered as "constants" and used as such.

| Variable name                     | Variable value |
| --------------------------------- | -------------- |
| **$DOLLAR** (dollar character)    | **$**          |
| **$SHARP** (sharp character)      | **#**          |
| **$AMP** (ampersand character)    | **&**          |
| **$QUOT** (double quotation mark) | **"**          |
| **$LT** (less-than sign)          | **<**          |
| **$GT** (greater-than sign)       | **>**          |
| **$LBRACE** (left brace)          | **{**          |
| **$RBRACE** (right brace)         | **}**          |
| **$NEWLINE** (new line character) | **\n**         |
| **$TAB** (tabulation character)   | **\t**         |



### Project configuration

These variables are specific for each project. They can be defined in the project configuration file ( "telosys-tools.cfg" )

All the project configuration variables are usable in both templates files (".vm" files) and bundle configuration file ("templates.cfg").

#### Directories

| Variable name  | Configuration value                                                                                   |
| -------------- | ----------------------------------------------------------------------------------------------------- |
| **$SRC**       | <p>Directory where to generate <strong>sources</strong></p><p>e.g. "src/main/java", "src"</p>         |
| **$RES**       | <p>Directory where to generate <strong>resources</strong></p><p>e.g. "src/main/resources", "conf"</p> |
| **$WEB**       | <p>Directory where to generate <strong>web files</strong> </p><p>e.g. "src/main/webapp", "www"</p>    |
| **$TEST\_SRC** | <p>Directory where to generate <strong>test sources</strong></p><p>e.g. "src/test/java"</p>           |
| **$TEST\_RES** | <p>Directory where to generate <strong>test resources</strong></p><p>e.g. "src/test/resources"</p>    |
| **$DOC**       | <p>Directory where to generate <strong>documentation files</strong><br>e.g "doc" </p>                 |
| **$TMP**       | <p>Directory where to generate <strong>temporary files</strong> </p><p>e.g. "tmp", "temp"</p>         |

**Packages**

Variables usable for target languages having a notion of "packages" or "modules" or "namespaces" (Java, Golang, C#, etc)

| Variable name    | Configuration value                                                  |
| ---------------- | -------------------------------------------------------------------- |
| **$ROOT\_PKG**   | <p>The root package <br>containing all other packages</p>            |
| **$ENTITY\_PKG** | <p>The package containing the entities <br>classes or structures</p> |

## Specific variables

If you need more variables for your project you can define them in the project configuration file "**telosys-tools.cfg**".

Once defined, these specific variables are usable exactly like standard variables.

You can use them in both templates files (".vm" files) and bundle configuration file ("templates.cfg").

See : [Configuration and variables](../configuration-and-variables.md)

