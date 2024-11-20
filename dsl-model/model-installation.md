# Model installation

Since version 4.2.0 it's now possible to install models from a "depot".

A "depot" is a collection of Git repositories, each repository is a "model".

### Command "lmd"

The "**lmd**" command can be used to "List Models available in the Depot"



### Command "im"&#x20;

The "**im**" command allows to install a model from the Depot"



### Proxy configuration

These commands must use Internet to reach the depot. \
So, if you are using a **proxy** to access Internet, you must configure it in the project configuration file. \
See "**Network proxy configuration**" in "[Project configuration](../configuration-and-variables.md)".



### Defining the depot containing the models

By default the depot is the GitHub organization containing the Telosys models examples.

You can define your own depot for models -> see "SpecificDepotForModels" in [Project configuration](../configuration-and-variables.md)

Use the "**cfg**" command to see the current configuration including the "depot for models".

