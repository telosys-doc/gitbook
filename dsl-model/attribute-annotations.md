# Annotations

Each entity, attribute or link can have **0 to N annotations**. \
Annotations provide additional information usable during the code generation. \
An annotation is a **predefined name** starting with "**@**". \
Some annotations may have **values** specified between "**(**" and "**)**". \
For attributes and links all annotations must be located in the block delimited by "**{**" and "**}**".

### @Abstract

Marks an entity as "abstract"&#x20;

Scope : **entity** /  Since : **4.0.0**

### @AggregateRoot

Marks an entity as "aggregate root" (useful to define "DDD aggregates" )

Scope : **entity**  /  Since : **4.0.0**

### @AutoIncremented

The attribute is supposed to be auto-incremented (for example for an auto-incremented key)\
Applicable only with "numeric" types

Scope : **attribute**  /  Since : **2.0.0**

### @Context(string)

Defines the context to which the entity belongs

Scope : **entity**  /  Since : **4.0.0**

### @DbCatalog(string)

Defines the database catalog to which the entity table belongs

Scope : **entity**  /  Since : **4.0.0**

### @DbComment(string)

The comment in the database (typically a column comment in a relational database)

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

### @DbSize(string)

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

Defines the generated value strategy ("AUTO", "IDENTITY", SEQUENCE" or "TABLE") for an attribute.

Scope : **attribute**  /  Since : **3.4.0**

Syntax :

`@GeneratedValue(AUTO)` \
`@GeneratedValue(IDENTITY)` \
`@GeneratedValue(SEQUENCE [, GeneratorName, SequenceName` \
&#x20; `[, AllocationSize ] ])` \
`@GeneratedValue(TABLE [, GeneratorName, TableName` \
&#x20; `[, PkColumnName, PkColumnValue, ValueColumnName [, AllocationSize ] ] ])`

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

Examples :\
`@Insertable(true)`\
`@Insertable(false)`

### @Label(string)

Defines the label usable for the field (for example an HTML label).

Scope : **attribute**  /  Since : **3.2.0**

### @LinkByAttr(string)&#x20;

Since version 3.3.0 \
Defines a link based on the given attribute(s) name(s).\
For multiple attributes (in case of composite PK) each attribute must define the referenced attribute in the target entity by using the ">" character ( "a > b" for  "a" referencing "b").\
\
Syntax :\
`// simple PK with a single attribute (ref not required) @LinkByAttr(attribName) // referenced PK inference`\
`// composite PK with N columns (referenced required)`\
`@LinkByAttr(attr1 > refAttr1 , attr2 > refAttr2 , ...)` \
\
Examples :\
`Point {`\
&#x20; `x : int { @Id } ;`\
&#x20; `y : int { @Id } ;`\
&#x20; `label : string ;`\
`}`\
`-----`\
`Line {`\
&#x20; `id : short { @Id } ;`\
&#x20; `name : string ;`\
&#x20; `// Point 1`\
&#x20; `point1X : int ;`\
&#x20; `point1Y : int ;`\
&#x20; `// Point 2`\
&#x20; `point2X : int ;`\
&#x20; `point2Y : int ;`\
&#x20; `// Link to point`\
&#x20; `point1 : Point { @LinkByAttr(point1X > x, point1Y > y) } ;`\
&#x20; `point2 : Point { @LinkByAttr(point2X > x, point2Y > y) } ;`\
`}`\


### @LinkByFK(string)&#x20;

Since version 3.3.0 \
Defines a link based on the given Foreign Key name.\
\
Examples :\
`// Link based on Foreign Key "FK_PERSON_SUBGROUP"`\
`subGroup : SubGroup { @LinkByFK(FK_PERSON_SUBGROUP) } ;`

### @LinkByJoinEntity(string)

Since version 3.3.0\
Defines a link based on the given "join entity" name.\
Usable with "many to many" link to define a "join table".\
\
Example :\
`workgroups : Workgroup[] { @ManyToMany` \
&#x20;            `@LinkByJoinEntity(EmployeeGroup) } ;`

### @LongText

The attribute is a "long text" for example a text of several lines. \
This annotation can be used for HTML "text area" or database "CLOB".\
Applicable with "string" basic type.

### @ManyToMany&#x20;

Since version 3.3.0 \
Defines a "many to many" cardinality for a link.\
Usable for ORM code generation (JPA, etc)

### @MappedBy(attributeName)

Since version 3.3.0 \
Defines the "mappedBy" attribute for a link.\
Usable for an "inverse side" relationship.\
\
Example :\
`shops : Shop[] { @MappedBy(employee) } ;`

### @Max(decimal)

To set the maximum acceptable value.\
Usable for field validation rules.\
Applicable with "numeric" types.

### @Min(decimal)

To set the minimum acceptable value.\
Usable for field validation rules.\
Applicable with "numeric" types.

### @NotBlank

The attribute value cannot be blank.\
Usable for field validation rules.

### @NotEmpty

The attribute value cannot be empty.\
Usable for field validation rules.

### @NotNull

The attribute value cannot be null.\
Usable for field validation rules and SQL databases.

### @ObjectType

The attribute type must be converted to "object/wrapper type" in the target language (for example for Java).\
No effect if not supported by the target language.\
Applicable with any basic type.

### @OneToOne&#x20;

Since version 3.3.0 \
Defines a "one to one" cardinality for a link.\
Usable for ORM code generation (JPA, etc)

### @Optional

Since version 3.3.0 \
Defines an "optional" relationship for a link.\
Usable for ORM code generation (JPA, etc)

### @Past

The attribute value must be in the past (before current date).\
Usable for field validation rules.\
Applicable with "date" type.

### @Pattern(string)

Since version 3.2.0 \
Defines a pattern usable for field validation, for example a RegEx pattern.

### @PrimitiveType

The attribute type must be converted to "primitive type" in the target language (for example for Java).\
No effect if not supported by the target language.\
Applicable with any basic type.

### @SizeMax(int)

To set the maximum acceptable size of the attribute value.\
Usable for field validation rules and GUI fields definition.

### @SizeMin(int)

To set the minimum acceptable size of the attribute value.\
Usable for field validation rules.

### @Transient

Since version 3.3.0

To define an attribute as "transient" (for example in a Java class or with an ORM like JPA)

### @UnsignedType

The attribute type must be converted to "unsigned type" in the target language (for example for C/C++).\
No effect if not supported by the target language.\
Applicable with any basic type.

### @Updatable(boolean)&#x20;

Since version 3.3.0 \
\
Examples :\
`@Updatable(true)`\
`@Updatable(false)`













