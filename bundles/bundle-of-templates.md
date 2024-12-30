# Bundle structure

A Telosys project may require a lot of templates, that's why the templates are organized in "bundles".

A "bundle" is just a set of "templates" (and sometimes resources) grouped together in a folder.

Thus it is possible to have clearly defined groups of templates for each part of the code to be generated (persistence, REST-API, DTO, HTML pages, testing, etc)

### What's in a bundle ?

Each bundle folder contains:

* 1 file "**templates.cfg**" (mandatory)
* 1 file "**README.md**" (to provide information about the bundle)
* 1..N **templates** (Velocity "**.vm**" files)
* 0..N **resources** files (static files)
* any other useful file for the bundle
* 0..N subfolders (to organize the different files)

### How it works ?

All code generation is driven by the "**templates.cfg**" file.\
This file defines the target files to generate, the directory in which to place the result and the templates to use.\
For example, if a template (".vm" file) is present in the bundle folder but not present in "templates.cfg", it will not be used.

The "templates.cfg" file is used to launch different types of processing defined by the last character of each line:

* **"\*"** : \
  code generation executed **multiple times** with the same template (1 time for each selected entity)
* **"1"** : \
  code generation executed **only once** independently of entities&#x20;
* **"R"** : \
  simple **resources files** copy in a destination folder&#x20;

### How to install a bundle?





#### :heavy\_check\_mark:Installation from any Git remote repository with Git&#x20;

You can install a bundle from any Git repository just using **Git commands**.

Get the Git repository URL for the bundle to install (on your remote Git server).\
For example : `http://server-name/xxx/yyy/bundle-name.git`&#x20;

Clone the Git repository in the Telosys project **templates** **directory**.\
For example : \
`git clone http://server-name/xxx/yyy/bundle-name.git`&#x20;

There you have it. You can now use the bundle to generate your code and eventually modify it and update it on the remote Git repository (with git commit and push).

### How to customize a bundle?

Telosys was designed to allow users to customize code generation. So, if you reuse existing bundles, you will probably want to change some its parts.

What you can do:

* modify existing templates (.vm files) with a text editor
* add new templates (.vm files) in the bundle (don't forget to reference them in "templates.cfg")
* delete certain templates (in this case you can only delete the line in "templates.cfg")
* add new resources (static files) to be copied&#x20;

### How to create a new bundle?

* Create the **bundle folder** in "TelosysTools/templates"\
  (the folder name is the bundle name)
* In the new folder :\
  \- Copy an existing "**templates.cfg**" file and adapt it\
  \- Create a "**README.md**" file \
  \- Create (or copy/paste/modify) the bundle "**.vm**" files&#x20;





