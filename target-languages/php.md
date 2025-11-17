# PHP

To define **PHP** as the **target language** in a template file :

```
#set( $env.language = 'PHP' )
```

A "**?**" is automatically added at the beginning of the type if the attribute is "**nullable**" (no "@NotNull" annotation). To disable this behavior:&#x20;

```
#set( $env.typeWithNullableMark = false )
```

The information below shows the behavior of the generator when PHP is the current target language. For a detailed description of type conversion, see the generated documentation : \
&#x20; [https://www.telosys.org/doc/latest/languages/language-php.html](https://www.telosys.org/doc/latest/languages/language-php.html)&#x20;

## Types conversion&#x20;

\
Typed class properties were added in PHP 7.4  ( [https://php.watch/versions/7.4/typed-properties](https://php.watch/versions/7.4/typed-properties) )

So since Telosys version 4.1.0, type conversion was added for the PHP language.

| Model type    | PHP property type                                               | with annotation         |
| ------------- | --------------------------------------------------------------- | ----------------------- |
| string        | <p><strong>?string</strong> </p><p><strong>string</strong></p>  | <p></p><p>@NotNull</p>  |
| byte          | <p><strong>?int</strong> <br><strong>int</strong></p>           | <p></p><p>@NotNull</p>  |
| short         | <p><strong>?int</strong> <br><strong>int</strong></p>           | <p><br>@NotNull</p>     |
| int           | <p><strong>?int</strong> <br><strong>int</strong></p>           | <p><br>@NotNull</p>     |
| long          | <p><strong>?int</strong> <br><strong>int</strong></p>           | <p></p><p>@NotNull</p>  |
| decimal       | <p><strong>?float</strong> <br><strong>float</strong></p>       | <p></p><p>@NotNull</p>  |
| float         | <p><strong>?float</strong> <br><strong>float</strong></p>       | <p></p><p>@NotNull</p>  |
| double        | <p><strong>?float</strong> <br><strong>float</strong></p>       | <p></p><p>@NotNull</p>  |
| boolean       | <p><strong>?bool</strong> <br><strong>bool</strong></p>         | <p></p><p>@NotNull</p>  |
| date          | <p><strong>?DateTime</strong> <br><strong>DateTime</strong></p> | <p><br>@NotNull</p>     |
| time          | <p><strong>?DateTime</strong> <br><strong>DateTime</strong></p> | <p><br>@NotNull</p>     |
| timetz        | <p><strong>?DateTime</strong> <br><strong>DateTime</strong></p> | <p><br>@NotNull</p>     |
| datetime      | <p><strong>?DateTime</strong> <br><strong>DateTime</strong></p> | <p><br>@NotNull</p>     |
| datetimetz    | <p><strong>?DateTime</strong> <br><strong>DateTime</strong></p> | <p><br>@NotNull</p>     |
| ~~timestamp~~ | <p><strong>?DateTime</strong> <br><strong>DateTime</strong></p> | <p><br>@NotNull</p>     |
| uuid          | <p><strong>?string</strong> </p><p><strong>string</strong></p>  | <p><br>@NotNull</p>     |
| binary        | <p><strong>?string</strong> </p><p><strong>string</strong></p>  | <p><br>@NotNull<br></p> |



## Literal values

#### TRUE, FALSE, NULL

|        | PHP  literal |
| ------ | ------------ |
| TRUE   | **true**     |
|  FALSE | **false**    |
|  NULL  | **null**     |
