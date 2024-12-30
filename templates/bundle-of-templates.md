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

### How to publish a bundle?

Once you've created (or customized) a bundle, you might want to publish it as a Git repository so that you can reuse it later from anywhere.

Here's the procedure to follow:

#### 1) Prepare the local Git repository&#x20;

The bundle folder will become a Git project.\
So, in the bundle folder...&#x20;

* Initialize the Git repository with initial branch “master” \
  `$ git init -b master`
* You can also define your user name and email for the current repo (optional)\
  `$ git config user.name "Your Name"` \
  `$ git config user.email your@email.com`
* Add all the bundle files to be committed \
  `$ git add .`
* Commit the files \
  `$ git commit -m "Initial commit"`

#### 2) Publish on remote repository&#x20;

On the **remote** Git server (GitHub, GitLab, your own server, etc):\
\- if you don't already have a repository to host the bundle, create it.\
\- copy the repository URL\
For example : `https://github.com/xxx/yyy.git`  \
or `https://gitlab.com/xxx/yyy.git`&#x20;

On the **local** bundle folder:

* Add the remote repository as a new remote (with name “origin”)\
  `$ git remote add origin https://xxx/yyy/repo-name.git`
* Check Git remote\
  `$ git remote -v`\
  `origin  https://xxx/yyy/repo-name.git (fetch)`\
  `origin  https://xxx/yyy/repo-name.git (push)`
* Push to remote “origin” (the GitHub repository) \
  `$ git push origin master`\
  (if not authenticated Git ask for user & password)

And that's all. \
The remote Git repository contains now all the bundle files. \
The bundle is now installable by Telosys on any workstation.

See also :\
[Adding an existing project to GitHub using the command line](https://docs.github.com/en/github/importing-your-projects-to-github/importing-source-code-to-github/adding-an-existing-project-to-github-using-the-command-line)
