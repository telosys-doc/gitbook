# Python

To define **Python** as the **target language** in a template file :

```
#set( $env.language = 'Python' )
```

The information below shows the behavior of the generator when Python is the current target language.\


For a detailed description of type conversion and literal values see the generated documentation : \
[https://www.telosys.org/doc/latest/languages/language-python.html](https://www.telosys.org/doc/latest/languages/language-python.html)

## Types conversion&#x20;

Python is a dynamically-typed language, there are no types in the source code. \
Therefore, the type conversion always return a void string.
