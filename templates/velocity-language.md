# Velocity language

The **Velocity engine** used in Telosys is **version 1.7**

For more information about the Velocity Templates Language \(VTL\) see the official web site : 

* **User guide** : [http://velocity.apache.org/engine/releases/velocity-1.7/user-guide.html](http://velocity.apache.org/engine/releases/velocity-1.7/user-guide.html)
* **Reference guide** : [http://velocity.apache.org/engine/releases/velocity-1.7/vtl-reference-guide.html](http://velocity.apache.org/engine/releases/velocity-1.7/vtl-reference-guide.html)

## References

A template is a text file mixing fixed parts and dynamic parts based on references to variables and objects. A **reference** to a variable or an object starts with "**$**". 

Exemple : 

* **$foo**  : content of variable "foo" 
* **$customer.address** : property "address" of object "customer" 
* **$person.isVIP\(\)** : call method "isVIP\(\)" in object "person"

In some cases "**Formal Reference Notation**"  with "**${xxx}**" is required to avoid ambiguities. Examples :

* **${foo}**
* **${customer.address}**
* **${person.isVIP\(\)}**

## Comments

All line starting with **"\#\#"** is a comment.   
All lines between "**\#\***" and **"\*\#"** are a comment block.

```text
## This is a single line comment.

#*
This is a multi-lines comment
with 1 to N lines
*#
```

## Operators 



Examples \(showing different operators\):

| Operator Name | Symbol | Alt | Example |
| :--- | :--- | :--- | :--- |
| Equals Number | == | eq | `#if( $foo == 42 )` |
| Equals String | == | eq | `#if( $foo == "bar" )` |
| Object Equivalence | == | eq | `#if( $foo == $bar )` |
| Not Equals | != | ne | `#if( $foo != $bar )` |
| Greater Than | &gt; | gt | `#if( $foo > 42 )` |
| Less Than | &lt; | lt | `#if( $foo < 42 )` |
| Greater Than  or Equal To | &gt;= | ge | `#if( $foo >= 42 )` |
| Less Than  or Equal To | &lt;= | le | `#if( $foo <= 42 )` |
| Boolean NOT | ! | not | `#if( !$foo )` |

Notes:

1. The == operator can be used to compare numbers, strings, objects of the same class, or objects of different classes. In the last case \(when objects are of different classes\), the toString\(\) method is called on each object and the resulting Strings are compared.
2. You can also use brackets to delimit directives. This is especially useful when text immediately follows an `#else` directive.

