# C\#

To define **C#** as the **target language** in a template file :

```
#set( $env.language = 'C#' )
```

A "**?**" is automatically added to the end of the type if the attribute is "**nullable**" (no "@NotNull" annotation). To disable this behavior:&#x20;

```
#set( $env.typeWithNullableMark = false )
```

The information below shows the behavior of the generator when C# is the current target language. For a detailed description of type conversion, see the generated documentation :  \
&#x20;[https://www.telosys.org/doc/latest/languages/language-csharp.html](https://www.telosys.org/doc/latest/languages/language-csharp.html) \


## Types conversion&#x20;

The table below describes how model neutral types are automatically converted to C# types with potential impact due to attribute annotations.

| Model type | C# type                                                                                                               | with annotation                                           |
| ---------- | --------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------- |
| string     | <p><strong>string?</strong> <br><strong>string</strong><br><strong>String?</strong></p>                               | <p><br>@NotNull</p><p>@ObjectType</p>                     |
| byte       | <p><strong>sbyte?</strong> <br><strong>sbyte</strong> <br><strong>byte?</strong> <br><strong>SByte?</strong></p>      | <p><br>@NotNull</p><p>@UnsignedType <br>@ObjectType</p>   |
| short      | <p><strong>short?</strong> </p><p><strong>short</strong><br><strong>ushort?</strong> <br><strong>Int16?</strong></p>  | <p><br>@NotNull</p><p>@UnsignedType</p><p>@ObjectType</p> |
| int        | <p><strong>int?</strong> </p><p><strong>int</strong><br><strong>uint?</strong> <br><strong>Int32?</strong></p>        | <p><br>@NotNull</p><p>@UnsignedType</p><p>@ObjectType</p> |
| long       | <p><strong>long?</strong></p><p><strong>long</strong></p><p><strong>ulong?</strong></p><p><strong>Int64?</strong></p> | <p><br>@NotNull</p><p>@UnsignedType</p><p>@ObjectType</p> |
| decimal    | <p><strong>decimal?</strong></p><p><strong>decimal</strong></p><p><strong>Decimal?</strong></p>                       | <p><br>@NotNull</p><p>@ObjectType</p>                     |
| float      | <p><strong>float?</strong></p><p><strong>float</strong><br><strong>Single?</strong></p>                               | <p><br>@NotNull</p><p>@ObjectType</p>                     |
| double     | <p><strong>double?</strong></p><p><strong>double</strong><br><strong>Double?</strong></p>                             | <p><br>@NotNull</p><p>@ObjectType</p>                     |
| boolean    | <p><strong>bool?</strong></p><p><strong>bool</strong><br><strong>Boolean?</strong></p>                                | <p><br>@NotNull</p><p>@ObjectType</p>                     |
| date       | <p><strong>DateOnly?</strong> <br><strong>DateOnly</strong></p>                                                       | <p><br>@NotNull</p>                                       |
| time       | <p><strong>TimeOnly?</strong><br><strong>TimeOnly</strong></p>                                                        | <p><br>@NotNull</p>                                       |
| timestamp  | <p><strong>DateTime?</strong> <br><strong>DateTime</strong></p>                                                       | <p><br>@NotNull</p>                                       |
| binary     | <p><strong>byte[]?</strong><br><strong>byte [ ]</strong></p>                                                          | <p><br>@NotNull</p>                                       |

Remarks:&#x20;

* since ver 4.1.0 "date" is converted to "DateOnly" and "time" is converted to "TimeOnly" &#x20;

### Annotations effects

* **@UnsignedType** \
  has effect only for **byte**, **short**, **int**, **long**
* **@ObjectType** \
  switches to **.Net types** ( System.Int64, System.Boolean, etc)
* **@NotNull** \
  type not nullable => no "?" at the end of the type
* **@PrimitiveType** \
  no effect

### Specific types&#x20;

* &#x20;**$attribute.fullType**\
  returns the C# System class full name for both "primitive type" and "object type"\
  ( for example : System.String, System.Int16, System.Decimal )
* &#x20;**$attribute.simpleType**&#x20;
  * for an "object type" returns the simple type name of the C# System class ( for example : String, Int16, Decimal )
  * for a "standard type" returns the usual type\
    ( for example : string, int, uint, bool )
* &#x20;**$attribute.wrapperType** \
  returns the C# System class associtated with the curren type

## Literal values

### TRUE, FALSE, NULL

|        | C# literal |
| ------ | ---------- |
| TRUE   | **true**   |
|  FALSE | **false**  |
|  NULL  | **null**   |

### Generated literal values

Below some examples of literal values generated for each type :

|  Model type |  C# type                                     |  C# literal value       |
| ----------- | -------------------------------------------- | ----------------------- |
| string      | <p>string</p><p>System.String</p>            | **"AAA"**               |
| byte        | <p>sbyte </p><p>byte</p><p>System.SByte</p>  | **1**                   |
| short       | <p>short<br>ushort<br>System.Int16</p>       | **1**                   |
| int         | <p>int<br>uint<br>System.Int32</p>           | **100**                 |
| long        | <p>long </p><p>ulong </p><p>System.Int64</p> | **1000L**               |
| decimal     | <p>decimal<br>System.Decimal</p>             | **10000.77M**           |
| float       | <p>float <br>System.Single</p>               | **1000.5F**             |
| double      | <p>double<br>System.Double</p>               | **1000.66D**            |
| boolean     | <p>bool<br>System.Boolean</p>                | **true**  or  **false** |
| date        | System.DateOnly                              | **null**                |
| time        | System.TimeOnly                              | **null**                |
| timestamp   | System.DateTime                              | **null**                |
| binary      | byte \[ ]                                    | **null**                |

