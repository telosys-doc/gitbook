# Attribute

### Syntax

An attribute definition is composed of the following elements :

* **name**
* **":"** (separator)
* **type** (attribute "neutral type" )
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

An attribute is a simple and unitary piece of data such as a string, a number, etc. Its type is defined by a "**neutral type**" independent of any programming language. Each "neutral type" will be converted into the target language type during generation. Telosys offers automatic conversion for most used languages (Java, C#, etc, see [target-languages](../target-languages/ "mention")).

### Available neutral types&#x20;

####

<table data-header-hidden><thead><tr><th width="183.5999755859375"></th><th></th></tr></thead><tbody><tr><td><h4>String/text type</h4></td><td></td></tr><tr><td>🔹<strong>string</strong> </td><td>standard "string" type</td></tr><tr><td><h4>Boolean type</h4></td><td></td></tr><tr><td>🔹<strong>boolean</strong>  </td><td>to store "true"/"false" value</td></tr><tr><td><h4>Numeric types</h4></td><td></td></tr><tr><td></td><td></td></tr><tr><td><h4>Temporal types </h4></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr></tbody></table>

#### String and text type&#x20;

**string** (standard "string" type)

#### Boolean type

**boolean**  (to store "true"/"false" value)

#### Numeric types&#x20;

* **byte**  (8-bit integer, range: -128 to +127)
* **short** (16-bit integer, range: -32,768 to +32,767)
* **int**   (32-bit integer , range: -2,147,483,648 to +2,147,483,647)
* **long**  (64-bit integer, range: -9,223,372,036,854,775,808 to +9,223,372,036,854,775,807)



#### Temporal types&#x20;





* **binary**  (to store a sequence of bytes)
*
*
* **date**  (to store a date with only year, month and day)
* **decimal**  (arbitrary precision decimal number, not limited to 32 or 64 bits like float or double)
* **double**  (double-precision 64-bit IEEE 754 floating point)
* **float**  (single-precision 32-bit IEEE 754 floating point)
*
*
*
*
* **time** (to store a time with hour, minute, second, and optionally nanosecond - without time zone)
* **timestamp** (to store a date and time - without time zone)



