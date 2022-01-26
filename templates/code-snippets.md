# Code snippets

### Iterate over all entities defined in the model

```
#foreach( $e in $model.allEntites )
		...
#end
```

### Iterate over entity attributes

```
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

```
#foreach( $link in $entity.links )
		...
#end

```

### Execute a ".vm" file located in a model folder

The function "$fn.fileFromModel(fileName)" returns an instance of "file" located in the current model. If the file exists, its content is loaded and evaluated with "#evaluate" directive.

```
#set( $file = $fn.fileFromModel("model-init.vm") )
#if($file.exists())#evaluate($file.loadContent())#end
```

### Get the class of an object

As all Velocity references ( "$xxx" ) are references of Java objects, sometimes it could be useful to know the object's class. To do this, just use "**class.name**" (full name with package) or "**class.simpleName**" (only the class name without package)

```
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

```
##--- NB : do not rewrite the file if it already exists
#if($target.outputFileExists() )#cancel("File already exists")#end

```
