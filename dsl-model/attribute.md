# Attribute / Link

### Syntax

An attribute or link definition is composed of the following elements :

* **name**
* **":"** \(separator\)
* **type** \(basic attribute type or referenced entity for a link\)
* further information \(optional\) defined between **"{"** and **"}"**
  * **annotations** \(optional\)  
  * **tags** \(optional\)  
* **";"** \(end of definition\)

Syntax :

```text
name : type { annotations and tags } ;
```

An attribute or link definition can span multiple lines.   
Example :

```text
name : type { 
            annotations 
            tags } ;
```

### 

### Name

The name can be composed of : **letters**, **numbers** and **"\_"** \(underscore\). Other characters are not allowed. By convention the name usually starts with a lower case character.

Each name must be unique in the entity.

{% hint style="success" %}
Examples of **valid** attribute names : 

* **age** 
* **firstName** 
* **first\_name** 
* **flag12**
{% endhint %}

{% hint style="danger" %}
Examples of **invalid** attribute names :

* **flag\#12**  \( "\#" not allowed \) 
* **first-name**  \( "-" not allowed \) 
* **$code**  \( "$" not allowed \)
{% endhint %}



### Attribute type

An attribute is a simple and unitary piece of data such as a string, a number, etc. Its type is defined by a "**neutral type**" independent of any programming language. Each "neutral type" will be converted into the target language type during generation. Telosys offers automatic conversion for most used languages \(Java, C\#, etc\).

Available neutral types : 

* **binary** 
* **boolean** 
* **byte** 
* **date** 
* **decimal**
* **double** 
* **float** 
* **int** 
* **long** 
* **short** 
* **string** 
* **time** 
* **timestamp** 

\*\*\*\*

### Link type

A link is a reference to another entity. It's a relationship with a cardinality \(one to many, many to one, etc\). So the type is the **referenced entity name**. Of course, the referenced entity must exist in the model \(at least the entity file\).  
To reference a **collection** of entities just add "**\[ \]**" after the entity name. 

Examples : 

* **Driver** \(to reference a single Driver instance, "0..1" cardinality\) 
* **Driver\[ \]** \(to reference a collection of Driver instances, "0..N" cardinality\)







