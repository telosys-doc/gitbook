# Attribute / Link

### Syntax

An attribute or link definition is composed of the following elements :

* **name**
* **":"** (separator)
* **type** (basic attribute type or referenced entity for a link)
* further information (optional) defined between **"{"** and **"}"**
  * **annotations** (optional) &#x20;
  * **tags** (optional) &#x20;
* **";"** (end of definition)

Syntax :

```
name : type { annotations and tags } ;
```

An attribute or link definition can span multiple lines. \
Example :

```
name : type { 
            annotations 
            tags } ;
```

###

### Name

The name can be composed of : **letters**, **numbers** and **"\_"** (underscore). Other characters are not allowed. By convention the name usually starts with a lower case character.

Each name must be unique in the entity.

{% hint style="success" %}
Examples of **valid** attribute names :&#x20;

* **age**&#x20;
* **firstName**&#x20;
* **first\_name**&#x20;
* **flag12**
{% endhint %}

{% hint style="danger" %}
Examples of **invalid** attribute names :

* **flag#12**  ( "#" not allowed )&#x20;
* **first-name** ( "-" not allowed )&#x20;
* **$code**  ( "$" not allowed )
{% endhint %}



### Attribute type

An attribute is a simple and unitary piece of data such as a string, a number, etc. Its type is defined by a "**neutral type**" independent of any programming language. Each "neutral type" will be converted into the target language type during generation. Telosys offers automatic conversion for most used languages (Java, C#, etc).

Available neutral types :&#x20;

* **binary**  (to store a sequence of bytes)
* **boolean**  (to store "true"/"false" value)
* **byte**  (8-bit integer, range: -128 to +127)
* **date**&#x20;
* **decimal**
* **double**  (double-precision 64-bit IEEE 754 floating point)
* **float**  (single-precision 32-bit IEEE 754 floating point)
* **int**   (32-bit integer , range: -2,147,483,648 to +2,147,483,647)
* **long**  (64-bit integer, range: -9,223,372,036,854,775,808 to +9,223,372,036,854,775,807)
* **short** (16-bit integer, range: -32,768 to +32,767)
* **string** (standard "string" type)
* **time**&#x20;
* **timestamp**&#x20;



### Link type

A link is a reference to another entity. It's a relationship with a cardinality (one to many, many to one, etc). So the type is the **referenced entity name**. Of course, the referenced entity must exist in the model (at least the entity file).\
To reference a **collection** of entities just add "**\[ ]**" after the entity name.&#x20;

Examples :&#x20;

* **Driver** (to reference a single Driver instance, "0..1" cardinality)&#x20;
* **Driver\[ ]** (to reference a collection of Driver instances, "0..N" cardinality)





