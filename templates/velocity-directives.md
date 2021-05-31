# Velocity directives

## Most useful directives

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

### xxxxxxxx

### xxxx

