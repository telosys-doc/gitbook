# Kotlin

To define **Kotlin** as the **target language** in a template file :

```
#set( $env.language = 'Kotlin' )
```

The information below shows the behavior of the generator when Kotlin is the current target language.

## Types conversion&#x20;

The table below describes how model **neutral types** are automatically converted to **Kotlin types** with potential impact due to attribute annotations.



The table below describes how model neutral types are automatically converted to C# types with potential impact due to attribute annotations.

| Model type | C# type                                                                                | with annotation                               |
| ---------- | -------------------------------------------------------------------------------------- | --------------------------------------------- |
| string     | <p><strong>String?</strong><br><strong>String</strong></p>                             | <p></p><p>@NotNull</p>                        |
| byte       | <p><strong>Byte?</strong><br><strong>UByte?</strong><br><strong>Byte</strong></p>      | <p></p><p>@UnsignedType <br>@NotNull</p>      |
| short      | <p>Short?<br>UShort?<br>Short</p>                                                      | <p></p><p>@UnsignedType <br>@NotNull</p>      |
| int        | <p>Int? <br>UInt? <br>Int</p>                                                          | <p></p><p>@UnsignedType <br>@NotNull</p>      |
| long       | <p><strong>long</strong></p><p><strong>ulong</strong></p><p><strong>Int64</strong></p> | <p></p><p>@UnsignedType</p><p>@ObjectType</p> |
| decimal    | <p><strong>decimal</strong></p><p><strong>Decimal</strong></p>                         | <p></p><p>@ObjectType</p>                     |
| float      | <p><strong>float</strong><br><strong>Single</strong></p>                               | <p></p><p>@ObjectType</p>                     |
| double     | <p><strong>double</strong><br><strong>Double</strong></p>                              | <p></p><p>@ObjectType</p>                     |
| boolean    | <p><strong>bool</strong><br><strong>Boolean</strong></p>                               | <p></p><p>@ObjectType</p>                     |
| date       | **DateTime**                                                                           |                                               |
| time       | **DateTime**                                                                           |                                               |
| timestamp  | **DateTime**                                                                           |                                               |
| binary     | **byte \[ ]**                                                                          |                                               |

### Annotations effects



| string    | <p>String?<br>String</p>                          | <p><br>@NotNull</p>         |
| --------- | ------------------------------------------------- | --------------------------- |
| byte      | <p><strong>xx</strong><br><strong>xx</strong></p> | <p></p><p></p>              |
| short     | <p><strong>xx</strong><br><strong>xx</strong></p> | <p></p><p></p>              |
| int       | <p><strong>xx</strong><br><strong>xx</strong></p> | <p></p><p></p>              |
| long      | <p><strong>x</strong><br><strong>x</strong></p>   | <p></p><p>@UnsignedType</p> |
| decimal   | **x**                                             |                             |
| float     | **x**                                             |                             |
| double    | **x**                                             |                             |
| boolean   | **x**                                             |                             |
| date      | **xx**                                            |                             |
| time      | **xx**                                            |                             |
| timestamp | **x**                                             |                             |
| binary    | **x**                                             |                             |

### Annotations effects

