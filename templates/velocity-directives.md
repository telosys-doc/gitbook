# Velocity directives

## Most used directives

### \#set

The \#set directive is used for setting a value. A value can be assigned to either a simple variable or an object property.

```text
#set( $name = "Bob" )
#set( $customer.name = "Bob")
#set( $user.level = 3 ) ## number literal
#set( $a = $b ) ## variable reference
#set( $mylist = [ "A", $v, "Z"] ) ## list
```



### \#foreach / \#end

Loops through a list of objects

Examples :

Loop with given values :

```text
#foreach ( $item in [1..8] ) ## from 1 to 8
 . item = $item 
#end

#foreach ( $item in [3,2,1] ) ## from 3 to 1
 . item = $item 
#end

## Everything in a single line
#foreach( $item in ['A','B','C','D'] ) ${item}#end
```

Loop with an object \(array, list, collection\) :

```text
#foreach( $attribute in $entity.attributes )
 $attribute.type $attribute.name
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

"**$foreach.count**"  loop counter \( 1 to N \) :

```text
#foreach ( $item in ["A", "B", "C", "D" ] ) 
 . $foreach.count : $item 
#end
```

"**$foreach.index**"  zero-based index \( 0 to N-1 \) :

```text
#foreach ( $item in ["A", "B", "C", "D" ] ) 
 . $foreach.index : $item 
#end
```

"**$foreach.hasNext**"  \( true if not last item \) :

```text
#foreach( $customer in $customerList )
  $customer.Name#if( $foreach.hasNext ),#end
#end
```

Nested loops  :

It's possible to access outer loops properties by using "**$foreach.parent**" or "**$foreach.topmost**"   
\(e.g. $foreach.parent.index or $foreach.topmost.hasNext\).

```text
#foreach ( $item1 in ["A", "B", "C", "D" ] ) 
#foreach ( $item2 in [1,2,3 ] )
 . $foreach.index : $item1 / $item2  
   ($foreach.parent.index) ($foreach.topmost.index)
#end 
#end
```



### \#if / \#else / \#**elseif** / \#end

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

### \#include

The **\#include** directive allows to import a local file at the current position.   
The file is included "as is" \(as a text file, not rendered through the template engine, not parsed\).  
If more than one file will be included, they should be separated by commas. A variable can be used instead of a literal filename.

Examples :

```text
## Include a single file :
#include( "myfile.txt" )
#include( "include/myfile.txt" ) 

## Include multiple files :
#include( "a.txt", "b.html" )

## Include with variables :
#include( $myfile )
#include( "header.include", $myfile ) 
```

### \#parse

xxxx

## Other directives

### \#stop

The **\#stop** directive stops any further rendering and execution of the template. This is true even when the directive is nested within another template accessed through **\#parse** or located in a velocity **macro**. 

The resulting output will contain all the content up to the point the \#stop directive was encountered. This is handy as an early exit from a template.

Example :

```text
#if ( $v == 12 ) 
#stop 
#end 
```



### \#break

xxxx



### \#evaluate

xxxx



### \#define

xxxx



### \#macro

xxxx





