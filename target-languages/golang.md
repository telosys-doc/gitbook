# Golang

To define **Golang** as the **target language** in a template file :

```
#set( $env.language = 'Go' )
```

The information below shows the behavior of the generator when Golang is the current target language. For a detailed description of type conversion, see the generated documentation :  \
&#x20;[https://www.telosys.org/doc/latest/languages/language-go.html](https://www.telosys.org/doc/latest/languages/language-go.html)

## Types conversion&#x20;

The table below describes how model neutral types are automatically converted to Golang types with potential impact due to attribute annotations.

| Model type    | Go type                                                   | with annotation              |
| ------------- | --------------------------------------------------------- | ---------------------------- |
| string        | **string**                                                |                              |
| byte          | <p><strong>byte</strong> <br><strong>uint8</strong></p>   | <p></p><p>@UnsignedType </p> |
| short         | <p><strong>int16</strong> <br><strong>uint16</strong></p> | <p></p><p>@UnsignedType</p>  |
| int           | <p><strong>int32</strong> <br><strong>uint32</strong></p> | <p></p><p>@UnsignedType</p>  |
| long          | <p><strong>int64</strong><br><strong>uint64</strong></p>  | <p></p><p>@UnsignedType</p>  |
| decimal       | **float64**                                               |                              |
| float         | **float32**                                               |                              |
| double        | **float64**                                               |                              |
| boolean       | **bool**                                                  |                              |
| date          | **time.Time**                                             |                              |
| time          | **time.Time**                                             |                              |
| timetz        | **time.Time**                                             |                              |
| datetime      | **time.Time**                                             |                              |
| datetimetz    | **time.Time**                                             |                              |
| ~~timestamp~~ | **time.Time**                                             |                              |
| uuid          | **uuid.UUID**                                             |                              |
| binary        | **\[ ] byte**                                             |                              |

### Annotations effects

* **@UnsignedType** \
  has effect only for **byte**, **short**, **int**, **long**
* **@ObjectType** \
  no effect
* **@NotNull** \
  no effect
* **@PrimitiveType** \
  no effect

### Specific types&#x20;

* &#x20;**$attribute.fullType**\
  no effect (always returns the standard Go type)
*   &#x20;**$attribute.simpleType**&#x20;

    no effect (always returns the standard Go type)
* &#x20;**$attribute.wrapperType** \
  no effect (always returns the standard Go type)

So, for **Golang** you can always use the basic "**$attribute.type**"

### See also

For more information about Golang types see :

* [https://golang.org/ref/spec#Types](https://golang.org/ref/spec#Types)

## Literal values

#### TRUE, FALSE, NULL

|        | Golang literal |
| ------ | -------------- |
| TRUE   | **true**       |
|  FALSE | **false**      |
|  NULL  | **nil**        |

### Generated literal values

Below some examples of literal values generated for each type :

|  Model type |  Golang  type           |  Golang literal value   |
| ----------- | ----------------------- | ----------------------- |
| string      | string                  | **"AAA"**               |
| byte        | <p>byte</p><p>uint8</p> | **1**                   |
| short       | <p>int16 <br>uint16</p> | **1**                   |
| int         | <p>int32 <br>uint32</p> | **100**                 |
| long        | <p>int64<br>uint64</p>  | **1000**                |
| decimal     | float64                 | **10000.77**            |
| float       | float32                 | **1000.5**              |
| double      | float64                 | **1000.66**             |
| boolean     | bool                    | **true**  or  **false** |
| date        | time.Time               | **nil**                 |
| time        | time.Time               | **nil**                 |
| timestamp   | time.Time               | **nil**                 |
| binary      | \[ ] byte               | **nil**                 |

