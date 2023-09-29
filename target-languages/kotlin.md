# Kotlin

Kotlin is a predefined target language since Telosys **version 4.1.0**

To define **Kotlin** as the **target language** in a template file :

```
#set( $env.language = 'Kotlin' )
```

A "**?**" is automatically added to the end of the type if the attribute is "**nullable**" (no "@NotNull" annotation). To disable this behavior:&#x20;

```
#set( $env.typeWithNullableMark = false )
```

The information below shows the behavior of the generator when Kotlin is the current target language. For a detailed description of type conversion, see the generated documentation : \
[https://www.telosys.org/doc/latest/languages/language-kotlin.html](https://www.telosys.org/doc/latest/languages/language-kotlin.html)&#x20;

## Types conversion&#x20;

The table below describes how model **neutral types** are automatically converted to **Kotlin types** with potential impact due to attribute annotations.



The table below describes how model neutral types are automatically converted to C# types with potential impact due to attribute annotations.

| Model type | C# type                                                                              | with annotation                            |
| ---------- | ------------------------------------------------------------------------------------ | ------------------------------------------ |
| string     | <p><strong>String?</strong><br><strong>String</strong></p>                           | <p></p><p>@NotNull</p>                     |
| byte       | <p><strong>Byte?</strong><br><strong>UByte?</strong><br><strong>Byte</strong></p>    | <p></p><p>@UnsignedType <br>@NotNull</p>   |
| short      | <p><strong>Short?</strong><br><strong>UShort?</strong><br><strong>Short</strong></p> | <p></p><p>@UnsignedType <br>@NotNull</p>   |
| int        | <p><strong>Int?</strong> <br><strong>UInt?</strong> <br><strong>Int</strong></p>     | <p></p><p>@UnsignedType <br>@NotNull</p>   |
| long       | <p><strong>Long?</strong> <br><strong>ULong?</strong> <br><strong>Long</strong></p>  | <p></p><p>@UnsignedType</p><p>@NotNull</p> |
| decimal    | <p><strong>BigDecimal?</strong> <br><strong>BigDecimal</strong></p>                  | <p></p><p>@NotNull</p>                     |
| float      | <p><strong>Float?</strong> <br><strong>Float</strong></p>                            | <p></p><p>@NotNull</p>                     |
| double     | <p><strong>Double?</strong> <br><strong>Double</strong></p>                          | <p></p><p>@NotNull</p>                     |
| boolean    | <p><strong>Boolean?</strong> <br><strong>Boolean</strong></p>                        | <p></p><p>@NotNull</p>                     |
| date       | <p><strong>LocalDate?</strong> </p><p><strong>LocalDate</strong></p>                 | <p><br>@NotNull</p>                        |
| time       | <p><strong>LocalTime?</strong> </p><p><strong>LocalTime</strong></p>                 | <p><br>@NotNull</p>                        |
| timestamp  | <p><strong>LocalDateTime?</strong><br><strong>LocalDateTime</strong></p>             | <p><br>@NotNull</p>                        |
| binary     | <p><strong>ByteArray?</strong> <br><strong>ByteArray</strong></p>                    | <p><br>@NotNull</p>                        |



### Annotations effects

* **@UnsignedType** \
  has effect only for **byte**, **short**, **int**, **long**
* **@ObjectType** \
  no effect
* **@NotNull** \
  type not nullable => no "?" at the end of the type
* **@PrimitiveType** \
  no effect



