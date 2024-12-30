# Model installation

Since version 4.2.0 it's now possible to install models from a "depot".

A "depot" is a collection of Git repositories, each repository is a "model".

### Command "lmd"

The "**lmd**" command can be used to "List Models available in the Depot".

It can be used to see which models can be installed.&#x20;

Syntax: **`lmd [model-name-part-1] [model-name-part-2] [model-name-part-N]`**

For more convenience, you can use only a part of the model name. If several models contain this part in their name then they will all be listed.

Examples:

* **`lmd`**   -> show all available models
* **`lmd ord`**  -> show all available models with “_ord_” in their name
* **`lmd ord car`**  -> show all available models with “_ord_” or "_car_" in their name

<div align="left"><figure><img src="https://res.cloudinary.com/dhcihuzk8/image/upload/v1735579247/telosys-cli-command-lmd.png" alt=""><figcaption></figcaption></figure></div>

### Command "im"&#x20;

The "**im**" command means "Install Model(s)".\
It allows to install one or more models from the Depot.

Syntax:   **`im model-name-part-1 [model-name-part-2] [model-name-part-N]`**

For more convenience, you can use only a part of the model name. If several bundles contain this part in their name then they will all be installed.

Examples:

* **`im ord`** ->  install all models with “_ord_” in their name
* **`im ord car`** -> ->  install all models with “_ord_” or "_car_" in their name
* **`im *`** -> install all models&#x20;

Example:  install all models with name containing "_ord_"

<div align="left"><figure><img src="https://res.cloudinary.com/dhcihuzk8/image/upload/v1735579923/telosys-cli-command-im-001.png" alt=""><figcaption></figcaption></figure></div>

### Proxy configuration

These commands must use Internet to reach the depot. \
So, if you are using a **proxy** to access Internet, you must configure it in the project configuration file. \
See "**Network proxy configuration**" in "[Project configuration](../configuration-and-variables.md)".



### Defining the depot containing the models

By default the depot is the GitHub organization containing the Telosys models examples.

You can define your own depot for models -> see "SpecificDepotForModels" in [Project configuration](../configuration-and-variables.md)

Use the "**cfg**" command to see the current configuration including the "depot for models".



### How to install a model with Git clone?

See  [Install with Git](../install-with-git.md) &#x20;
