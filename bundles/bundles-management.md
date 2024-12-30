# Bundles management

### Current bundle

The current bundle is printed between "\[...]" in the CLI prompt.

Example with "**java-jdbc**" as the current bundle:  **`telosys#[java-jdbc]>`**

Use "**`b`**" command to set/unset/print the current bundle:&#x20;

Syntax:   **`b [bundle-part-name] [-none]`**&#x20;

For more convenience, you can use only a part of the bundle name\
(if several bundles contain this part in their name then the command just says "ambiguous")

Examples:

* **`b`**  -> print the current bundle
* **`b java-jdbc`**  -> set "_java-jdbc_" as current bundle
* **`b jdbc`**  -> set "_java-jdbc_" as current bundle \
  if "_java-jdbc_" is the only bundle with "_jdbc_" in its name
* **`b -none`**  -> unset the current bundle



{% hint style="info" %}
Once you have defined a **current model** and a **current bundle** \
the Telosys prompt looks like this:\
&#xNAN;**`telosys#(model-name)[bundle-name]>`**
{% endhint %}



### Main commands for bundles management

**Bundles commands:**&#x20;

* "**`b`**" Bundle: Set/print the current bundle
* "**`lb`**" List Bundles : List the project bundles&#x20;
* "**`lbd`**" List Bundles in Depot : List bundles of templates available in the depot&#x20;
* "**`ib`**" Install Bundle(s) : Install bundle(s) of templates available in the depot&#x20;
* "**`eb`**" Edit Bundle : Edit the 'templates.cfg' file of the given bundle&#x20;
* "**`db`**" Delete Bundle : Delete the current/given bundle&#x20;

**Template commands:**&#x20;

* "**`lt`**" List Templates : List the templates for the current bundle&#x20;
* "**`et`**" Edit Template : Edit a template (.vm) file

