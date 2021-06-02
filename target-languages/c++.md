# C++

C++ language is supported since version : **3.3.0**

To define **C++** as the target language in a template file :

```text
#set( $env.language = 'C++' )
```

The information below shows the behavior of the generator when 'C++' is the current target language.  


## Types conversion 

The table below describes how the model neutral types are automatically converted to C++ types.

| Model type | Default |  @UnsignedType |  @NotNull |  @PrimitiveType |  @ObjectType |
| :--- | :--- | :--- | :--- | :--- | :--- |
| string | string | string | string | string | string |
| byte | char | unsigned char | char | char | char |
| short | short | unsigned short | short | short | short |
| int | int | unsigned int | int | int | int |
| long | long | unsigned long | long | long | long |
| decimal | double | double | double | double | double |
| float | float | float | float | float | float |
| double | double | double | double | double | double |
| boolean | bool | bool | bool | bool | bool |
| date | std::tm | std::tm | std::tm | std::tm | std::tm |
| time |  |  |  |  |  |
| timestamp |  |  |  |  |  |
| binary |  |  |  |  |  |

The type conversion has an impact on :

*  $attribute.type
*  $attribute.fullType
*  $attribute.simpleType
*  $attribute.wrapperType
*  $attribute.isPrimitiveType\(\)

## Remarks

'@UnsignedType' has effect only for char, short, int, long

'@NotNull' has no effect  
'@PrimitiveType' has no effect  
'@ObjectType' has no effect  


## Literals for TRUE, FALSE and NULL

|  TRUE | true |
| :--- | :--- |
|  FALSE | false |
|  NULL | NULL |

## Literal values

|  Model type |  Language type |  Language full type |  Language literal value example |
| :--- | :--- | :--- | :--- |
| string | string | string | "AAA" |
| byte | char | char | 1 |
| byte | unsigned char | unsigned char | 1 |
| short | short | short | 1 |
| short | unsigned short | unsigned short | 1 |
| int | int | int | 100 |
| int | unsigned int | unsigned int | 100 |
| long | long | long | 1000 |
| long | unsigned long | unsigned long | 1000 |
| decimal | double | double | 10000.77 |
| float | float | float | 1000.5 |
| double | double | double | 1000.66 |
| boolean | bool | bool | true |
| date | std::tm | std::tm | NULL |
| time |  |  | NULL |
| timestamp |  |  | NULL |
| binary |  |  | NULL |

