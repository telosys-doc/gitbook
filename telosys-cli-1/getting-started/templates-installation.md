# Templates installation



Once you have a model you need at least one **bundle of templates** to generate your code.

The templates are organized in "bundles". A **"bundle"** is a set of templates designed to generate a particular kind of targets.

Of course you can create your own templates from scatch, but the simplest way to start is to use existing templates. 

Templates bundles can be downloaded for **GitHub** \(each bundle is a "git repository"\).

### Templates catalog configuration \(GitHub account\)

By default the templates catalog points to [https://github.com/telosys-templates-v3](https://github.com/telosys-templates-v3)

To see the current catalog use the **`gh`** \("GitHub"\) command without argument.

You can change it by defining a new account or organization name where you will store your own templates. 

Use**`gh new-catalog`**  to change the current catalog

Examples :

```text
telosys#(mymodel.model)>gh
telosys-templates-v3

telosys#(mymodel.model)>gh mycatalog
GitHub store is now 'mycatalog'

telosys#(mymodel.model)>gh
mycatalog
```

### List templates bundles available in GitHub catalog

To list the bundles available in the current GitHub account use the **`lgh`** \(List GitHub\) command.

Example : list bundles with name containing "pyth"

```text
telosys#(mymodel.model)>lgh pyth
Bundles found in GitHub store 'telosys-templates-v3' :
 . python-persistence-sqlalchemy
 . python-web-mvc-bottle
 . python-web-rest-bottle
GitHub API rate limit : 57/60
```

### Install bundles of templates

When you have found a useful bundle for your project, you can install it with the **`ib`** \(Install Bundle\) command.

The syntax is : **`ib bundle-name`**

For more convenience, you can use only a part of the bundle name \(this part must be discriminant enough to identify a single bundle\).

For example **`ib jaxrs`** to install the **`java-web-rest-jaxrs1-T300`** bundle.

Example : install bundles with name containing "pyth"

```text
telosys#(mymodel.model)>ib pyth
Installing 3 bundle(s) from GitHub...
 . 'python-persistence-sqlalchemy' : installed.
 . 'python-web-mvc-bottle' : installed.
 . 'python-web-rest-bottle' : installed.
```

{% hint style="info" %}
If you are using a **proxy** to access Internet, you must configure it in the project configuration file.   
Use the "**ecfg**" command to edit the configuration file   
and set the properties for "**Network proxy configuration**"
{% endhint %}

### List templates bundles available in the project



Example : list all bundles 

```text
telosys#(mymodel.model)>lb
3 bundle(s) :
 . python-persistence-sqlalchemy
 . python-web-mvc-bottle
 . python-web-rest-bottle
```

Example : list bundles with name containing "sql"

```text
telosys#(mymodel.model)>lb sql
1 bundle(s) :
 . python-persistence-sqlalchemy
```

### Select a bundle of templates

Use the **`b`**command to show the current bundle or select a new one.

Example : select the bundle having "sqlalch" in its name

```text
telosys#(mymodel.model)>b sqlalch
Current bundle is now 'python-persistence-sqlalchemy'
```

{% hint style="info" %}
Once you have defined a **current model** and a **current bundle** the Telosys prompt looks like this: `telosys#(model-name)[bundle-name]>`
{% endhint %}

### Commands summary

* **`lb`** \(List Bundles\) to list all the bundles installed in your project
* **`b`** \(Bundle\) to show or set the current bundle
* **`eb`** \(Edit Bundle\) to edit the bundle of templates \('templates.cfg'\)
* **`db`** \(Delete Bundle\) to delete a bundle
* **`lt`** \(List Templates\) to list all the templates provided by the current bundle

