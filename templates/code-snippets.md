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



