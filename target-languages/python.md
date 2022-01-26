# Python

To define **Python** as the **target language** in a template file :

```
#set( $env.language = 'Python' )
```

The information below shows the behavior of the generator when Python is the current target language.\


## Types conversion&#x20;

Python is a dynamically-typed language, there are no types in the source code. \
Therefore, the type conversion always return a void string.
