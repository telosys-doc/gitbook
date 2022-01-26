# C++

**C++** language is supported since **version 3.3.0**

To define **C++** as the **target language** in a template file :

```
#set( $env.language = 'C++' )
```

The information below shows the behavior of the generator when C++ is the current target language.\


## Types conversion&#x20;

The table below describes how model neutral types are automatically converted to C++ types with potential impact due to annotations (@UnsignedType, @NotNull, @PrimitiveType, @ObjectType)

| Model type | C++ type                                                            | with annotation             |
| ---------- | ------------------------------------------------------------------- | --------------------------- |
| string     | **string**                                                          |                             |
| byte       | <p><strong>char</strong></p><p><strong>unsigned char</strong></p>   | <p></p><p>@UnsignedType</p> |
| short      | <p><strong>short</strong></p><p><strong>unsigned short</strong></p> | <p></p><p>@UnsignedType</p> |
| int        | <p><strong>int</strong></p><p><strong>unsigned int</strong></p>     | <p></p><p>@UnsignedType</p> |
| long       | <p><strong>long</strong></p><p><strong>unsigned long</strong></p>   | <p></p><p>@UnsignedType</p> |
| decimal    | **double**                                                          |                             |
| float      | **float**                                                           |                             |
| double     | **double**                                                          |                             |
| boolean    | **bool**                                                            |                             |
| date       | **std::tm**                                                         |                             |
| time       |                                                                     |                             |
| timestamp  |                                                                     |                             |
| binary     |                                                                     |                             |

### Annotations effects

* **@UnsignedType** \
  ****has effect only for **char**, **short**, **int**, **long**
* **@NotNull** \
  ****has no effect
* **@PrimitiveType**\
  ****no effect
* **@ObjectType** \
  ****no effect

### Specific types&#x20;

* &#x20;**$attribute.fullType**\
  no effect
* &#x20;**$attribute.simpleType** \
  no effect
* &#x20;**$attribute.wrapperType** \
  no effect

So, for **C++** you can always use the basic "**$attribute.type**"\


## Literal values

### TRUE, FALSE, NULL

|        | C++ literal |
| ------ | ----------- |
| TRUE   | **true**    |
|  FALSE | **false**   |
|  NULL  | **NULL**    |

### Generated literal values

Below some examples of literal values generated for each type :

|  Model type |  C++ type                         |  C++ literal value      |
| ----------- | --------------------------------- | ----------------------- |
| string      | string                            | **"AAA"**               |
| byte        | <p>char</p><p>unsigned char</p>   | **1**                   |
| short       | <p>short</p><p>unsigned short</p> | **1**                   |
| int         | <p>int</p><p>unsigned int</p>     | **100**                 |
| long        | <p>long</p><p>unsigned long</p>   | **1000**                |
| decimal     | double                            | **10000.77**            |
| float       | float                             | **1000.5**              |
| double      | double                            | **1000.66**             |
| boolean     | bool                              | **true**  or  **false** |
| date        | std::tm                           | **NULL**                |
| time        |                                   | **NULL**                |
| timestamp   |                                   | **NULL**                |
| binary      |                                   | **NULL**                |
