# Python

To define **Python** as the **target language** in a template file :

```
#set( $env.language = 'Python' )
```

The information below shows the behavior of the generator when Python is the current target language.\


For a detailed description of type conversion and literal values see the generated documentation : \
[https://www.telosys.org/doc/latest/languages/language-python.html](https://www.telosys.org/doc/latest/languages/language-python.html)

## Types conversion&#x20;

Python is a dynamically-typed language, so there are no real types in the source code. \
But "**type hints**" were introduced in PEP 484 to make Python code easier to understand, maintain, and analyze. Telosys offers an automatic conversion of the model's neutral types into Python type hints.

The table below describes how model neutral types are automatically converted to Python type hints.

Conversion to Python type hints is supported since Telosys 4.3.0

| Model type  | Python type hint |
| ----------- | ---------------- |
| string      | **str**          |
| byte        | **int**          |
| short       | **int**          |
| int         | **int**          |
| long        | **int**          |
| decimal     | **Decimal**      |
| float       | **float**        |
| double      | **float**        |
| boolean     | **bool**         |
| date        | **date**         |
| time        | **time**         |
| timetz      | **time**         |
| datetime    | **datetime**     |
| _timestamp_ | **datetime**     |
| datetimetz  | **datetime**     |
| uuid        | **UUID**         |
| binary      | **bytes**        |

### Annotations effects

* **@UnsignedType** : no effect
* **@ObjectType** : no effect
* **@NotNull** : no effect
* **@PrimitiveType**  : no effect

## Literal values

#### TRUE, FALSE, NULL

|        | Python literal |
| ------ | -------------- |
| TRUE   | **True**       |
|  FALSE | **False**      |
|  NULL  | **none**       |
