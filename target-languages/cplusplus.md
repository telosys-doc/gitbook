# C++

**C++** language is supported since **version 3.3.0**

To define **C++** as the **target language** in a template file :

```
#set( $env.language = 'C++' )
```

\
The information below shows the behavior of the generator when C++ is the current target language. For a detailed description of type conversion, see the generated documentation :\
[https://www.telosys.org/doc/latest/languages/language-c++.html](https://www.telosys.org/doc/latest/languages/language-c++.html)&#x20;

## Types conversion&#x20;

The table below describes how model neutral types are automatically converted to C++ types with potential impact due to annotations (@UnsignedType, @NotNull, @PrimitiveType, @ObjectType)

<table><thead><tr><th width="182.39996337890625">Model type</th><th width="262.9292399088542">C++ type</th><th>with annotation</th></tr></thead><tbody><tr><td>string</td><td><strong>std::string</strong></td><td></td></tr><tr><td>byte</td><td><p><strong>char</strong></p><p><strong>unsigned char</strong></p></td><td><p></p><p>@UnsignedType</p></td></tr><tr><td>short</td><td><p><strong>short</strong></p><p><strong>unsigned short</strong></p></td><td><p></p><p>@UnsignedType</p></td></tr><tr><td>int</td><td><p><strong>int</strong></p><p><strong>unsigned int</strong></p></td><td><p></p><p>@UnsignedType</p></td></tr><tr><td>long</td><td><p><strong>long</strong></p><p><strong>unsigned long</strong></p></td><td><p></p><p>@UnsignedType</p></td></tr><tr><td>decimal</td><td><strong>double</strong></td><td></td></tr><tr><td>float</td><td><strong>float</strong></td><td></td></tr><tr><td>double</td><td><strong>double</strong></td><td></td></tr><tr><td>boolean</td><td><strong>bool</strong></td><td></td></tr><tr><td>date</td><td><strong>std::chrono::year_month_day</strong></td><td></td></tr><tr><td>time</td><td><strong>std::chrono::hh_mm_ss</strong></td><td></td></tr><tr><td>timetz</td><td><strong>std::chrono::hh_mm_ss</strong></td><td></td></tr><tr><td>datetime</td><td><strong>std::chrono::local_time</strong></td><td></td></tr><tr><td>datetimetz</td><td><strong>std::chrono::zoned_time</strong></td><td></td></tr><tr><td><em>timestamp</em></td><td><strong>std::chrono::local_time</strong></td><td></td></tr><tr><td>uuid</td><td><strong>std::string</strong></td><td></td></tr><tr><td>binary</td><td><strong>std::vector</strong></td><td></td></tr></tbody></table>

### Annotations effects

* **@UnsignedType** \
  has effect only for **char**, **short**, **int**, **long**
* **@NotNull** \
  has no effect
* **@PrimitiveType**\
  no effect
* **@ObjectType** \
  no effect

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
