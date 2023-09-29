# Scala

**Scala** is supported since **version 3.3.0**

To define **Scala** as the **target language** in a template file :

```
#set( $env.language = 'Scala' )
```

The information below shows the behavior of the generator when Scala is the current target language.

For a detailed description of type conversion and literal values see the generated documentation: \
[https://www.telosys.org/doc/latest/languages/language-scala.html](https://www.telosys.org/doc/latest/languages/language-scala.html)

## Types conversion&#x20;

The table below describes how model neutral types are automatically converted to Scala types with potential impact due to attribute annotations.

| Model type | Scala type        |   |
| ---------- | ----------------- | - |
| string     | **String**        |   |
| byte       | **Byte**          |   |
| short      | **Short**         |   |
| int        | **Int**           |   |
| long       | **Long**          |   |
| decimal    | **BigDecimal**    |   |
| float      | **Float**         |   |
| double     | **Double**        |   |
| boolean    | **Boolean**       |   |
| date       | **LocalDate**     |   |
| time       | **LocalTime**     |   |
| timestamp  | **LocalDateTime** |   |
| binary     | **Array\[Byte]**  |   |

### Annotations effects

* **@UnsignedType** : no effect
* **@ObjectType** : no effect
* **@NotNull** : no effect
* **@PrimitiveType**  : no effect
