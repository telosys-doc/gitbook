# Java

**Java** is the target language **by default**, so you don't have to define it explicitly.&#x20;

However, you can define it with the following instruction :

```
#set( $env.language = 'Java' )
```



The information below shows the behavior of the generator when Java is the current target language. For a detailed description of type conversion, see the generated documentation :   \
[https://www.telosys.org/doc/latest/languages/language-java.html](https://www.telosys.org/doc/latest/languages/language-java.html) \


## Types conversion&#x20;

The table below describes how model neutral types are automatically converted to Java types with potential impact due to attribute annotations.

| Model type    | Java type                                                                                     | with annotation                          |
| ------------- | --------------------------------------------------------------------------------------------- | ---------------------------------------- |
| string        | **String**                                                                                    |                                          |
| byte          | <p><strong>Byte</strong><br><strong>byte</strong><br><strong>byte</strong></p>                | <p></p><p>@NotNull<br>@PrimitiveType</p> |
| short         | <p><strong>Short</strong></p><p><strong>short</strong></p><p><strong>short</strong></p>       | <p></p><p>@NotNull<br>@PrimitiveType</p> |
| int           | <p><strong>Integer</strong><br><strong>int</strong></p><p><strong>int</strong></p>            | <p></p><p>@NotNull<br>@PrimitiveType</p> |
| long          | <p><strong>Long</strong></p><p><strong>long</strong></p><p><strong>long</strong></p>          | <p></p><p>@NotNull<br>@PrimitiveType</p> |
| decimal       | **BigDecimal**                                                                                | <p></p><p></p>                           |
| float         | <p><strong>Float</strong></p><p><strong>float</strong></p><p><strong>float</strong></p>       | <p></p><p>@NotNull<br>@PrimitiveType</p> |
| double        | <p><strong>Double</strong></p><p><strong>double</strong></p><p><strong>double</strong></p>    | <p></p><p>@NotNull<br>@PrimitiveType</p> |
| boolean       | <p><strong>Boolean</strong></p><p><strong>boolean</strong></p><p><strong>boolean</strong></p> | <p></p><p>@NotNull<br>@PrimitiveType</p> |
| date          | **LocalDate**                                                                                 |                                          |
| time          | **LocalTime**                                                                                 |                                          |
| timetz        | **OffsetTime**                                                                                |                                          |
| datetime      | **LocalDateTime**                                                                             |                                          |
| datetimetz    | **OffsetDateTime**                                                                            |                                          |
| ~~timestamp~~ | **LocalDateTime**                                                                             |                                          |
| uuid          | **UUID**                                                                                      |                                          |
| binary        | **byte \[ ]**                                                                                 |                                          |

### Annotations effects

* **@UnsignedType** \
  no effect (all numeric types are signed in Java)
* **@ObjectType** \
  switches to the standard wrapper type for the current type \
  (Byte, Short, Integer, Long, Float, Double, Boolean)
* **@PrimitiveType** \
  switches to the primitive type if possible\
  (byte, short, int, long, float, double, boolean)
* **@NotNull** \
  switches to primitive type if possible in order to avoid 'null' value



### Specific types&#x20;

* &#x20;**$attribute.fullType**
  * for an "object type" returns the fully-qualified class name \
    (java.lang.String,  java.lang.Integer,  java.math.BigDecimal, etc )
  *   for a "primitive type" returns the primitive type as is&#x20;

      ( int,  double,  etc )
* &#x20;**$attribute.simpleType**&#x20;
  * for an "object type" returns the simple class name\
    ( String,  Integer,  Double, etc )
  *   for a "primitive type" returns the primitive type as is

      ( int,  double,  etc )
* &#x20;**$attribute.wrapperType** \
  returns the Java wrapper type class associtated with the current type (Integer, Double, etc )
