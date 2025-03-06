# Velocity language

The **Velocity engine** used in Telosys is **version 1.7**

For more information about the Velocity Templates Language (VTL) see the official web site :&#x20;

* **User guide** : [http://velocity.apache.org/engine/releases/velocity-1.7/user-guide.html](http://velocity.apache.org/engine/releases/velocity-1.7/user-guide.html)
* **Reference guide** : [http://velocity.apache.org/engine/releases/velocity-1.7/vtl-reference-guide.html](http://velocity.apache.org/engine/releases/velocity-1.7/vtl-reference-guide.html)

## References

A template is a text file mixing fixed parts and dynamic parts based on references to variables and objects. A **reference** to a variable or an object starts with "**$**".&#x20;

Exemple :&#x20;

* **$foo**  : content of **variable** "_foo_"&#x20;
* **$customer.address** : get **property** "_address_" in object "_customer_"&#x20;
* **$person.isVIP()** : call **method** "_isVIP()_" in object "_person_"

In some cases "**Formal Reference Notation**"  with "**${xxx}**" is required to avoid ambiguities. Examples :

* **${foo}**
* **${customer.address}**
* **${person.isVIP()}**

Examples :

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

#*
This is a multi-lines comment
with 1 to N lines
*#
```

## Unparsed content

All lines between "**#\[\[**" and **"]]#"** are not parsed by Velocity, they are rendered as is.\
So characters like "#" or "$" can be used anywhere

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

### Unparsed content

The **#\[\[ do not parse me ]]#** syntax allows to easily use large chunks of uninterpreted and unparsed content in a template.

```
#[[
Unparsed block (all this block will be rendered as is)
$undefined
#set($i = 50)
#foobar #zzz(ee)
#include("foo.txt")
]]#
```

## Operators&#x20;

### Comparison operators

Examples (showing different operators):

| Operator                            | Symbol | Text | Example                |
| ----------------------------------- | ------ | ---- | ---------------------- |
| Equals / number                     | ==     | eq   | `#if( $foo == 42 )`    |
| Equals / string                     | ==     | eq   | `#if( $foo == "bar" )` |
| Equals / object                     | ==     | eq   | `#if( $foo == $bar )`  |
| Not Equals                          | !=     | ne   | `#if( $foo != $bar )`  |
| Greater Than                        | >      | gt   | `#if( $foo > 42 )`     |
| Less Than                           | <      | lt   | `#if( $foo < 42 )`     |
| <p>Greater Than <br>or Equal To</p> | >=     | ge   | `#if( $foo >= 42 )`    |
| <p>Less Than <br>or Equal To</p>    | <=     | le   | `#if( $foo <= 42 )`    |

Note:\
The == operator can be used to compare numbers, strings, objects of the same class, or objects of different classes. In the last case (when objects are of different classes), the toString() method is called on each object and the resulting Strings are compared.



### Logical operators

| Operator    | Symbol | Text |
| ----------- | ------ | ---- |
| Logical AND | &&     |  and |
| Logical OR  | \|\|   |  or  |
| Logical NOT | !      | not  |

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
