# Attribute annotations

Each attribute can have **0 to N annotations**.   
Annotations provide additional information usable during the code generation.   
An annotation is a **predefined name** starting with "**@**".   
Some annotations may have **values** specified between "**\(**" and "**\)**".   
All annotations must be located in the block delimited by "**{**" and "**}**".

### @AutoIncremented

The attribute is supposed to be auto-incremented \(for example for an auto-incremented key\)  
Applicable with "numeric" types

### @DbComment\(string\)

Since version 3.2.0  
The comment in the database \(typically a column comment in a relational database\)

### @DbDefaultValue\(string\)

Since version 3.2.0  
The default value in the database. 

### @DbName\(string\)

Since version 3.2.0  
The name in the database \(for example the column name in a relational database\)

### @DbSize\(string\)

Since version 3.2.0   
Deprecated - Do not use

### @DbType\(string\)

Since version 3.2.0   
The type in the database \(for example the column type in a relational database\)

### @DefaultValue\(string\)

Since version 3.2.0  
The default value 

### @Embedded

The entity referenced by the attribute must be embedded \(typically for NoSQL databases\).  
Applicable with "references" to embed them in the current entity.

### @FetchTypeEager

Since version 4.0.0   
Define an "Eager Loading" fetch type for a link, typically for ORM \(JPA, Doctrine, etc \).

### @FetchTypeLazy

Since version 4.0.0   
Define a "Lazy Loading" fetch type for a link, typically for ORM \(JPA, Doctrine, etc \).

### @FK\( string \[, string, string\] \)

Since version 4.0.0  
xxx

### @Future

The attribute value must be in the future \(after current date\).  
Usable for field validation rules.  
Applicable with "date" type.

### @Id

The attribute is the ID \(or Primary Key\) for the current entity.  
For an entity with a composite ID \(composite Primary Key\), put this annotation on each attribute that is part of the ID.  
Applicable with any basic type.

### @InitialValue\(string\)

Since version 3.2.0  
Defines the initial value.

### @InputType\(string\)

Since version 3.2.0   
Defines the input type usable for the field \(for example an HTML input type\).

### @Insertable\(boolean\) 

Since version 4.0.0   
Examples :  
`@Insertable(true)  
@Insertable(false)`

### @Label\(string\)

Since version 3.2.0   
Defines the label usable for the field \(for example an HTML label\).

### @LinkByAttr\(string\) 

Since version 4.0.0   
Defines a link based on the given attribute name.

### @LinkByCol\(string\) 

Since version 4.0.0   
Defines a link based on the given column name.

### @LinkByFK\(string\) 

Since version 4.0.0   
Defines a link based on the given Foreign Key name.

### @LinkByJoinEntity\(string\)

Since version 4.0.0   
Defines a link based on the given "join entity" name.

### @LongText

The attribute is a "long text" for example a text of several lines.   
This annotation can be used for HTML "text area" or database "CLOB".  
Applicable with "string" basic type.

### @ManyToMany 

Since version 4.0.0   
Defines a "many to many" relationship for a link.

### @MappedBy\(string\)

Since version 4.0.0   
xxx

### @Max\(decimal\)

To set the maximum acceptable value.  
Usable for field validation rules.  
Applicable with "numeric" types.

### @Min\(decimal\)

To set the minimum acceptable value.  
Usable for field validation rules.  
Applicable with "numeric" types.

### @NotBlank

The attribute value cannot be blank.  
Usable for field validation rules.

### @NotEmpty

The attribute value cannot be empty.  
Usable for field validation rules.

### @NotNull

The attribute value cannot be null.  
Usable for field validation rules and SQL databases.

### @ObjectType

The attribute type must be converted to "object/wrapper type" in the target language \(for example for Java\).  
No effect if not supported by the target language.  
Applicable with any basic type.

### @OneToOne 

Since version 4.0.0   
Defines a "one to one" relationship for a link.

### @Optional

Since version 4.0.0   
xxx

### @Past

The attribute value must be in the past \(before current date\).  
Usable for field validation rules.  
Applicable with "date" type.

### @Pattern\(string\)

Since version 3.2.0   
xxx

### @PrimitiveType

The attribute type must be converted to "primitive type" in the target language \(for example for Java\).  
No effect if not supported by the target language.  
Applicable with any basic type.

### @SizeMax\(int\)

To set the maximum acceptable size of the attribute value.  
Usable for field validation rules and GUI fields definition.

### @SizeMin\(int\)

To set the minimum acceptable size of the attribute value.  
Usable for field validation rules.

### @UnsignedType

The attribute type must be converted to "unsigned type" in the target language \(for example for C/C++\).  
No effect if not supported by the target language.  
Applicable with any basic type.

### @Updatable\(boolean\) 

Since version 4.0.0   
Examples :  
`@Updatable(true)  
@Updatable(false)`



xxxxx













