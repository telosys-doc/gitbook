# Attribute

### Attribute structure

An attribute structure is composed of the following elements :

* attribute **name**
* **":"** \(separator\)
* attribute **type** \(basic type or reference\)
* **annotations** \(optional\) defined between **"{"** and **"}"**
* **";"** \(end of attribute definition\)

Syntax :

```text
attributeName : attributeType { annotations } ;
```

An attribute definition can span multiple lines.   
Example :

```text
attributeName : attributeType { 
                annotations } ;
```

### 

### Attribute name

The attribute name can be composed of : **letters**, **numbers** and **"\_"** \(underscore\). Other characters are not allowed. By convention the name usually starts with a lower case character.

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

The attribute type can be a "**basic type**" or a "**reference to another entity**". 

#### Basic type

A "**basic type**" is a "**neutral type**" independent of any programming language. 

Available basic types : 

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

All of these "neutral types" are converted into the target language types during generation. Telosys offers automatic conversion for most used languages \(Java, C\#, etc\). 

#### Reference type

A "**reference**" is defined by using an **entity name** instead of the basic type.   
The referenced entity must exist in the model \(at least the entity file\).  
To reference a collection of entities just add "\[ \]" after the entity name. 

Examples : 

* **Driver** \(to reference a single Driver instance, "0..1" cardinality\) 
* **Driver\[ \]** \(to reference a collection of Driver instances, "0..N" cardinality\)

References are used to define _links_ between entities \("many to one" and "one to many"\)





