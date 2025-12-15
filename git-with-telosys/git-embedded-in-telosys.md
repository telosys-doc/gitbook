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
The **remote repository** is defined from the current "**depot**" configuration
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

After installing or creating a model or bundle you must create its Git repository.

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

&#x20;**🔹 `git statusb``  `**_**`[bundle-name]`**_

* Examples:
  * get the status of the current bundle (without parameter)\
    `git statusb`
  * get the status of a specific model\
    `git statusb front-angular`

### Publish all changes to remote repository

**Publish a model repository status with "**<mark style="color:red;">**pubm**</mark>**"**

&#x20;**🔹 `git pubm`` `**_**`[model-name]`**_

**Publish a bundle repository status with "**<mark style="color:red;">**pubb**</mark>**"**

&#x20;**🔹 `git pubb``  `**_**`[bundle-name]`**_

The "pub\[m/b]" command allow to perform several "Git" actions with a single command:

* **git add** \
  Adds all the changes to the index&#x20;
* **git commit**  \
  Creates a new commit containing the current contents of the index\
  It uses a default message
* **git push**  \
  Pushes to the remote repository according with the current "depot" definition

xx



