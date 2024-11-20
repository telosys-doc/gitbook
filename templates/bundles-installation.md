# Bundles installation

The most efficient way to use templates is to install existing bundles and then adapt them to the specific needs of the project.

Bundles of template can be installed from a “depot”. \
A "depot" contains several bundles, which are in fact Git repositories. \
A "depot" can be a **GitHub organization** or a **GitHub user** (containing a Git repository for each bundle).

### Command "lbd" <a href="#command-lmd" id="command-lmd"></a>

The "**lbd**" command means "List Bundles available in the Depot".

It can be used to see which bundles can be installed.

Examples:

* **`lbd`**   -> show all available bundles&#x20;
* **`lbd java`**  -> show all available bundles with “java” in their name
* **`lbd java php`**  -> show all available bundles with “java” or "php" in their name

### Command "ib" <a href="#command-im" id="command-im"></a>

The "**ib**" command means "Install Bundle(s)"&#x20;

It allows to install one or more bundles from the Depot.

Examples:

* **`ib php`**  -> install all bundles with “php” in their name
* **`ib php java`** -> install all bundles with “php” or "java" in their name
* **`ib *`** -> install all bundles&#x20;

Note: \
When installing bundles with the “ib” command, only bundles that do not exist locally are installed.\
In this way, it is not possible to overwrite a local bundle that may contain specialized templates for the current project.

Example:

`Installing 4 bundle(s) from depot...` \
`. 'java-domain-example' :`` `**`not installed (already exists)`**`.` \
`. 'java-jdbc' :`` `**`not installed (already exists)`**`.` \
`. 'java-jpa-entities' :`` `**`installed`**`.` \
`. 'java-rest-springboot-jpa-basic' :`` `**`not installed (already exists)`**`.`



### Proxy configuration

These commands must use Internet to reach the depot. \
So, if you are using a **proxy** to access Internet, you must configure it in the project configuration file. \
See "**Network proxy configuration**" in "[Project configuration](../configuration-and-variables.md)".



### Defining the depot containing the bundles

By default the depot is the GitHub organization containing the Telosys bundles examples.

You can define your own depot for bundles -> see "**SpecificDepotForBundles**" in [Project configuration](../configuration-and-variables.md)

Use the "**cfg**" command to see the current configuration including the current "depot for bundles".


