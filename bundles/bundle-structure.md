# Bundle structure

A Telosys project may require a lot of templates, that's why the templates are organized in "**bundles**".

A "bundle" is just a set of "templates" (and sometimes resources) grouped together in a folder.

Thus it is possible to have clearly defined groups of templates for each part of the code to be generated (persistence, REST-API, DTO, HTML pages, testing, etc)

<div align="left"><figure><img src="https://res.cloudinary.com/dhcihuzk8/image/upload/v1735580497/bundle-struct-001.png" alt=""><figcaption></figcaption></figure></div>

### What's in a bundle ?

Each bundle folder contains:

* 1 file "**templates.cfg**" (mandatory)
* 1 file "**README.md**" (to provide information about the bundle, optional)
* 1..N **templates** (Velocity "**.vm**" files)
* 0..N **resources** files (static files)
* any other useful file for the bundle
* 0..N subfolders (to organize the different files)



### The "templates.cfg" file&#x20;

All code generation is driven by the "**templates.cfg**" file. &#x20;

Each line of this file defines a genaration task with the necessary information:

* the **target file(s)** to generate
* the **target directory** in which to place the result&#x20;
* the **template** to use&#x20;
* the **type of execution**:
  * **"\*"** :  a code generation executed **multiple times** with the same template \
    (1 generation for each selected entity)
  * **"1"** :  a code generation executed **only once** independently of entities&#x20;
  * **"R"** :  a simple **resources files** copy in a destination folder (no template)

NB:  if a template (".vm" file) is present in the bundle folder but not present in "templates.cfg", it will not be used.



### Variables usable in "templates.cfg"&#x20;

For greater flexibility, variables can be used in the **target file name** and the **target directory name**.

* **${ENT}**  ⇒  current **entity name**  (since ver 4.2.0 )\
  this variable is required for generation with type "\*" in order to generate a file for each entity
* _**${BEANNAME}**_ ⇒ same as **${ENT}** deprecated since ver 4.2.0 ⇒ use ${ENT} instead
* **${BUN}** ⇒ current **bundle name**  (since ver 4.2.0 )
* **${MOD}** ⇒ current **model name**  (since ver 4.2.0 )

The following suffixes can be added to all of these variables:

* "**\_LC**" ⇒ conversion to "**lower case**".   Examples:  ${ENT\_LC},  ${MOD\_LC}
* "**\_UC**" ⇒ conversion to "**upper case**".   Examples:  ${ENT\_UC},  ${MOD\_UC}

It is also possible to use any variables defined in the **project configuration**:

* **standard predefined variables** \
  like ${SRC}, ${RES}, ${WEB}, ${TEST\_SRC}, ${TEST\_RES}, ${DOC}, ${TMP}
* all other **specific variables**



### How to customize a bundle?

Telosys was designed to allow users to customize code generation. So, if you reuse existing bundles, you will probably want to change some its parts.

What you can do:

* modify existing templates (.vm files) with a text editor
* add new templates (.vm files) in the bundle (don't forget to reference them in "templates.cfg")
* delete certain templates (in this case you can only delete the line in "templates.cfg")
* add new resources (static files) to be copied&#x20;



### How to use Git to clone and push a bundle ?

See  [Install with Git](../git-with-telosys/git-as-an-external-tool/clone-with-git.md)  and  [Publish with Git](/broken/pages/aAH24lA3MNXizn2RPiS1)



