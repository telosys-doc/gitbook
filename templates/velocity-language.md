# Velocity Language

The **Velocity engine** used in Telosys is **version 1.7**

For more information about the Velocity Templates Language \(VTL\) see the official web site : 

* **User guide** : [http://velocity.apache.org/engine/releases/velocity-1.7/user-guide.html](http://velocity.apache.org/engine/releases/velocity-1.7/user-guide.html)
* **Reference guide** : [http://velocity.apache.org/engine/releases/velocity-1.7/vtl-reference-guide.html](http://velocity.apache.org/engine/releases/velocity-1.7/vtl-reference-guide.html)





## \#foreach / \#end

Loops through a list of objects

Examples :

Loop through an array :

```text
 #foreach ( $item in [1..8] ) ## from 1 to 8
 . item = $item 
 #end

 #foreach ( $item in [3,2,1] ) ## from 3 to 1
 . item = $item 
 #end

 ## Everything in a single line
 #foreach ( $item in ['this', 'is', 'a', 'loop' ] ) ${item}#end
```

Loop through an object \(array, list, collection\) :

```text
 #foreach( $attribute in $entity.attributes )
 $attribute.type $attribute.name
 #end
```

Loop counter provided by "$foreach.count" \( 1 to N \) :

```text
 #foreach ( $item in ["A", "B", "C", "D" ] ) 
 $foreach.count : $item 
 #end
```

Map iteration :

```text
 #set ( $map = {"banana" : "good", "cream" : "bad"} ) 
 #foreach($key in $map.keySet() )
 $key --> $map.get($key)
 #end
```

Break the current iteration :

```text
 #foreach ( $item in [1..20] )
 #if ( $item > 3 ) #break #end
 . item = $item 
 #end
```





## \#if / \#else / \#**elseif** / \#end

Conditional output or instructions

Examples :

**\#if / \#end :**

```text
 #if ( $v == 1 ) equals 1 #end 

 #if ( $v == 1 ) 
 equals 1 
 #end 
```

**\#if / \#else / \#end :**

```text
 #if ( $v == 1 ) equals 1 #else not equals 1 #end 

 #if ( $v == 1 ) 
 equals 1 
 #else 
 not equals 1 
 #end 
```

**\#if / \#elseif / \#else / \#end :**

```text
 #if ( $v == 1 ) 
 equals 1 
 #elseif ( $v == 2 ) 
 equals 2 
 #else 
 other 
 #end 
```



## Operators 



Examples \(showing different operators\):

| Operator Name | Symbol | Alternative Symbol | Example |
| :--- | :--- | :--- | :--- |
| Equals Number | == | eq | `#if( $foo == 42 )` |
| Equals String | == | eq | `#if( $foo == "bar" )` |
| Object Equivalence | == | eq | `#if( $foo == $bar )` |
| Not Equals | != | ne | `#if( $foo != $bar )` |
| Greater Than | &gt; | gt | `#if( $foo > 42 )` |
| Less Than | &lt; | lt | `#if( $foo < 42 )` |
| Greater Than or Equal To | &gt;= | ge | `#if( $foo >= 42 )` |
| Less Than or Equal To | &lt;= | le | `#if( $foo <= 42 )` |
| Boolean NOT | ! | not | `#if( !$foo )` |

Notes:

1. The == operator can be used to compare numbers, strings, objects of the same class, or objects of different classes. In the last case \(when objects are of different classes\), the toString\(\) method is called on each object and the resulting Strings are compared.
2. You can also use brackets to delimit directives. This is especially useful when text immediately follows an `#else` directive.

