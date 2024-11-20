# Set up a bundle of templates

Once you have a model you need at least one **bundle of templates** to generate your code.

The templates are organized in "bundles". A **"bundle"** is a set of templates designed to generate a particular kind of targets.

Of course you can create your own templates from scatch, but the simplest way to start is to use existing templates. To do so, see "[Bundles installation](../../templates/bundles-installation.md)"





### List templates bundles available in GitHub catalog

To list the bundles available in the current GitHub account use the **`lgh`** (List GitHub) command.

The syntax is :&#x20;

* **`lgh`** list all bundles&#x20;
* **`lgh bundle-name-part`** list all bundles containing the given name-part in their name

Example : list bundles with name containing "pyth"

```
telosys#(mymodel.model)>lgh pyth
Bundles found in GitHub store 'telosys-templates-v3' :
 . python-persistence-sqlalchemy
 . python-web-mvc-bottle
 . python-web-rest-bottle
GitHub API rate limit : 57/60
```

### Install bundles of templates

When you have found a useful bundle for your project, you can install it with the **`ib`** (Install Bundle) command.

The syntax is : **`ib bundle-name-part`**

For more convenience, you can use only a part of the bundle name. If several bundles contain this part in their name then they will all be installed.

Example : install all bundles with name containing "pyth"

```
telosys#(mymodel.model)>ib pyth
Installing 3 bundle(s) from GitHub...
 . 'python-persistence-sqlalchemy' : installed.
 . 'python-web-mvc-bottle' : installed.
 . 'python-web-rest-bottle' : installed.
```

{% hint style="info" %}
If you are using a **proxy** to access Internet, you must configure it in the project configuration file. \
Use the "**ecfg**" command to edit the configuration file \
and set the properties for "**Network proxy configuration**"
{% endhint %}

### List templates bundles available in the project

To list the bundles available in the current Telosys project use the **`lb`** (List Bundles) command.

The syntax is :&#x20;

* **`lb`** list all bundles&#x20;
* **`lb bundle-name-part`** list all bundles containing the given name-part in their name

Example : list all bundles&#x20;

```
telosys#(mymodel.model)>lb
3 bundle(s) :
 . python-persistence-sqlalchemy
 . python-web-mvc-bottle
 . python-web-rest-bottle
```

Example : list bundles with name containing "sql"

```
telosys#(mymodel.model)>lb sql
1 bundle(s) :
 . python-persistence-sqlalchemy
```

### Select a bundle of templates

Use the **`b`**command to show the current bundle or select a new one.

Example : select the bundle having "sqlalch" in its name

```
telosys#(mymodel.model)>b sqlalch
Current bundle is now 'python-persistence-sqlalchemy'
```

{% hint style="info" %}
Once you have defined a **current model** and a **current bundle** the Telosys prompt looks like this: `telosys#(model-name)[bundle-name]>`
{% endhint %}

### Commands summary

* **`lb`** (List Bundles) to list all the bundles installed in your project
* **`b`** (Bundle) to show or set the current bundle
* **`eb`** (Edit Bundle) to edit the bundle of templates ('templates.cfg')
* **`db`** (Delete Bundle) to delete a bundle
* **`lt`** (List Templates) to list all the templates provided by the current bundle
