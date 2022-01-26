# PHP

To define **PHP** as the **target language** in a template file :

```
#set( $env.language = 'PHP' )
```

The information below shows the behavior of the generator when PHP is the current target language.\


## Types conversion&#x20;

PHP is a dynamically-typed language, there are no types in the source code. \
Therefore, the type conversion always return a void string.
