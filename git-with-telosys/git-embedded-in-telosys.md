# Git embedded in Telosys

Since version 4.3.0 Telosys-CLI is able to execute Git commands by itself, \
even if no Git tool is intalled on your workstation.

**Git is embedded in Telosys-CLI** in order to simplify Git usage to **clone**, **init** and **publish** models and bundles repositories.

<mark style="color:red;">**`git`**</mark>  is the command to execute git operations.

For help with Git commands, type   **`? git`**   in Telosys-CLI .

All git commands are designed to work with **Telosys models and bundles**:

* Commands ending with "**m**" are for **models**
* Commands ending with "**b**" are for **bundles**

{% hint style="info" %}
The **remote repository** is defined from the current "**depot**" configuration.\
To define a specific depot for models or bundles, see  [configuration-and-variables.md](../configuration-and-variables.md "mention")&#x20;
{% endhint %}

### Clone an existing Git repository

This command allows to clone a repository from the current "depot" or from a specific URL.

**Clone a model repository with "**<mark style="color:red;">**clonem**</mark>**"**

**🔹 `git clonem`` `**_**`model-name-in-depot`**_` ``|or|`` `_**`any-repo-url`**_

* Examples:&#x20;
  * clone by name:\
    &#x20;`git clonem cars`      &#x20;
  * clone by URL:\
    &#x20;`git clonem https://github.com/telosys-models-v4-3/employees`&#x20;

**Clone a bundle repository with "**<mark style="color:red;">**cloneb**</mark>**"**&#x20;

**🔹 `git cloneb`` `**_**`bundle-name-in-depot`**_` ``|or|`` `_**`any-repo-url`**_

* Examples:&#x20;
  * clone by name:\
    &#x20;`git cloneb front-angular`&#x20;
  * clone by URL:\
    `git cloneb https://github.com/telosys-templates-v4-3/java-jpa-entities`

### Init a new Git repository

After installing or creating a new model or bundle you can create the Git repository with "initm" or "initb".

**Init a model repository with "**<mark style="color:red;">**initm**</mark>**"**&#x20;

&#x20;**🔹 `git initm`` `**_**`[model-name]`**_

* Examples:&#x20;
  * init the current model (without parameter)\
    `git initm`
  * init a specific model\
    `git initm pizzas`

**Init a bundle repository with "**<mark style="color:red;">**initb**</mark>**"**&#x20;

&#x20;**🔹 `git initb`` `**_**`[bundle-name]`**_

* Examples:
  * init the current bundle (without parameter)\
    `git initb`
  * init a specific bundle\
    `git initb database-sql-liquibase`

### Check current status

**Check a model repository status with "**<mark style="color:red;">**statusm**</mark>**"**

&#x20;**🔹 `git statusm`` `**_**`[model-name]`**_

* Examples:&#x20;
  * get the status of the current model (without parameter)\
    `git statusm`
  * get the status of a specific model\
    `git statusm cars`

**Check a bundle repository status with "**<mark style="color:red;">**statusb**</mark>**"**

&#x20;**🔹 `git statusb`` `**_**`[bundle-name]`**_

* Examples:
  * get the status of the current bundle (without parameter)\
    `git statusb`
  * get the status of a specific bundle \
    `git statusb front-angular`

### Publish all changes to remote repository

The "**pub\[m/b]**" command allow to perform several "Git" actions with a single command:

* **git add** \
  Adds all the changes to the index&#x20;
* **git commit**  \
  Creates a new commit containing the current contents of the index\
  It uses a default message
* **git push**  \
  Pushes to the remote repository according with the current "depot" definition

With this command you just have to:

* edit the model or the bundle
* use "git pub\[m/b]" to publish it on the remote server

{% hint style="info" %}
Before using the "git pub\[m/b]" command, ensure that the remote repository exists in the "depot".\
If the remote Git repository does not yet exist, create it.\
You can do that with the web GUI on GitHub, GitLab, your own server, etc...
{% endhint %}

**Publish a model repository status with "**<mark style="color:red;">**pubm**</mark>**"**

&#x20;**🔹 `git pubm`` `**_**`[model-name]`**_

* Examples:&#x20;
  * publish the current model (without parameter)\
    `git pubm`
  * publish a specific model\
    `git pubm pizzas`

**Publish a bundle repository status with "**<mark style="color:red;">**pubb**</mark>**"**

&#x20;**🔹 `git pubb`` `**_**`[bundle-name]`**_

* Examples:
  * publish the current bundle (without parameter)\
    `git pubb`
  * publish a specific bundle\
    `git pubb database-sql-liquibase`

### Reset from remote repository

The "**reset\[m/b]**" command allows to perform 2 "Git" actions with a single command:

* **git fetch**\
  Fetch the branch from the remote repository&#x20;
* **git reset --mixed** \
  Resets the index but **not the working tree** (changed files are preserved but not marked for commit)

In brief: make the branch match remote, keep changes unstaged, forget old commits.\
This command is useful in case of "**REJECTED\_NONFASTFORWARD**" error \
when attempting to push the changes to a remote server with "**git pub\[m/b]**" command.

**Reset a model repository with "**<mark style="color:red;">**resetm**</mark>**"**

&#x20;**🔹 `git resetm`` `**_**`[model-name]`**_

* Examples:&#x20;
  * reset the current model (without parameter)\
    `git resetm`
  * reset a specific model\
    `git resetm cars`

**Reset a bundle repository with "**<mark style="color:red;">**resetb**</mark>**"**

&#x20;**🔹 `git resetb`` `**_**`[bundle-name]`**_

* Examples:
  * reset the current bundle (without parameter)\
    `git resetb`
  * reset a specific bundle \
    `git resetb front-angular`

### Git credentials management&#x20;

Credentials are required for Git remote repository operations, \
the "**git cred**" commands allows to print, set and remove credentials.

You can define credentials at different levels:

* "**global credentials**" used for both models and bundles (the most frequent case)
* "**model credentials**" used only for models
* "**bundle credentials**" used only for bundles

{% hint style="info" %}
The credentials are encrypted and stored on the workstation.\
They can be used by all telosys projects.
{% endhint %}

To show all credentials settings (password or token are not printed, just "set" or "not set"):

**🔹 `git cred`**   show **all** credentials (all levels)

**🔹 `git credg`**  show the "**global**" credentials (for both models and bundles)

**🔹 `git credm`**  show the credentials for "**models**"

**🔹 `git credb`**  show the credentials for "**bundles**"

To set the credentials use **`-set`**  parameter \
and enter the requested information:

* User name&#x20;
* Password or personal access token (PAT) &#x20;

To remove the credentials use **`-none`**  parameter



