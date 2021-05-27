# Velocity objects

## List

Object containing a list of any type of values.  
The values are stored internally in a "_ArrayList_" Java object  
\( see java.util.ArrayList for details \).

Even if it's not a real "Java array", this object is often considered as an "_array_" in many Velocity documentations..

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

Print all items with "\#foreach"  
\( "$foreach.count" goes from 1 to length, it's a count not an index \) :

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

Change list content :

```text
#set( $mylist[2] = "CCC" ) ## index starts at 0

#set( $z = $mylist.add("new item") ) 
#set( $z = $mylist.remove("A") )
#set( $z = $mylist.removeAll( [1, 2, true, "Y"] ) )
##  'set($z=..)' is a work around to avoid printing 
##  the return value from 'add', 'remove', etc
```

Other examples :

```text
isEmpty : $mylist.isEmpty()
#if ( $mylist.isEmpty() ) list is void #end

size    : $mylist.size()
#if ( $mylist.size() > 0 ) list is not void #end

$mylist.indexOf("A")  ## OUTPUT : 3 (found at index 3)
$mylist.indexOf("Z")  ## OUTPUT : -1 (not found)

$mylist.contains("A") ## OUTPUT : true (found)
$mylist.contains("Z") ## OUTPUT : false (not found)

$mylist.subList(1,3) ## from 1 to 2 (3 is exclusive)
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

## Array

"Pure array" object that can be obtained from other objects.

The values are stored internally in a "_Object \[ \]_ " instance. And therefore it doesn't have all the features offered by a List. An array does not support operations changing its size \( add, remove, removeAll, etc\)

Initialization :

```text
#set( $array = $mylist.toArray() ) 
```

Print all items with "\#foreach"  
\( "$foreach.count" goes from 1 to length, it's a count not an index \) :

```text
#foreach ( $item in $array) 
 $foreach.count : $item 
#end

--- OUTPUT :
 1 : item = A 
 2 : item = B 
 3 : item = C 
 4 : item = D 
```

```text
#set($last = $array.size() - 1 ) ## last index
#foreach ( $i in [0..$last] )  ## index 'range'
// index : $i --> element : $array[$i] 
#end

--- OUTPUT :
// index : 0 --> element : A 
// index : 1 --> element : B 
// index : 2 --> element : C 
// index : 3 --> element : D 
```

Change value :

```text
#set( $array[2] = "newValue" ) ## index starts at 0
```

Other examples :

```text
isEmpty : $array.isEmpty()
#if ( $array.isEmpty() ) is void #end

size    : $array.size()
#if ( $array.size() > 0 ) is not void #end

$array.contains("B") ## OUTPUT : true (found)
$array.indexOf("B") ## OUTPUT : 1 (found at index 1)
```









