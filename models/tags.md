# Tags

As Telosys aims to provide highly customizable models (and predefined annotations are usually not sufficient to handle all special cases) in version 3.3.0 "**tags**" have been added for attributes and since version 4.0.0 they can be used everywhere (entity, attribute and link).

Tags are a very simple way to easily customize your models by adding as much additional information as you want.

### Set tags in model

Each **entity**, **attribute** or **link** can have **0 to N tags**.&#x20;

Like annotations, tags provide additional information usable during the code generation. But, unlike annotations, **tags do not have predefined names**. The user can define as many tags as he wants.

A tag is **any name** starting with "**#**" and optionally having a value.\
If the tag has a **value** then the value is defined between "**(**" and "**)**".

Examples of tags :

```
MyEntity {
id  : int { @Id } ;

// tag "mytag" (without value) :
comment : string { #mytag } ;

// tag "OpenAPIFormat" with value :
val : long  { #OpenAPIFormat(int64) } ;

}
```



### Use tags in templates

In a template you can define conditions based on the presence (or absence) of a tag \
and you can retrieve the value of a tag (with default value if necessary).

To do this, use the following syntax:

* $x.**hasTag**("tagName")
* $x.**tagValue**("tagName")
* $x.**tagValue**("tagName", "defaultValue")
* $x.**tagValueAsBoolean**("tagName", true/false)
* $x.**tagValueAsInt**("tagName", 123)

Example : check tag presence and use its value if present

```
#if ( $attrib.hasTag("OpenAPIFormat") )  
$attrib.tagValue("OpenAPIFormat")
#end
```

See [Telosys objects](../bundles/telosys-objects.md) reference guide for detailed information \
(objects $entity, $attribute and $link).
