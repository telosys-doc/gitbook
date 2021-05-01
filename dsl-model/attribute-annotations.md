# Attribute annotations

Each attribute can have **0 to N annotations**.   
Annotations provide additional information usable during the code generation.   
An annotation is a predefined name starting with "**@**".   
Some annotations may have **values** specified between "**\(**" and "**\)**".   
All annotations must be located in the block delimited by "**{**" and "**}**".

### @AutoIncremented

The attribute is supposed to be auto-incremented \(for example for an auto-incremented key\)  
Applicable with "numeric" basic types

### @Embedded

The entity referenced by the attribute must be embedded \(typically for NoSQL databases\).  
Applicable with "references" to embed them in the current entity.

### @Future

The attribute value must be in the future.  
Applicable with "date" basic type.

### @Id

The attribute is the ID \(or Primary Key\) for the current entity.  
For an entity with a composite ID \(composite Primary Key\), put this annotation on each attribute that is part of the ID.  
Applicable with any basic type.

### @LongText

xx

### @Max\(int value\)

xx

### @Min\(int value\)

xx

### @NotBlank

xx

### @NotEmpty

xx

### @NotNull

xx

### @ObjectType

xx

### @Past

xx

### @PrimitiveType

xx

### @SizeMax\(int value\)

xx

### @SizeMin\(int value\)

xx

### @UnsignedType

xx

xx













