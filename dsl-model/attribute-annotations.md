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

Since version 3.2.0\
The default value in the database.&#x20;

### @DbName(string)

Since version 3.2.0\
The name in the database (for example the column name in a relational database)

### @DbSize(string)

Since version 3.2.0 \
_Deprecated - Do not use_

### @DbType(string)

Since version 3.2.0 \
The type in the database (for example the column type in a relational database)

### @DefaultValue(string)

Since version 3.2.0\
The default value&#x20;

### @Embedded

The entity referenced by the attribute must be embedded (typically for NoSQL databases).\
Applicable with "references" to embed them in the current entity.

### @FetchTypeEager

Since version 3.3.0 \
Define an "Eager Loading" fetch type for a link, typically for ORM (JPA, Doctrine, etc ).

### @FetchTypeLazy

Since version 3.3.0 \
Define a "Lazy Loading" fetch type for a link, typically for ORM (JPA, Doctrine, etc ).

### @FK( \[fkName,] referencedEntity\[.attribute] )

Since version 3.3.0\
Define a Foreign Key or a Foreign Key part \
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

The attribute value must be in the future (after current date).\
Usable for field validation rules.\
Applicable with "date" type.

### @Id

The attribute is the ID (or Primary Key) for the current entity.\
For an entity with a composite ID (composite Primary Key), put this annotation on each attribute that is part of the ID.\
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

Since version 3.2.0\
Defines the initial value.

### @InputType(string)

Since version 3.2.0 \
Defines the input type usable for the field (for example an HTML input type).

### @Insertable(boolean)&#x20;

Since version 3.3.0 \
\
Examples :\
`@Insertable(true)`\
`@Insertable(false)`

### @Label(string)

Since version 3.2.0 \
Defines the label usable for the field (for example an HTML label).

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













