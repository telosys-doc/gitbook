# Tags

As Telosys aims to enable highly customizable templates \(and predefined annotations are usually not sufficient to handle all special cases\) since version 3.3.0 **tags** have been added.

Tags are a very simple way to easily customize your templates by adding as much additional information as you want.

### Set tags in model

Each attribute can have **0 to N tags**. 

Like annotations, tags provide additional information usable during the code generation. But, unlike annotations, **tags do not have predefined names**. The user can define as many tags as he wants.

A tag is **any name** starting with "**\#**" and optionally having a value.  
If the tag has a **value** then the value is defined between "**\(**" and "**\)**".

Examples of tags :

```text
MyEntity {
id  : int { @Id } ;

// tag "mandatory " (without value) :
comment : string { #mandatory } ;

// tag "OpenAPIFormat" with value :
val : long  { #OpenAPIFormat(int64) } ;

}
```



### Use tags in templates

In a template you can define conditions based on the presence or absence of a tag and whether to retrieve the value of the tag.

* $attrib.**hasTag**\("tagName"\)
* $attrib.**tagValue**\("tagName"\)

Example : check tag presence and use its value if present

```text
#if ( $attrib.hasTag("OpenAPIFormat") )  
$attrib.tagValue("OpenAPIFormat")
#end
```

