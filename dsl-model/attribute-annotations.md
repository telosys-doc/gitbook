# Attribute annotations

Each attribute can have **0 to N annotations**.   
Annotations provide additional information usable during the code generation.   
An annotation is a predefined name starting with "**@**".   
Some annotations may have **values** specified between "**\(**" and "**\)**".   
All annotations must be located in the block delimited by "**{**" and "**}**".

### @AutoIncremented

The attribute is supposed to be auto-incremented \(for example for an auto-incremented key\)  
Applicable with "numeric" types

### @Embedded

The entity referenced by the attribute must be embedded \(typically for NoSQL databases\).  
Applicable with "references" to embed them in the current entity.

### @Future

The attribute value must be in the future \(after current date\).  
Applicable with "date" type.

### @Id

The attribute is the ID \(or Primary Key\) for the current entity.  
For an entity with a composite ID \(composite Primary Key\), put this annotation on each attribute that is part of the ID.  
Applicable with any basic type.

### @LongText

The attribute is a "long text" for example a text of several lines. This annotation can be used for HTML "text area" or database "CLOB".  
Applicable with "string" basic type.

### @Max\(value\)

To set the maximum acceptable value.  
For example for field validation rules.  
Applicable with "numeric" types.

### @Min\(value\)

To set the minimum acceptable value.  
For example for field validation rules.  
Applicable with "numeric" types.

### @NotBlank

The attribute value cannot be blank.

### @NotEmpty

The attribute value cannot be empty.

### @NotNull

The attribute value cannot be null.

### @ObjectType

The attribute type must be converted to "object/wrapper type" in the target language \(for example for Java\).  
No effect if not supported by the target language.  
Applicable with any basic type.

### @Past

The attribute value must be in the past \(before current date\).  
Applicable with "date" type.

### @PrimitiveType

The attribute type must be converted to "primitive type" in the target language \(for example for Java\).  
No effect if not supported by the target language.  
Applicable with any basic type.

### @SizeMax\(value\)

To set the maximum acceptable size of the attribute value.  
For example for field validation rules.

### @SizeMin\(value\)

To set the minimum acceptable size of the attribute value.  
For example for field validation rules.

### @UnsignedType

The attribute type must be converted to "unsigned type" in the target language \(for example for C/C++\).  
No effect if not supported by the target language.  
Applicable with any basic type.

xx













