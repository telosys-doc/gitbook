# TypeScript

To define **TypeScript** as the **target language** in a template file :

```
#set( $env.language = 'TypeScript' )
```

The information below shows the behavior of the generator when TypeScript is the current target language.

For a detailed description of type conversion and literal values see the generated documentation:[](https://www.telosys.org/doc/latest/languages/language-scala.html)\
[https://www.telosys.org/doc/latest/languages/language-typescript.html](https://www.telosys.org/doc/latest/languages/language-typescript.html)

## Types conversion&#x20;

The table below describes how **model neutral types** are automatically converted to **TypeScript types**

| Model type    | TypeScript type |   |
| ------------- | --------------- | - |
| string        | **string**      |   |
| byte          | **number**      |   |
| short         | **number**      |   |
| int           | **number**      |   |
| long          | **number**      |   |
| decimal       | **number**      |   |
| float         | **number**      |   |
| double        | **number**      |   |
| boolean       | **boolean**     |   |
| date          | **Date**        |   |
| time          | **Date**        |   |
| timetz        | **Date**        |   |
| datetime      | **Date**        |   |
| datetimetz    | **Date**        |   |
| ~~timestamp~~ | **Date**        |   |
| uuid          | **string**      |   |
| binary        | **Uint8Array**  |   |

### Annotations effects

* **@UnsignedType** : no effect
* **@ObjectType** : no effect
* **@NotNull** : no effect
* **@PrimitiveType**  : no effect

### See also

For more information about TypeScript see :

* [https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#object-types](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#object-types)

## Literal values

#### TRUE, FALSE, NULL

|        | TypeScript  literal |
| ------ | ------------------- |
| TRUE   | **true**            |
|  FALSE | **false**           |
|  NULL  | **null**            |
