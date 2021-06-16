# Code snippets

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

If the file exists, its content is loaded and evaluated with "\#evaluate" directive

```text
#set( $file = $fn.fileFromModel("model-init.vm") )
#if($file.exists())#evaluate($file.loadContent())#end
```



