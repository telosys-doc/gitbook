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

Examples :

```text
Current entity is ${entity.name}

#foreach( $attrib in $entity.attributes )
  Do something with $attrib.name and $attrib.type
#end

```

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

### Comparison Operators

Examples \(showing different operators\):

| Operator | Symbol | Text | Example |
| :--- | :--- | :--- | :--- |
| Equals / number | == | eq | `#if( $foo == 42 )` |
| Equals / string | == | eq | `#if( $foo == "bar" )` |
| Equals / object  | == | eq | `#if( $foo == $bar )` |
| Not Equals | != | ne | `#if( $foo != $bar )` |
| Greater Than | &gt; | gt | `#if( $foo > 42 )` |
| Less Than | &lt; | lt | `#if( $foo < 42 )` |
| Greater Than  or Equal To | &gt;= | ge | `#if( $foo >= 42 )` |
| Less Than  or Equal To | &lt;= | le | `#if( $foo <= 42 )` |

Note:  
The == operator can be used to compare numbers, strings, objects of the same class, or objects of different classes. In the last case \(when objects are of different classes\), the toString\(\) method is called on each object and the resulting Strings are compared.



### Logical Operators

| Operator | Symbol | Text |
| :--- | :--- | :--- |
| Logical AND | && |  and |
| Logical OR | \|\| |  or |
| Logical NOT | ! | not |

Examples :

```text
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



### Arithmetic Operators

| Operator | Symbol | Example |
| :--- | :--- | :--- |
| Addition | + | `#set( $r = $a + $b )` |
| Subtraction | - | `#set( $r = $a - $b )` |
| Multiplication | \* | `#set( $r = $a * $b )` |
| Division | / | `#set( $r = $a / $b )` |
| Modulo | % | `#set( $r = $a % 10 )` |
| Increment | \(no operator\) | `#set( $a = $a + 1 )` |
| Decrement | \(no operator\) | `#set( $a = $a - 1 )` |



