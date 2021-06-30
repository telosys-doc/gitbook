# Code snippets

### Iterate over all entities defined in the model

```text
#foreach( $e in $model.allEntites )
		...
#end
```

### Iterate over entity attributes

```text
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

```text
#foreach( $link in $entity.links )
		...
#end

```

### Execute a ".vm" file located in a model folder

The function "$fn.fileFromModel\(fileName\)" returns an instance of "file" located in the current model. If the file exists, its content is loaded and evaluated with "\#evaluate" directive.

```text
#set( $file = $fn.fileFromModel("model-init.vm") )
#if($file.exists())#evaluate($file.loadContent())#end
```

### Get the class of an object

As all Velocity references \( "$xxx" \) are references of Java objects, sometimes it could be useful to know the object's class. To do this, just use "**class.name**" \(full name with package\) or "**class.simpleName**" \(only the class name without package\)

```text
#set( $v = 12 )
$v.class.name 
$v.class.simpleName 

#set( $s = "abc" )
$s.class.name 
$s.class.simpleName 

$entity.class.name 

$now.class.simpleName 
```

