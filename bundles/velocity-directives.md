# Velocity directives

A directive is a Velocity keyword starting by a "**#**", for example "#set", "#if", "#foreach", etc.&#x20;

Directives can be thought of as "instructions" for handling rendering in a model. They can be used to define variables (#set), apply logical conditions (#if), iterate over collections (#foreach), etc.

```velocity
#set( $name = "Bob" )
#foreach( $v in $elements )
 $v
#end
```

To avoid misinterpretations the name of the directive can be bracketed with "{" and "}"&#x20;

```velocity
#if($x)true#{else}false#end
```

## Most used directives

### #set

The #set directive is used for setting a value. A value can be assigned to either a simple variable or an object property.\
"#set" always defines a "global variable" wherever you use it.

```velocity
#set( $name = "Bob" )
#set( $customer.name = "Bob")
#set( $user.level = 3 ) ## number literal
#set( $a = $b ) ## variable reference
#set( $mylist = [ "A", $v, "Z"] ) ## list
```

You cannot set a variable to "null" explicitly&#x20;

```velocity
#set( $v = null ) ## causes an error
```

NB : if the value to be assigned is null then it will not be assigned!

```velocity
#set( $v = $o.get("abc") ) 
## if get returns null then $v remains unchanged
```

### #foreach / #end

The "#foreach" directive is used to loop through a list of objects. Within the "#foreach" directive 2 local variables are created to represent :\
&#x20;\- the **current item** in the loop (you can name it as you want)\
&#x20;\- the "**$foreach**" object providing properties like "count", "index", "hasNext", "first", "last", "parent", "topmost".\
The visibility of these variables is only "local" (visible only in the "#foreach" block). \
A variable defined with "#set" inside a "#foreach" block remains global (visible outside of the block).\
The "$foreach" object is an instance of org.apache.velocity.runtime.directive.ForeachScope.

Examples :

Loop with given values :

```velocity
#foreach ( $item in [1..8] ) ## from 1 to 8
 . item = $item 
#end

#foreach ( $item in [3,2,1] ) ## from 3 to 1
 . item = $item 
#end

## Everything in a single line
#foreach( $item in ['A','B','C','D'] ) ${item}#end
```

Loop with an object (array, list, collection) :

```velocity
#foreach( $attribute in $entity.attributes )
 $attribute.type $attribute.name
#end
```

Map iteration :

```velocity
#set ( $map = {"banana" : "good", "cream" : "bad"} ) 
#foreach($key in $map.keySet() )
 $key --> $map.get($key)
#end
```

Break the current iteration :

```velocity
#foreach ( $item in [1..20] )
#if ( $item > 3 ) #break #end
 . item = $item 
#end
```

**"$foreach" object:**&#x20;

When you are in a "**#foreach**" directive it is possible to use the Velocity object "**$foreach**". \
It provides information about the current iteration (index, count, etc)

$foreach attributes:

* **`$foreach.index`**: The current iteration index, starting from 0.
* **`$foreach.count`**: The current iteration count, starting from 1.
* **`$foreach.hasNext`**: A boolean value that is true if there are more elements to iterate over.
* **`$foreach.first`**: A boolean value that is true if the current iteration is the first one.
* **`$foreach.last`**: A boolean value that is true if the current iteration is the last one.
* **`$foreach.parent`**: same type of object but in the parent loop's context
* **`$foreach.topmost`**: same type of object but in the topmost (outermost) loop's context

"**$foreach.count**"  loop counter ( 1 to N ) :

```velocity
#foreach ( $item in ["A", "B", "C", "D" ] ) 
 . $foreach.count : $item 
#end
```

"**$foreach.index**"  zero-based index ( 0 to N-1 ) :

```velocity
#foreach ( $item in ["A", "B", "C", "D" ] ) 
 . $foreach.index : $item 
#end
```

"**$foreach.hasNext**"  ( true if not last item ) :

```velocity
#foreach( $customer in $customerList )
  $customer.Name#if( $foreach.hasNext ),#end
#end
```

Nested loops  :

It's possible to access outer loops properties by using "**$foreach.parent**" or "**$foreach.topmost**" \
(e.g. $foreach.parent.index or $foreach.topmost.hasNext).

```velocity
#foreach ( $item1 in ["A", "B", "C", "D" ] ) 
#foreach ( $item2 in [1,2,3 ] )
 . $foreach.index : $item1 / $item2  
   ($foreach.parent.index) ($foreach.topmost.index)
#end 
#end
```



### #if / #else / #**elseif** / #end

Conditional output or instructions

Examples :

**#if / #end :**

```velocity
 #if ( $v == 1 ) equals 1 #end 

 #if ( $v == 1 ) 
 equals 1 
 #end 
```

**#if / #else / #end :**

```velocity
 #if ( $v == 1 ) equals 1 #else not equals 1 #end 

 #if ( $v == 1 ) 
 equals 1 
 #else 
 not equals 1 
 #end 
```

**#if / #elseif / #else / #end :**

```velocity
 #if ( $v == 1 ) 
 equals 1 
 #elseif ( $v == 2 ) 
 equals 2 
 #else 
 other 
 #end 
```



### #include

The **#include** directive allows to import a local file at the current position. The file is included "as is" (as a text file, not rendered through the template engine, not parsed).\
If more than one file will be included, they should be separated by commas. A variable can be used instead of a literal filename.\
Any files to which #include refers must be included under "TEMPLATE\_ROOT" ( the "bundle" directory for Telosys ).

Examples :

```velocity
## Include a single file :
#include( "myfile.txt" )
#include( "include/myfile.txt" ) 

## Include multiple files :
#include( "a.txt", "b.html" )

## Include with variables :
#include( $myfile )
#include( "header.include", $myfile ) 
```



### #parse

The **#parse** directive allows to import a local Velocity template file. \
The file is parsed by the Velocity engine. Only one argument is accepted (only one file for each call, other arguments are ignored). A variable can be used instead of the literal filename.\
All the variables defined before the "#parse" call are usable in the parsed file. All the variables defined in the parsed file are usable in the primary file after the "#parse" call.\
Any templates to which #parse refers must be included under "TEMPLATE\_ROOT" ( the "bundle" directory for Telosys ).

Examples :

```velocity
#parse("foo.vm")
#parse($myfile)
#parse("include/initvar.vm")
## Here we can use variables defined in "initvar.vm"
```

\#parse can be used inside "parsed files".\
Recursion is permitted (with a condition to stop recursion).

Primary file :

```velocity
#set( $count = 8 )
#parse( "foo.vm" )
```

"foo.vm" file with recursive "parse" :

```velocity
#set( $count = $count - 1 )
#if( $count > 0 )
  #parse( "foo.vm" )
#else
  End of recursion.
#end
```



## Other directives

### #stop

The **#stop** directive stops any further rendering and execution of the template. This is true even when the directive is nested within another template accessed through **#parse** or located in a velocity **macro**.&#x20;

The resulting output will contain all the content up to the point the #stop directive was encountered. This is handy as an early exit from a template.

Example :

```velocity
#if ( $v == 12 ) 
#stop 
#end 
```



### #break

The **#break** directive stops any further rendering of the current "execution scope". \
An "execution scope" can be \
\- a **directive with content** : #foreach, #parse, #evaluate, #define, #macro, or #@somebodymacro\
\- the **current template** ("root scope").\
Unlike #stop, #break will only stop the innermost, immediate scope, not all of them.

Examples :

```velocity
## BREAK at template level (stop template rendering)
#break

## BREAK in a single loop
#set($mylist = ["A", "B", "C", "D", "E", "F" ])
#foreach( $v in $mylist )
#if( $foreach.count > 3 ) 
  #break
#end
$foreach.count : $v

## BREAK in a nested loop (break innermost)
#set($mylist1 = ["A", "B", "C", "D", "E", "F" ])
#set($mylist2 = [1, 2, 3, 4, 5, 6 ])
#foreach( $v1 in $mylist1 )
#foreach( $v2 in $mylist2 )
#if( $foreach.count > 3 )#break
#end
$foreach.parent.count : $v1 / $foreach.count : $v2
#end
#end
```



### #evaluate

The **#evaluate** directive can be used to dynamically evaluate a statement (piece of Velocity code). This allows to evaluate a string that is created dynamically at render time. '#evalute' works like '#parse' but with content that comes from a variable in memory instead of a file (it's possible to evaluate multiple lines).

Examples :

```velocity
#set($v = 2)
#set($statement = '#set($r = $v * 10)' )
#evaluate($statement)
v : $v 
statement : $statement
r : $r ## r : 20
```



### #macro

Velocity "macros" allow you to define a portion of VTL code which will then be reusable several times. They are often called "Velocimacro".

Example : basic macro (without argument)

```velocity
#macro( three )
#set ( $result = "" )
#foreach ( $i in [1..3] ) ${i}#end
#end
## -------
#three() 
```

Arguments : \
A Velocimacro can take any number of arguments (0 to N arguments). When the Velocimacro is invoked, it must be called with the same number of arguments with which it was defined. Each argument is a local variable and can never be used outside.

Example : macro with 2 arguments

```velocity
#macro( add $a1 $a2 )
#set ( $r = $a1 + $a2 )
$a1 + $a2 = $r 
#end
## -------
#add( 20, 3 )
## rendering : 20 + 3 = 23
```

NB : Macros are not functions, they are designed to render and they cannot return a value. But you can simulate a "return value" by setting a variable in the macro and using it after calling the macro or by setting the result as a string.

Example : "Function like call" getting the result as text (with quotes)

```velocity
#macro( add3 $a1 $a2 $a3 )
#set ( $r = $a1 + $a2 + $a3)
$r## NO EOL
#end
## -------
#set($v = 50)
#set( $result = "#add3(10,20,$v)" )
result : $result
```

**Macro with body content**

It is possible to call a macro and pass it a text (1 to N lines). To do so call the macro with '**@**' between '#' and the macro name ( **#@mymacro()** ) . With this type of call you can add the text to pass after the call using '**#end**' to mark the end of the text. In the macro definition the text can be retrived via the '**$bodyContent**' reference (special reference defined only for macro).

```velocity
#macro(xml)
<aaa>
$bodyContent
</aaa>
#end
## ------------------------
#@xml()line1
line2
line3#end
```

### #define

The #define directive allows to assign a **block of code** to a **variable**.  The associated block of code can contain any valid code.

The code associated with a variable by #define is executed **when the variable is referenced**.&#x20;

The type of the variable created by #define is org.apache.velocity.runtime.directive.Block$Reference

Example :

```velocity
#define( $block )Hello $who#end
#set( $who = 'World!' )
$block
```

Differences between "#define" and "#macro" : "\
&#x20;\-  #macro" accepts parameters so that they provide a context for creation of local variables \
&#x20;\-  "#define" structure (unless it contains macros) only works with global variables

