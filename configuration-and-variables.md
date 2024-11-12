# Project configuration

The project configuration is defined in the file **TelosysTools/telosys-tools.cfg**

Each line has the following syntax :

```
name = value
```

Each line starting with a "#" is a comment :

```
# this is a comment
```

###

### **"SpecificTemplatesFolder" -> specific location for bundles of templates**

To define a specific location for templates, a directory where the templates are located for the current project. By default templates are located in "(project-home)/TelosysTools/templates", if you want to use another directory you can define it with this parameter.

Examples:

```
#-- Specific location for bundles of templates (Windows) :
SpecificTemplatesFolder=C:/dir1/dir2

#-- Specific location for bundles of templates (Linux) :
SpecificTemplatesFolder=/dir1/dir2
```



### **"**SpecificModelsFolder**" -> specific location for models**&#x20;

(since ver 4.2.0)

To define a specific location for models, a directory where the models are located for the current project. By default models are located in "(project-home)/TelosysTools/models", if you want to use another directory you can define it with this parameter.

Examples:

<pre><code><strong>#-- Specific models location (Windows) :
</strong><strong>SpecificModelsFolder=C:/dir1/dir2
</strong>
#-- Specific models location (Linux) :
SpecificModelsFolder=/dir1/dir2
</code></pre>



### **"SpecificDestinationFolder"**  ->  specific destination for generation output files

To define a specific destination for code generation. The root directory where the generated files will be placed. By default the generated files are located in the current project directory (project home), you can change it with this parameter.

Examples:

```
#-- Specific destination for code generation (Windows) :
SpecificDestinationFolder=C:/dir1/dir2

#-- Specific destination for code generation (Linux) :
SpecificDestinationFolder=/dir1/dir2
```



### **"**SpecificDepotForBundles**" -> specific "depot" for bundles**

(since ver 4.2.0)

The standard "depot" for available "bundles of templates" is a Telosys organization in GitHub.\
You can define your own "depot" to store and install your bundles.

For GitHub 3 types of definitions are possible:

* **`github_org`**  ->  GitHub organization  +  " **:** " +  _**organization-name**_
* **`github_user`** ->  GitHub user  +  " **:** " +  _**user-name**_
* **`github_current_user`**  ->  GitHub current user  ( user authenticated by the current token )

Examples:

<pre><code><strong>#-- Organization in GitHub :
</strong>SpecificDepotForBundles=github_org:my-organization
#-- User in GitHub :
SpecificDepotForBundles=github_user:my-user
#-- Current authenticated user in GitHub :
SpecificDepotForBundles=github_current_user
</code></pre>



### **"**SpecificDepotForModels**" -> specific "depot" for models**

(since ver 4.2.0)

Same principle as for the bundles

Examples:

```
SpecificDepotForModels=github_org:my-organization
SpecificDepotForModels=github_user:my-user
SpecificDepotForModels=github_current_user
```



### Http proxy configuration

Telosys uses http to get models from a remote repository (usually GitHub).&#x20;

So if you use a proxy to access the Internet you need to configure its configuration so that the Telosys "http client" can connect to proxy.

The usual proxy configuration settings are expected (for http and https) :&#x20;

* **http\[s].proxyHost** :   \
  the host name of the proxy server
* **http\[s].proxyPort** :  \
  the port number of the proxy server
* **http\[s].nonProxyHosts**  : \
  a list of hosts that should be reached directly, bypassing the proxy
* **http\[s].proxyUser** :  \
  the proxy user name
* **http\[s].proxyPassword**  :  \
  the proxy user password

Example:&#x20;

```
# --- Network proxy configuration
http.proxyHost=my.proxy.hostname
http.proxyPort=3128
http.nonProxyHosts=localhost|127.0.0.1
http.proxyUser=foo
http.proxyPassword=secret
#--
https.proxyHost=my.proxy.hostname
https.proxyPort=3129
https.nonProxyHosts=localhost|127.0.0.1
https.proxyUser=foo
https.proxyPassword=secret
```



