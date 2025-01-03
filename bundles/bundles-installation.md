# Bundles installation

The most efficient way to use templates is to install existing bundles and then adapt them to the specific needs of the project.

Bundles of templates can be installed from a “depot”. \
A "depot" contains several bundles, which are actually Git repositories. \
A "depot" can be a **GitHub organization** or a **GitHub user** (containing a Git repository for each bundle).

### Command "lbd" <a href="#command-lmd" id="command-lmd"></a>

The "**lbd**" command means "List Bundles available in the Depot".

It can be used to see which bundles can be installed.

Syntax:   **`lbd [bundle-name-part-1] [bundle-name-part-2] [bundle-name-part-N]`**

For more convenience, you can use only a part of the bundle name. If several bundles contain this part in their name then they will all be listed.

Examples:

* **`lbd`**   -> show all available bundles&#x20;
* **`lbd java`**  -> show all available bundles with “_java_” in their name
* **`lbd java php`**  -> show all available bundles with “_java_” or "_php_" in their name

<div align="left"><figure><img src="https://res.cloudinary.com/dhcihuzk8/image/upload/v1735566885/telosys-cli-command-lbd.png" alt=""><figcaption></figcaption></figure></div>



### Command "ib" <a href="#command-im" id="command-im"></a>

The "**ib**" command means "Install Bundle(s)".\
It allows to install one or more bundles from the Depot.

Syntax:   **`ib bundle-name-part-1 [bundle-name-part-2] [bundle-name-part-N]`**

For more convenience, you can use only a part of the bundle name. If several bundles contain this part in their name then they will all be installed.

Examples:

* **`ib php`**  -> install all bundles with “_php_” in their name
* **`ib php java`** -> install all bundles with “_php_” or "_java_" in their name
* **`ib *`** -> install all bundles&#x20;

Example:  install all bundles with name containing "java"

<div align="left"><figure><img src="https://res.cloudinary.com/dhcihuzk8/image/upload/v1735567501/telosys-cli-command-ib-001.png" alt=""><figcaption></figcaption></figure></div>

Note: \
When installing bundles with the “ib” command, only bundles that do not exist locally are installed.\
In this way, it is not possible to overwrite a local bundle that may contain specialized templates for the current project.

Example:

<div align="left"><figure><img src="https://res.cloudinary.com/dhcihuzk8/image/upload/v1735567510/telosys-cli-command-ib-002.png" alt=""><figcaption></figcaption></figure></div>



### Proxy configuration

These commands must use Internet to reach the depot. \
So, if you are using a **proxy** to access Internet, you must configure it in the project configuration file. \
See "**Network proxy configuration**" in "[Project configuration](../configuration-and-variables.md)".



### Defining the depot containing the bundles

By default the depot is the GitHub organization containing the Telosys bundles examples.

You can define your own depot for bundles -> see "**SpecificDepotForBundles**" in [Project configuration](../configuration-and-variables.md)

Use the "**cfg**" command to see the current configuration including the current "depot for bundles".



### How to install a bundle with Git clone?

See  [Install with Git](../telosys-with-git/install-with-git.md) &#x20;
