# Telosys directives

xx





## \#assertFalse

\( Telosys specific directive - since version 2.0.7 \)

Checks that the value of the first argument is FALSE.  
Otherwise throws an error with the given message.

Examples :

```text
 #assertFalse( $flag, "Flag is true (false expected)" ) 
 #assertFalse( $entity.hasCompositePrimaryKey(), "Composite Primary Key not supported" ) 
```



## \#assertTrue

\( Telosys specific directive - since version 2.0.7 \)

Checks that the value of the first argument is TRUE.  
Otherwise throws an error with the given message.

Examples :

```text
 #assertTrue( $flag, "Flag is not true!" ) 
 #assertTrue( $entity.hasPrimaryKey(), "Primary Key required!" )
```



## \#checkId

\( Telosys specific directive - since version 3.0.0 \)

Checks the existence of ID/Primary Key in the given entity   
Throws an error if there's no ID/Primary Key defined in the entity.

Examples :

```text
 #checkId( $entity) 
```



## \#error

\( Telosys specific directive - since version 2.0.7 \)

Throws an error with the given message

Examples :

```text
 #if( $flag ) 
 #error( "Flag is true!" ) 
 #end 

 #if( ! $entity.hasPrimaryKey() ) 
 #error( "Primary Key required!" ) 
 #end 
```



## \#using

\( Telosys specific directive - since version 2.0.7 \)

Declares that the current template will use unusual objects or variables which must therefore be defined in the context.  
This directive verifies that all required objects or variables are defined in the Velocity context.  
It throws an error if one of the given objects is not defined.  
Often used to verify that required specific variables have been defined.

Examples :

```text
 #using( "var1" ) 
 #using( "var1", "var2" ) 
 #using( "var1", "var2", "foo", "bar" ) 

 #using( '$var1' ) 
 #using( '$var1', '$var2' ) 
```

