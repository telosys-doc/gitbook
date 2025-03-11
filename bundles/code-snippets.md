# Code snippets

### Iterate over all entities defined in the model

```velocity
#foreach( $e in $model.allEntites )
		...
#end
```

### Iterate over entity attributes

```velocity
#foreach( $attribute in $entity.attributes )
		...
#end

#foreach( $attribute in $entity.keyAttributes)
		...
#end

#foreach( $attribute in $entity.nonKeyAttributes)
		...
#end
```

### Iterate over entity links

```velocity
#foreach( $link in $entity.links )
		...
#end

```

### Execute a ".vm" file located in a model folder

The function "$fn.fileFromModel(fileName)" returns an instance of "file" located in the current model. If the file exists, its content is loaded and evaluated with "#evaluate" directive.

```velocity
#set( $file = $fn.fileFromModel("model-init.vm") )
#if($file.exists())#evaluate($file.loadContent())#end
```

### Get the class of an object

As all Velocity references ( "$xxx" ) are references of Java objects, sometimes it could be useful to know the object's class. To do this, just use "**class.name**" (full name with package) or "**class.simpleName**" (only the class name without package)

```velocity
#set( $v = 12 )
$v.class.name 
$v.class.simpleName 

#set( $s = "abc" )
$s.class.name 
$s.class.simpleName 

$entity.class.name 

$now.class.simpleName 
```

### Generate a file only once

Sometimes it can be useful to make sure you only generate a file once to avoid overwriting manual changes after project bootstrapping. Since Telosys 3.3.0 you can do that with **#cancel** directive.

```velocity
##--- NB : do not rewrite the file if it already exists
#if($target.outputFileExists() )#cancel("File already exists")#end

```

### Maps of lists&#x20;

With Velocity, you can create a "map" of "anything". A map can contain any object, even lists.

```velocity
## --- Example 1 :
#set( $list1 = [ 0, 1, 2 ] )
#set( $list2 = [ "", "A", "B", "C", "D" ] )
## A map of lists :
#set( $m = {"k1" : $list1 , "k2" : $list2} )

## --- Example 2 (literal):
#set( $m2 = {
  "int" : [ 100, 200, 300 ] , 
  "str" : [ "AAA", "BB", "CCC", "D" ] 
  } )

## --- Usage 
$m["k2"]
$m["k2"][2]

$m2["int"][1]
```

