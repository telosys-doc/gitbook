# Velocity directives

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



## xxxx

