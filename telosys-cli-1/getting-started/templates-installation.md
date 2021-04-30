# Templates installation

Once you have a model you need **templates** to generate your code.

Of course you can create your own templates, but the simplest way to start is to use existing templates.

Templates are organized in "bundles". A **"bundle"** is a set of templates designed to generate a particular kind of targets.

Templates bundles can be downloaded for **GitHub** \(each bundle is a "git repository"\).

You can download bundles from the official site : [https://github.com/telosys-templates-v3](https://github.com/telosys-templates-v3)

To see \(or change\) the current GitHub URL use the **`gh`** command.

To list the bundles available on the current GitHub URL use the **`lgh`** command.

When you have found a useful bundle for your project, you can install it with the **`ib`** \(Install Bundle\) command.

The syntax is : **`ib bundle-name`**

For more convenience, you can use only a part of the bundle name \(this part must be discriminant enough to identify a single bundle\).

For example **`ib jaxrs`** to install the **`java-web-rest-jaxrs1-T300`** bundle.

{% hint style="info" %}
If you are using a **proxy** to access Internet, you must configure it in the project configuration file.   
Use the "**ecfg**" command to edit the configuration file   
and set the properties for "**Network proxy configuration**"
{% endhint %}



**Other useful commands :**

* **`lb`** \(List Bundles\) to list all the bundles installed in your project
* **`b`** \(Bundle\) to show or set the current bundle
* **`eb`** \(Edit Bundle\) to edit the bundle of templates \('templates.cfg'\)
* **`db`** \(Delete Bundle\) to delete a bundle
* **`lt`** \(List Templates\) to list all the templates provided by the current bundle

