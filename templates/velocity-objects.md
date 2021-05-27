# Velocity objects

## List \(array\)

Object containing a list of any type of values.  
The values are stored internally in a "_ArrayList_" Java object  
\( see java.util.ArrayList for details \).

This object is also considered as an "_array_" in many documentations.

Initialization :

```text
## 4 numbers from 1 to 4 (with range operator)
#set( $mylist = [1..4]) 

## void list
#set($mylist = [])

## 6 values with diferent types
#set( $mylist = [1, 2, 3, "A", true, 65.78] )
```

Print content :

```text
mylist content : $mylist

--- OUTPUT :
mylist content : [1, 2, 3, A, true, 65.78]
```

Print all items \("$foreach.count" goes from 1 to length, it's a count not an index \) :

```text
#foreach ( $item in $mylist ) 
 - $foreach.count : $item 
#end

--- OUTPUT :
 1 : item = 1 
 2 : item = 2 
 3 : item = 3 
 4 : item = A 
 5 : item = true 
 6 : item = 65.78 
```

Print a single item by index \(the index goes from 0 to length-1\)  :

```text
item 0 : $mylist[0]
--- OUTPUT :
item 0 : 1 

item 3 : $mylist[3]
--- OUTPUT :
item 3 : A

item 6 : $mylist[6]
--- ERROR :
Index 6 out of bounds for length 6
```

Other examples :

```text
isEmpty : $mylist.isEmpty()
#if ( $mylist.isEmpty() ) list is void #end

size    : $mylist.size()
#if ( $mylist.size() > 0 ) list is not void #end

#set( $z = $mylist.add("new item") ) 
##  set is a work around to avoid printing 
##  the return value of 'add'
```

## Map

Object containing Key-Value associations.  
The "key-value" pairs are stored internally in a "_LinkedHashMap_" Java object \(see "java.util.LinkedHashMap" for details\)

Initialization :

```text
#set( $mymap = {"k1" : "v1" , "k2" : "v2"} )
```

Print content :

```text
mymap content : $mymap
--- OUTPUT :
mymap content : {k1=v1, k2=v2}
```











