# Velocity language

The **Velocity engine** used in Telosys is **version 1.7**

For more information about the Velocity Templates Language (VTL) see the official web site :&#x20;

* **User guide** : [http://velocity.apache.org/engine/releases/velocity-1.7/user-guide.html](http://velocity.apache.org/engine/releases/velocity-1.7/user-guide.html)
* **Reference guide** : [http://velocity.apache.org/engine/releases/velocity-1.7/vtl-reference-guide.html](http://velocity.apache.org/engine/releases/velocity-1.7/vtl-reference-guide.html)

## References (variables and objects)

A template is a text file mixing fixed parts and dynamic parts based on references to variables and objects. A **reference** to a variable or an object starts with "**$**".&#x20;

Example :&#x20;

* **$foo**  : content of **variable** "_foo_"&#x20;
* **$customer.address** : get **property** "_address_" in object "_customer_"&#x20;
* **$person.isVIP()** : call **method** "_isVIP()_" in object "_person_"

In some cases "**Formal Reference Notation**"  with "**${xxx}**" is required to avoid ambiguities.&#x20;

Examples :

* **${foo}**
* **${customer.address}**
* **${person.isVIP()}**

Examples:

```
Current entity is ${entity.name}

#foreach( $attrib in $entity.attributes )
  Do something with $attrib.name and $attrib.type
#end

```

## Comments

A part of line starting with **"##"** is a single line comment. \
All lines between "**#\***" and **"\*#"** are a comment block.

```
## This is a single line comment.
#set($x = 12)## init variable x
#*
This is a multi-lines comment
with 1 to N lines
*#
```

{% hint style="info" %}
The single-line comment (**##**) removes the "end of line", \
so you can use it to concatenate multiple lines into one. \
Example:\
`aaa`` `**`##`**\
&#x20;`bb`` `**`##`**\
&#x20;`cc`\
Result:\
`aaa bb cc`
{% endhint %}



## Unparsed content

All lines between "**#\[\[**" and **"]]#"** are not parsed by Velocity, they are rendered as is.\
So characters like "#" or "$" can be used anywhere.

The **#\[\[ do not parse me ]]#** syntax allows to easily use large chunks of uninterpreted and unparsed content in a template.

```
#[[
This part is not parsed, it is rendered as text (without Velocity interpretation)
Blablabla #include blabla
#set #break #if  $a 
]]#
```

## Literals

### String literals

When using the #set directive, strings that are enclosed in **double quote** characters will be **parsed**. But if the string literal is **enclosed in single quote characters**, it will **not be parsed**. A string literal can contains multiple lines.

```
#set($s = "abc $i")## 'i' is replaced by its value

#set($s = 'abc $i')## no variable substitution

#set($s = 
'line 1 $a
line 2 $b
line 3 $c')## 3 lines in the string
```

### Numbers literals

Same as in all languages:  0 to 9 plus ' . ' &#x20;

Examples:

```
#set($x = 12)## Integer
#set($y = 12.34)## Double
```

### Boolean literals

Just  **true**  and  **false**

Examples:

```
#set( $b = true )
#set( $b = false )
```

## Operators&#x20;

### Comparison operators

Examples (showing different operators):

<table data-header-hidden><thead><tr><th width="192.20001220703125">Operator</th><th width="119.2000732421875">Symbol</th><th width="95.60009765625">Text</th><th>Example</th></tr></thead><tbody><tr><td>Operator</td><td>Symbol</td><td>Text</td><td>Example</td></tr><tr><td>Equals / number</td><td>==</td><td>eq</td><td><code>#if( $foo == 42 )</code></td></tr><tr><td>Equals / string</td><td>==</td><td>eq</td><td><code>#if( $foo == "bar" )</code></td></tr><tr><td>Equals / object </td><td>==</td><td>eq</td><td><code>#if( $foo == $bar )</code></td></tr><tr><td>Not Equals</td><td>!=</td><td>ne</td><td><code>#if( $foo != $bar )</code></td></tr><tr><td>Greater Than</td><td>></td><td>gt</td><td><code>#if( $foo > 42 )</code></td></tr><tr><td>Less Than</td><td>&#x3C;</td><td>lt</td><td><code>#if( $foo &#x3C; 42 )</code></td></tr><tr><td>Greater Than <br>or Equal To</td><td>>=</td><td>ge</td><td><code>#if( $foo >= 42 )</code></td></tr><tr><td>Less Than <br>or Equal To</td><td>&#x3C;=</td><td>le</td><td><code>#if( $foo &#x3C;= 42 )</code></td></tr></tbody></table>

Note:\
The == operator can be used to compare numbers, strings, objects of the same class, or objects of different classes. In the last case (when objects are of different classes), the toString() method is called on each object and the resulting Strings are compared.



### Logical operators

<table data-header-hidden><thead><tr><th width="220.53334554036456">Operator</th><th width="165.4000244140625">Symbol</th><th>Text</th></tr></thead><tbody><tr><td>Operator</td><td>Symbol</td><td>Text</td></tr><tr><td>Logical AND</td><td>&#x26;&#x26;</td><td> and</td></tr><tr><td>Logical OR</td><td>||</td><td> or</td></tr><tr><td>Logical NOT</td><td>!</td><td>not</td></tr></tbody></table>

Examples :

```
#if ( $v > 100 && $v < 200 )
Between 100 and 200 
#end 

#if ( $v == 100 || $v == 102 || $v == 123 )
Var is 100 or 102 or 123 
#end 

#if ( ! ( $v == 100 || $v == 101 ) )
Var is not 100 or 101
#end 

```



### Arithmetic operators

| Operator       | Symbol        | Example                |
| -------------- | ------------- | ---------------------- |
| Addition       | +             | `#set( $r = $a + $b )` |
| Subtraction    | -             | `#set( $r = $a - $b )` |
| Multiplication | \*            | `#set( $r = $a * $b )` |
| Division       | /             | `#set( $r = $a / $b )` |
| Modulo         | %             | `#set( $r = $a % 10 )` |
| Increment      | (no operator) | `#set( $a = $a + 1 )`  |
| Decrement      | (no operator) | `#set( $a = $a - 1 )`  |

Note:  when the "+" operator is used with 2 strings, it concatenates these 2 strings.



### Range operator

The range operator creates an **array of integer objects**. It can be used in conjunction with #set and #foreach statements.\
Syntax : `[ first .. last ]`

Examples :

```
## Range from 1 to 5
#foreach( $i in [1..5] )
  $i
#end

## Range from 10 to 12 (size : 3 )
#set( $r = [ 10 .. 12 ] )
range size : $r.size()
#foreach( $i in $r )
  $i
#end

## Range from var to var
#set( $a = 4 )
#set( $b = 8 )
#foreach( $i in [$a..$b] )
  $i
#end

## Range in reverse order
#foreach( $i in [ 4 .. -2 ] )
  $i
#end
```
