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

An attribute is a simple and unitary piece of data such as a string, a number, etc.&#x20;

Its type is defined by a "**neutral type**" independent of any programming language.&#x20;

Each "neutral type" will be converted into the target language type during generation.&#x20;

Telosys offers automatic conversion for most used languages (Java, C#, etc, see [target-languages](../target-languages/ "mention")).



### Available types&#x20;

#### String or text type&#x20;

<table data-header-hidden><thead><tr><th width="196.39990234375"></th><th></th></tr></thead><tbody><tr><td><strong>string</strong> </td><td>standard "string" type</td></tr></tbody></table>

#### Numeric types&#x20;

<table data-header-hidden><thead><tr><th width="196.39990234375"></th><th></th></tr></thead><tbody><tr><td><strong>byte</strong>  </td><td>8-bit integer<br>range: -128 to +127</td></tr><tr><td><strong>short</strong> </td><td>16-bit integer<br>range: -32,768 to +32,767</td></tr><tr><td><strong>int</strong>   </td><td>32-bit integer <br>range: -2,147,483,648 to +2,147,483,647</td></tr><tr><td><strong>long</strong>  </td><td>64-bit integer<br>range: -9,223,372,036,854,775,808 to +9,223,372,036,854,775,807</td></tr><tr><td><strong>float</strong>  </td><td>single-precision 32-bit IEEE 754 floating point</td></tr><tr><td><strong>double</strong></td><td>double-precision 64-bit IEEE 754 floating point</td></tr><tr><td><strong>decimal</strong>  </td><td>arbitrary precision decimal number,<br>not limited to 32 or 64 bits like float or double</td></tr></tbody></table>

#### Temporal types&#x20;

<table data-header-hidden><thead><tr><th width="196.39990234375"></th><th></th></tr></thead><tbody><tr><td><strong>date</strong>  </td><td>to store a date <br><strong>year</strong>, <strong>month</strong> and <strong>day</strong></td></tr><tr><td><strong>time</strong> </td><td>to store a time <br><strong>hour</strong>, <strong>minute</strong>, <strong>second</strong>, and optionally nanosecond<br>without time zone</td></tr><tr><td><strong>datetime</strong> <br>(since ver 4.3.0)</td><td>to store a date with the time <br><strong>year</strong>, <strong>month, day, hour</strong>, <strong>minute</strong>, <strong>second</strong>, and optionally nanosecond<br>without time zone</td></tr><tr><td><strong>datetimetz</strong> <br>(since ver 4.3.0)</td><td>same as "datetime" but with "Time Zone Offset"</td></tr><tr><td><strong>timetz</strong><br>(since ver 4.3.0)</td><td>same as "time" but with "Time Zone Offset"</td></tr><tr><td><em><strong>timestamp</strong></em> </td><td>synonym for "datetime",  deprecated since ver 4.3.0 </td></tr></tbody></table>

#### Other types&#x20;

<table data-header-hidden><thead><tr><th width="196.39990234375"></th><th></th></tr></thead><tbody><tr><td><strong>boolean</strong>  </td><td>to store "true"/"false" value</td></tr><tr><td><strong>uuid</strong><br>(since ver 4.3.0)</td><td>"Universally Unique Identifier" <br>(128-bit number used to uniquely identify information)</td></tr><tr><td><strong>binary</strong>  </td><td>to store a sequence of bytes</td></tr></tbody></table>

