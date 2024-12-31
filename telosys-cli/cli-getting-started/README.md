# Getting started

To start using Telosys, simply follow these 4 steps:

1. [Initialize a project ](./#id-1-initialize-a-project)
2. [Set up a model](./#id-2-set-up-a-model)&#x20;
3. [Set up a bundle of templates](./#id-3-set-up-a-bundle-of-templates)
4. [Generate your code](./#id-4-generate-your-code)

## 1 - Initialize a project

When Telosys-CLI starts nothing is defined ( no "home directory", no "model", no "bundle", etc...)

You can use the **`env`** command to see the current Telosys environment.

```
telosys>env
```

With the command **`h`** you can see that the "home directory" is not yet defined.

### 1.1 - Set the "home directory"

When Telosys-CLI starts its current directory is the directory where it has been launched

Use **`pwd`** to print the current working directory

Use **`cd`** to change the current directory

Once your are in the correct directory (the directory where you want to work with Telosys) you can use the **`h`** command to set the project's home

Example 1 : use the current directory "**.**" as HOME

```
telosys>h .
```

Example 2 : use the "**foo**" subdirectory as HOME

```
telosys>h foo
```

Once Telosys HOME is defined the prompt contains a "#"

```
telosys#>
```



### 1.2 - Initialize the Telosys project folders and files

Once the "home directory" is defined, you can initialize the Telosys projet.

For that just run the **`init`** command

```
telosys#>init
```

This command creates the "**TelosysTools**" folder containing all the Telosys files and subfolders.



### 1.3 - Configure the project&#x20;

Each project can be configured, for example, to define project-specific variables or to define the directory where the generated files must be created.

All the configuration of a Telosys project is defined in the "**TelosysTools/telosys-tools.cfg**" file. You can edit the "telosys-tools.cfg" file with your favorite text editor.&#x20;

To print the current configuration, use the **`cfg`** command.

To edit the configuration file with the Telosys-CLI default editor use **`ecfg`** command.

For more information about project configuration see [Configuration & variables](../../configuration-and-variables.md).

If you want to try Telosys quickly you can continue with the default configuration.



## 2 - Set up a model

To generate application code, you need a **model** containing the **entities** of your business domain.

There are 3 ways to set up a Telosys model :&#x20;

* **create a new model from scratch** \
  an empty model in which you can then create the entities you need&#x20;
* **create a new model from an existing relational database** : \
  a model created from the database schema (1 entity for each table)
* **install an existing model from a depot** \
  download and install a Git repository containing the model&#x20;

For more information, see pages "[Model creation](../../models/model-creation.md)" and "[Model installation](../../models/model-installation.md)"

To manage your model and its entities you can use "**Model commands**" and "**Entity commands**".\
See "[Model management](../../models/models-management.md)".



## 3 - Set up a bundle of templates

Once you have a model you need at least one **bundle of templates** to generate your code.

The templates are organized in "bundles". A **"bundle"** is a set of templates designed to generate a particular kind of targets.

Of course you can create your own templates from scatch, but the simplest way to start is to use existing templates. To do so, see "[Bundles installation](../../bundles/bundles-installation.md)"

To manage your bundles of templates you can "**Bundle commands**" and "**Template commands**".\
See "[Bundles management](../../bundles/bundles-management.md)".



## 4 - Generate your code

Once you have a **valid model** and a least one **bundle of templates**, you are **ready to generate your code**.

To generate your code you can use the following commands:

* **`gen`** to generate code with the current model and the current bundle
* **`genb`** to generate code in "batch mode" (since ver 4.1.0) with multiple models and/or bundles

See "[Code generation](../../code-generation/)".
