# Code generation

Once you have a **valid model** and a least one **bundle of templates**, you are **ready to generate your code**.

**`gen`** is the only command you need to generate your code.

### "gen" command syntax

```text
> gen *|entities *|templates [-r] [-y]
```

* **`entities`** : a **list of entities** \(part of the name\) separated by a comma \(,\) or **"\*"** for all
* **`templates`** : a **list of templates** \(part of the name\) separated by a comma \(,\) or **"\*"** for all
* **`-r`**  \(optional\) to copy the **static resources** provided by the bundle \(if any\)
* **`-y`**   \(optional\) to force "**yes**" answer \(to avoid confirmation\)

{% hint style="info" %}
You must have defined the **current model** and the **current bundle** before using the gen command, the Telosys prompt must look like this: `telosys#(model-name)[bundle-name]>`
{% endhint %}

### "gen" command examples

```text
> gen * *
```

generates the code for **all the entities** of the current model with **all the templates** of the current bundle



```text
> gen * * -r
```

generates the code for **all the entities** of the current model with **all the templates** of the current bundle and copy the **static resources** provided by the bundle \(if any\)



```text
> gen Driver *
```

generates the code for only the entities having "**Driver**" in their name and for all the templates of the current bundle



```text
> gen Car,Dri *
```

generates the code for only the entities having "**Car**" or "**Dri**" in their name and for all the templates of the current bundle



```text
> gen * dao
```

generates the code for all the entities of the current model with only the templates having "**dao**" in their name

 

```text
> gen Car,Dri dao,controller
```

generates the code for only the entities having "**Car**" or "**Dri**" in their name and only the templates having "**dao**" or "**controller**" in their name

