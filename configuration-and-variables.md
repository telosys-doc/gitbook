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

Project configuration allows setting parameters such as **specific directories** and **http proxy configuration**.

### Specific folders

In the configuration file you can define the following specific folders :

* **SpecificTemplatesFolder** :&#x20;

To define a specific location for templates, a directory where the templates are located for the current project. By default templates are located in "(project-home)/TelosysTools/templates", if you want to use another directory you can define it with this parameter.

Examples :

```
#-- Specific location for templates (Windows) :
SpecificTemplatesFolder=C\:\\dir1\\dir2

#-- Specific location for templates (Linux) :
SpecificTemplatesFolder=/dir1/dir2
```

* **SpecificDestinationFolder**  :&#x20;

To define a specific destination for code generation. The root directory where the generated files will be placed. By default the generated files are located in the current project directory (project home), you can change it with this parameter.

Examples :

```
#-- Specific destination for code generation (Windows) :
SpecificDestinationFolder=C\:\\dir1\\dir2

#-- Specific destination for code generation (Linux) :
SpecificDestinationFolder=/dir1/dir2
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



