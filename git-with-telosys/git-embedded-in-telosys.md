# Git embedded in Telosys

Since version 4.3.0 Telosys-CLI is able to execute Git commands by itself, \
even if no Git tool is intalled on your workstation.

**Git is embedded in Telosys-CLI** in order to simplify Git usage to **clone**, **init** and **publish** models and bundles repositories.

&#x20;**`git`**  is the command to execute git operations.

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

**🔹 `git clonem`** _`model-name-in-depot`_` ``|or|`` `_`any-repo-url`_

* Examples:&#x20;
  * clone by name:\
    &#x20;`git clonem cars`      &#x20;
  * clone by URL:\
    &#x20;`git clonem https://github.com/telosys-models-v4-3/employees`&#x20;

**Clone a bundle repository with "**<mark style="color:red;">**cloneb**</mark>**"**&#x20;

**🔹 `git cloneb`** _`bundle-name-in-depot`_` ``|or| any-repo-url`

* Examples:&#x20;
  * clone by name:\
    &#x20;`git cloneb front-angular`&#x20;
  * clone by URL:\
    `git cloneb https://github.com/telosys-templates-v4-3/java-jpa-entities`

### Init a new Git repository

After installing or creating a model or bundle you must create its Git repository.

**Init a model repository with "**<mark style="color:red;">**initm**</mark>**"**&#x20;

&#x20;**🔹 `git initm`**  _`[model-name]`_

* Examples:
  * x
  *

**Init a bundle repository with "**<mark style="color:red;">**initb**</mark>**"**&#x20;

&#x20;**🔹 `git initb`**  _`[bundle-name]`_

* Examples:
  * x

### Check current status

**Check a model repository status with "**<mark style="color:red;">**statusm**</mark>**"**

&#x20;**`git statusm`**  _`[model-name]`_

* Examples:
  * x
  *

**Check a bundle repository status with "**<mark style="color:red;">**statusb**</mark>**"**

**`git statusb`**  _`[bundle-name]`_

* Examples:
  * x
  *

