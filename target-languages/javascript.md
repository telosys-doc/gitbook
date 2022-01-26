# JavaScript

To define **JavaScript** as the **target language** in a template file :

```
#set( $env.language = 'JavaScript' )
```

The information below shows the behavior of the generator when JavaScript is the current target language.\


## Types conversion&#x20;

JavaScript is a dynamically-typed language, there are no types in the source code. \
Therefore, the type conversion always return a void string.
