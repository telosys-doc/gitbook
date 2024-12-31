# "genb" command

"**genb**" is a special command to generate code in "**batch mode**" (or "bulk mode") \
with **multiple models** and/or **multiple bundles**. \
This command has been added in Telosys version 4.1.0

Principle of using entities (.entity) and templates (.vm) for code generation:\
&#x20; \- All entities present in the selected model(s) are used.\
&#x20; \- All templates defined in the selected bundle(s) are used.

{% hint style="info" %}
You don't have to defined the **current model** and the **current bundle** \
before using the genb command (it can work with any models and any bundles)
{% endhint %}

## "genb" command syntax

```
> genb model(s) bundle(s) [-r] [-y]
```

* **`models`**:    **model name** or **part of name** or **"\*"** for all models
* **`bundles`**:  **bundle name**  or **part of name**  or **"\*"** for all bundles
* **`-r`**  (optional) to copy the **static resources** provided by the bundle (if any)
* **`-y`**  (optional) to force "**yes**" answer (to avoid confirmation)



## "genb" command examples

```
> genb * *
```

generates the code for **all the models** with **all the bundles of templates**&#x20;



```
> genb cars java 
```

generates the code for **all the models** having "_**cars**_" in their name \
with **all bundles** having "_**java**_" in their name

