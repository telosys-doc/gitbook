# Annotations

Each **entity**, **attribute** or **link** can have **0 to N annotations**. \
Annotations provide additional information usable during the code generation. \
An annotation is a **predefined name** starting with "**@**". \
Some annotations may have **values** specified between "**(**" and "**)**". \
For attributes and links all annotations must be located in the block delimited by "**{**" and "**}**".

NB : since version 4.0 the useless comma between annotations is prohibited and must be removed

### @Abstract

Marks an entity as "abstract"&#x20;

Scope : **entity** /  Since : **4.0.0**

### @AggregateRoot

Marks an entity as "aggregate root" (useful to define "DDD aggregates" )

Scope : **entity**  /  Since : **4.0.0**

### @AutoIncremented

This annotation is a synonym/shortcut for "**@GeneratedValue(IDENTITY)**".\
The attribute value relies on the database’s auto-increment feature.\
Only applicable to numeric types.

Scope : **attribute**  /  Since : **2.0.0** &#x20;

### @Cascade(string \[, string, ...] )&#x20;

Defines how to manage ORM "cascade" options for a link \
Valid options : ALL or A, MERGE or M, PERSIST or P, REFRESH or REF, REMOVE or REM

Scope : **link**  /  Since : **4.1.0**&#x20;

Examples :

&#x20;`@Cascade(MERGE)  @Cascade(REMOVE)  @Cascade(MERGE,REMOVE)  @Cascade(M,REM)`&#x20;

### @Context(string)

Defines the context to which the entity belongs

Scope : **entity**  /  Since : **4.0.0**

### @DbCatalog(string)

Defines the database catalog to which the entity table belongs

Scope : **entity**  /  Since : **4.0.0**

### @DbComment(string)

The comment in the database (typically a column comment or table comment in a relational database)

Scope : **attribute & entity**  /  Since : **3.2.0** for attribute, **4.0.0** for entity

### @DbDefaultValue(string)

The default value in the database.&#x20;

Scope : **attribute**  /  Since : **3.2.0**&#x20;

### @DbName(string)

The name in the database (for example the column name in a relational database)

Scope : **attribute**  /  Since : **3.2.0**&#x20;

### @DbSchema(string)

Defines the database schema to which the entity table belongs

Scope : **entity**  /  Since : **4.0.0**

### ~~@DbSize(string)~~

_**Deprecated** - Do not use_

_Scope : attribute  /_  Since : 3.2.0

### @Db**Table(str**ing)

Defines the database table associated with the entity

Scope : **entity**  /  Since : **4.0.0**

### @Db**Tablespace(str**ing)

Defines the database tablespace where the entity table is located

Scope : **entity**  /  Since : **4.0.0**

### @DbType(string)

The attribute type in the database (for example the column type in a relational database)

Scope : **attribute**  /  Since : **3.2.0**&#x20;

### @Db**View**

Marks the entity as a "view" in the database

Scope : **entity**  /  Since : **4.0.0**

### @DefaultValue(string)

The default value for an attribute

Scope : **attribute**  /  Since : **3.2.0**&#x20;

### @Domain(string)

Defines the "domain" to which the entity belongs

Scope : **entity**  /  Since : **4.0.0**

### @Embedded

The entity referenced by the attribute must be embedded (typically for NoSQL databases).\
Applicable with "references" to embed them in the current entity.

Scope : **link**  /  Since : **3.0.0**

### @**Extends**(string)

Defines the "superclass" of an entity (inheritance)

Scope : **entity**  /  Since : **4.0.0**

### @FetchTypeEager

Define an "Eager Loading" fetch type for a link, typically for ORM (JPA, Doctrine, etc ).

Scope : **link**  /  Since : **3.3.0**

### @FetchTypeLazy

Define a "Lazy Loading" fetch type for a link, typically for ORM (JPA, Doctrine, etc ).

Scope : **link**  /  Since : **3.3.0**

### @FK( \[fkName,] referencedEntity\[.attribute] )

Define a "Foreign Key" or a "Foreign Key part"&#x20;

Scope : **attribute**  /  Since : **3.3.0**\
\
Syntax :\
`// FK referencing an entity with a basic PK (single attribute)`\
`@FK( ReferencedEntity ) // without FK name (default name)`\
`@FK( ForeignKeyName, ReferencedEntity ) // with FK name`\
`---`\
`// FK referencing an entity with a compositePK (N attributes)`\
`@FK( ForeignKeyName, ReferencedEntity.ReferencedAttribute )`\
\
Examples :\
`// FK referencing "Brand" entity (with default FK name)`\
`brandId : int { @FK(Brand) }; // PK inference` \
`-----`\
`// FK referencing "Brand" entity (with default FK name)`\
`brandId : int { @FK(Brand.id) }; // explicit PK attribute`\
`-----`\
`// FK referencing "Group" entity (with FK name)`\
`groupCode : string { @FK(FK_EMP_GRP, Group) } ;`\
`-----`\
`// FK referencing "SubGroup" entity (composite PK)`\
`groupCode : string { @FK(FK_PER_SUBGRP, SubGroup.groupCode ) };` \
`subgroupId : int   { @FK(FK_PER_SUBGRP, SubGroup.subgroupId) };`

### @Future

The attribute date value must be in the future (after current date).\
Usable for field validation rules. Applicable with "date" type.

Scope : **attribute**  /  Since : **2.0.0**

### @GeneratedValue(string \[, string, ...])

Defines the generated value strategy ("AUTO", "IDENTITY", SEQUENCE" or "TABLE") for an attribute. This is useful for ORM like JPA, etc.

Scope : **attribute**  (applicable to **numeric types** only)  /  Since : **3.4.0** &#x20;

Strategies:

* **AUTO** - the ORM chooses the most appropriate strategy

> @GeneratedValue(**AUTO**)<br>

* **IDENTITY** - relies on the database’s auto-increment feature (int/long)

> @GeneratedValue(**IDENTITY**)<br>

* **SEQUENCE** - uses a database sequence to generate the value

> @GeneratedValue( **SEQUENCE**, **sequenceName**  \[, allocationSize \[, initialValue ] ]  )\
> \- sequenceName = the sequence used to provided the generated value\
> \- allocationSize (optional) = ORM-level optimization, prefetching/batching in memory (for ORM like JPA/HIbernate)\
> \- initialValue (optional) = first generated value<br>

* **TABLE** - simulates a sequence using a special table that stores the next value

> @GeneratedValue( **TABLE**,  **pkValue**  \[, allocationSize \[, initialValue ] ]  )> \
> \- pkValue = the primary key value used to store the current value in the special table \
> (must be unique to identify the entity/attribute)\
> \- allocationSize (optional) : ORM-level optimization, prefetching/batching in memory (for ORM like JPA/HIbernate)\
> \- initialValue (optional) = first generated value<br>

### @Id

The attribute is the "ID" (or "Primary Key") for the current entity.\
For an entity with a composite ID (composite Primary Key), put this annotation on each attribute that is part of the ID.

Scope : **attribute**  /  Since : **1.0.0**

Applicable with any basic type.\
For a composite Primary Key just put an "@Id" annotation for each attribute that is part of the key.\
Examples :\
`Badge { // Simple key => single "@Id"`\
&#x20; `id   : int { @Id } ;`\
&#x20; `name : string ;` \
`}`\
`SubGroup { // Composite key => multiple "@Id"`\
&#x20; `groupCode : string { @Id } ;`\
&#x20; `sectionId : int { @Id } ;`\
&#x20; `name : string ;`\
`}`

### @InitialValue(string)

Sets the initial value of the attribute.

Scope : **attribute**  /  Since : **3.2.0**

### @InMemoryRepository

Marks an entity as fully stored in memory.\
All occurrences can be accessed directly in memory (can be useful for static datasets).

Scope : **entity**  /  Since : **4.0.0**

### @InputType(string)

Defines the input type usable for a field (for example an HTML input type).

Scope : **attribute**  /  Since : **3.2.0**

### @Insertable(boolean)&#x20;

Defines if the link is "insertable" or not. &#x20;

Scope : **link**  /  Since : **3.3.0**

Examples :&#x20;

```
@Insertable(true)
@Insertable(false)
```

### @JoinEntity&#x20;

Marks the current entity as a "Join Entity" (an entity referencing two other entities in order to manage a many-to-many relationship).

Scope : **entity**  /  Since :  **4.1.0**

### @Label(string)

Defines a label usable for the attribute, for example in GUI (HTML label for an input field, etc)

Scope : **attribute**  /  Since : **3.2.0**

### @LinkByAttr(string \[, string, ...])&#x20;

Defines a link based on the given attribute(s) name(s) referencing the Primary Key.

For multiple attributes (in case of composite PK) each attribute must define the referenced attribute in the target entity.

Scope : **link**  /  Since : **3.3.0**\
\
Syntax :&#x20;

```
 // simple PK with a single attribute :
 @LinkByAttr(attributeName) 
 // composite PK with N columns (in PK order) :
 @LinkByAttr(attributeName1, attributeName2 [, attributeNameX ] )
```

Example :&#x20;

```
Point { 
   x : int { @Id @DbName(X) } ;  // PK 
   y : int { @Id @DbName(Y) } ;  // PK
   name : string ;
}

Line {
   id : int { @Id } ;
   color : string ;
	
   point1X : int  { @DbName(X1) } ;
   point1Y : int  { @DbName(Y1) } ;
	
   point2X : int  { @DbName(X2) } ;
   point2Y : int  { @DbName(Y2) } ;

   // LINKS 
   point1 : Point { @LinkByAttr(point1X , point1Y ) } ;
   point2 : Point { @LinkByAttr(point2X , point2Y ) } ;
}
```

### @LinkByFK(string)&#x20;

Defines a link based on the given Foreign Key name.

Scope : **link**  /  Since : **3.3.0**

Syntax :&#x20;

```
  @LinkByFK(foreignKeyName) 
```

Example : &#x20;

```
Area {
   id : int { @Id } ; 
   name : string ;
   // Foreign Key
   countryCode : string { @FK(FK_AREA_COUNTRY, Country) } ;
   // Link definition based on Foreign Key
   country : Country  { @LinkByFK(FK_AREA_COUNTRY) } ; 
}
```

### @LinkByJoinEntity(string)

Defines a link based on the given "join entity" name.\
Usable with "many to many" links to define a "join table".

Scope : **link**  /  Since : **3.3.0**

Syntax :&#x20;

```
  @LinkByJoinEntity(entityName)
```

Example : &#x20;

```
Employee {
   id   : int { @Id } ; 
   name : string ;
   // EmployeeGroup is a "join entity" to associate employees and workgroups
   workgroups : Workgroup[] { @ManyToMany 
                @LinkByJoinEntity(EmployeeGroup) } ;
}
```

### @LongText

Marks the attribute as "long text" (for example a text with several lines). \
This annotation can be used for HTML "text area" or database "CLOB".\
Applicable with "string" basic type.

Scope : **attribute**  /  Since : **2.0.0**

### @ManyToMany&#x20;

Defines a "many to many" cardinality for a link.\
Usable for ORM code generation (JPA, etc)

Scope : **link**  /  Since : **3.3.0**

### @MappedBy(attributeName)

Defines the "mappedBy" attribute for a link.\
Usable for an "**inverse side**" relationship.  \
Can be used with @OneToMany, @OneToOne, @ManyToMany\
(not with @ManyToOne, which is always the "owning side")

Scope : **link**  /  Since : **3.3.0**

Example :\
`shops : Shop[] { @MappedBy(employee) } ;`

### @Max(decimal)

To set the maximum acceptable value.\
Usable for field validation rules.\
Applicable with "numeric" types.

Scope : **attribute**  /  Since : **2.0.0**

### @Max**Len**(int)

To set the maximum acceptable length.\
Usable for field validation rules and GUI fields definition.

Scope : **attribute**  /  Since : **4.0.0**  (replaces "@SizeMax" )

### @Min(decimal)

To set the minimum acceptable value.\
Usable for field validation rules.\
Applicable with "numeric" types.

Scope : **attribute**  /  Since : **2.0.0**

### @M**inLen**(int)

To set the minimum acceptable length.\
Usable for field validation rules and GUI fields definition.

Scope : **attribute**  /  Since : **4.0.0**  (replaces "@SizeMin" )

### @NotBlank

The attribute value cannot be blank.\
Usable for field validation rules.

Scope : **attribute**  /  Since : **2.0.0**

### @NotEmpty

The attribute value cannot be empty.\
Usable for field validation rules.

Scope : **attribute**  /  Since : **2.0.0**

### @NotNull

The attribute value cannot be null.\
Usable for field validation rules and SQL databases.

Scope : **attribute**  /  Since : **2.0.0**

### @ObjectType

The attribute type must be converted to "object/wrapper type" in the target language (for example for Java).\
No effect if not supported by the target language.\
Applicable with any basic type.

Scope : **attribute**  /  Since : **2.0.0**

### @OneToOne&#x20;

Defines a "one to one" cardinality for a link.\
Usable for ORM code generation (JPA, etc)

Scope : **link**  /  Since : **3.3.0**

### @Optional

Defines an "optional" relationship for a link.\
Usable for ORM code generation (JPA, etc)

Scope : **link**  /  Since : **3.3.0**

### @OrphanRemoval

Set 'orphanRemoval'  to true in ORM (JPA, etc)

Scope : **link**  /  Since : **4.1.0**

### @Pa**ckage(string)**

Defines the "package" to which the entity belongs

Scope : **entity**  /  Since : **4.0.0**

### @Past

The attribute value must be in the past (before current date).\
Usable for field validation rules.\
Applicable with "date" type.

Scope : **attribute**  /  Since : **2.0.0**

### @Pattern(string)

Defines a pattern usable for field validation, for example a "RegEx" pattern.

Scope : **attribute**  /  Since : **3.2.0**

### @PrimitiveType

The attribute type must be converted to "primitive type" in the target language (for example for Java).\
No effect if not supported by the target language.\
Applicable with any basic type.

Scope : **attribute**  /  Since : **2.0.0**

### @ReadOnly

Marks the entity as "readonly"

Scope : **entity**  /  Since : **4.0.0**

### @Size(size)

Defines the attribute size.\
The size is defined with "precision" and "scale" if necessary (eg "6" or "6,2")

Scope : **attribute**  /  Since : **4.0.0**

### ~~@SizeMax(int)~~

_**Deprecated** - Do not use - Use "**@MaxLen**" instead_

_Defines the maximum acceptable size of the attribute value_.\
&#xNAN;_&#x53;cope : attribute  /_  Since : 2.0.0

### ~~@SizeMin(int)~~

_**Deprecated** - Do not use - Use "**@MinLen**" instead_

_Defines the minimum acceptable size of the attribute value_.\
&#xNAN;_&#x53;cope : attribute  /_  Since : 2.0.0

### @Transient

Define an attribute as "transient" (for example in a Java class or with an ORM like JPA)

Scope : **attribute & link**  /  Since : **3.3.0**

### @Un**iqu**e

Marks the attribute as unique for the entity.

Scope : **attribute**  /  Since : **4.0.0 &#x20;**_**(experimental)**_

### @UnsignedType

The attribute type must be converted to "unsigned type" in the target language (for example for C/C++).\
No effect if not supported by the target language.\
Applicable with any basic type.

Scope : **attribute**  /  Since : **3.0.0**

### @Updatable(boolean)&#x20;

Defines if the link is "updatable" or not. &#x20;

Scope : **link**  /  Since : **3.3.0**

Examples :&#x20;

```
@Updatable(true)
@Updatable(false)
```













