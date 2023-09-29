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

PHP is a dynamically-typed language, there are no types in the source code. \
Therefore, the type conversion always return a void string.
