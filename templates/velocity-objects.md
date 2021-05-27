# Velocity objects

## Array 

xxxx



## List

Object containing a list of any type of values.  
The values are stored internally in a "_ArrayList_" Java object  
\( see java.util.ArrayList \)

Initialization :

```text
#set( $mylist = [1, 2, 3, "A", true, 65.78] )
```

Print content :

```text
mylist content : $mylist

--- OUTPUT :
mylist content : [1, 2, 3, A, true, 65.78]
```

Print all items :

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

item 4 : $mylist[4]
--- OUTPUT :
item 4 : A

item 6 : $mylist[6]
--- ERROR :
Index 6 out of bounds for length 6
```

Other usages :

```text
// size    : $mylist.size()
// isEmpty : $mylist.isEmpty()
```

## Map

Object containing Key-Value associations.  
The "key-value" pairs are stored internally in a "_LinkedHashMap_" Java object \(see "java.util.LinkedHashMap" \)

Initialization :

```text
#set( $mymap = {"k1" : "v1" , "k2" : "v2"} )
```

Print content :

```text
mymap content : $mymap 
```

Result :

  `mymap content : {k1=v1, k2=v2}`









