# Bundle of templates

A Telosys project may require a lot templates, that's why the templates are organized in "bundles".

A "bundle" is just a set of "templates" \(and sometimes resources\) grouped together in a folder.

Thus it is possible to have clearly defined groups of templates for each part of the code to be generated \(persistence, REST-API, DTO, HTML pages, testing, etc\)

### What's in a bundle ?

Each bundle folder is supposed to contain :

* 1 file "**templates.cfg**" \(mandatory\)
* 1 file "**README.md**" \(to provide information about the bundle\)
* 1..N **templates** \(Velocity "**.vm**" files\)
* 0..N **resources** files \(static files\)
* any other useful file for the bundle
* 1..N subfolders \(to organize the different files\)

### How it works ?

All code generation is driven by the "**templates.cfg**" file.  
It is this file which defines the target files to generate, the directory in which to place the result and the templates to use.

For example, if a template \(.vm file\) is present in the bundle folder but not present in "templates.cfg", it will not be used.

The "templates.cfg" file is used to launch different types of processing defined by the last character of each line:

* "\*" : code generation executed multiple times with the same template \(1 time for each selected entity\)
* "1" : code generation executed only once independently of entities 
* "R" : simple resources files copy in a destination folder 



