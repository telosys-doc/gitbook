# Install with Git

If you plan to customize an existing model or bundle of templates, it may be more efficient to clone the Git repository so that you can then publish the changes more easily.

You can install a model or a bundle from any Git repository just using Git commands.&#x20;

{% hint style="info" %}
All the following command examples are meant to be used with a standard operating-system shell (not in Telosys-CLI )
{% endhint %}

* On the Git server (GitHub, GitLab, your own server, etc) \
  get the **Git URL** for the repository to install (on your remote Git server). \
  For example:  **`http://server-name/xxx/yyy/repo-name.git`**
* Clone the Git repository in the models or bundles directory\
  For example:  `$`**`git clone http://server-name/xxx/yyy/repo-name.git`**



After "git clone" the model or bundle is installed and ready to use.

It works as a standard model/bundle but it's a Git repository so it is ready for "commit" and "push" to publish your changes.

See also : [Publish with Git](git-publishing.md)



