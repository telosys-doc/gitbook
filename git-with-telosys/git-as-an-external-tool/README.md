# Git as an external tool

Prior to version 4.3.0, the only way to manage Git repositories was to use a Git tool external to Telosys.

Below you will find the git commands useful for this.

{% hint style="info" %}
All the following **git command** examples are meant to be used with a standard **operating-system shell** \
(not in Telosys-CLI )
{% endhint %}

### Check and configure Git

Verify that the Git command is available.\
`$`` `**`git --version`**

Verify your user name and email at global level \
`$``  `**`git config --global -l`**

Define your user name and email at global level (if necessary)\
`$`` `**`git config --global user.name "Your Name"`**\
`$`` `**`git config --global user.email your@email.com`**

### Clone an existing Git repository

If you plan to customize an existing model or bundle of templates, it may be more efficient to clone the Git repository so that you can then publish the changes more easily.

You can install a model or a bundle from any Git repository just using Git commands.&#x20;

* On the Git server (GitHub, GitLab, your own server, etc) \
  get the **Git URL** for the repository to install (on your remote Git server). \
  For example:  **`http://server-name/xxx/yyy/repo-name.git`**
* Go into the models or bundles directory\
  `$`**`cd TelosysTools\models`**  \
  or  `$`**`cd TelosysTools\templates`**
* Clone the Git repository in the models or bundles directory\
  `$`**`git clone http://server-name/xxx/yyy/repo-name.git`**

After a "git clone" the model or bundle is installed and ready to use.\
It works as a standard model/bundle, but it has Git repository, so it is ready for "commit" and "push" to publish your changes.

### Init a new Git repository

After installing or creating a model or bundle you must create its Git repository.

* Go into the model or bundle directory\
  `$`**`cd TelosysTools\models\mymodel`**  \
  or  `$`**`cd TelosysTools\templates\mybundle`**
* Init the new Git repository\
  `$`**`git init -b master`**

### Commit your changes

Preliminary note: \
if you want to define a specific user name and email for the **current repository** \
`$`` `**`git config`` `**<mark style="color:red;">**`--local`**</mark>**` ``user.name "Your Name"`**\
`$`` `**`git config`` `**<mark style="color:red;">**`--local`**</mark>**` ``user.email your@email.com`**

🔹Add all the files to be committed (usually all files)\
`$`**`git add .`**

🔹Commit the files \
`$`**`git commit -m "My commit message"`**

### Check the remote repository&#x20;

If the remote Git repository does not yet exist, create it.\
You can do that with the web GUI on GitHub, GitLab, your own server, etc...

Check and configure the Git remote repository:

🔹Check Git remote\
`$`**`git remote -v`**\
`origin  https://xxx/yyy/repo-name.git (fetch)`\
`origin  https://xxx/yyy/repo-name.git (push)`

🔹Add the remote repository if necessary \
`$`**`git remote add origin https://xxx/yyy/repo-name.git`** \
(you can copy/paste the repository URL)

### Push to the remote repository&#x20;

Push to “origin” (remote-side) a branch of your repository (for example “master”)\
`$`**`git push origin master`**\
(if not authenticated Git ask for user & password)

