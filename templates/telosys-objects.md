# Telosys objects

## Objects by categories

Telosys provides a set of predefined objects usable in the templates :

* Objects representing the model elements :&#x20;
  * [**$model**](https://www.telosys.org/doc/latest/objects/model.html)  (current model)
    * [**$entity**](https://www.telosys.org/doc/latest/objects/entity.html)  (entity defined in the model) \[0:N entities in each model]
      * [**$attribute**](https://www.telosys.org/doc/latest/objects/attribute.html)  (attribute defined in an entity) \[1:N attributes in each entity]
        * [**$fkPart** ](https://www.telosys.org/doc/latest/objects/fkPart.html) (part of foreign key, if attribute is involved in one or more FK)
      * [**$link**](https://www.telosys.org/doc/latest/objects/link.html)  (link defined in an entity) \[0:N links in each entity]
        * [**$linkAttribute** ](https://www.telosys.org/doc/latest/objects/linkAttribute.html) (attribute involved in link definition) \[1:N / link]
      * [**$fk** ](https://www.telosys.org/doc/latest/objects/fk.html)(foreign key defined in an entity) \[0:N FK in each entity]
        * [**$fkAttribute** ](https://www.telosys.org/doc/latest/objects/fkAttribute.html) (attribute involved in FK definition) \[1:N / fk]
      * [**$reference**](https://www.telosys.org/doc/latest/objects/reference.html)  (reference to other entity)  \[0:N references in each entity]
* Current environment and project : &#x20;
  * [**$env**](https://www.telosys.org/doc/latest/objects/env.html)  (environment configuration)
  * [**$project** ](https://www.telosys.org/doc/latest/objects/project.html) (project configuration)
* Generation in progress :&#x20;
  * [**$target** ](https://www.telosys.org/doc/latest/objects/target.html)  (current target file being generated)
  * [**$bundle**](https://www.telosys.org/doc/latest/objects/bundle.html) (bundle in use for current generation)
  * [**$generator**](https://www.telosys.org/doc/latest/objects/generator.html) (generator engine)
* Utility functions and tools :&#x20;
  * [**$fn**  ](https://www.telosys.org/doc/latest/objects/fn.html) (set of utility functions)
  * [**$const** ](https://www.telosys.org/doc/latest/objects/const.html) (set of constants)
  * [**$factory**](https://www.telosys.org/doc/latest/objects/factory.html) (a factory to create objects)
  * [**$file** ](https://www.telosys.org/doc/latest/objects/file.html) (to use files located on the file system)&#x20;
  * [**$loader** ](https://www.telosys.org/doc/latest/objects/loader.html) (to load your own utility classes)
  * **$now**  (current date and time)
  * **$values** (literal values generator for attributes)
  * **$h2** (utility functions for H2 database)
* Objects dedicated to code generation of certain target languages :  &#x20;
  * Java :  **$java**   **$jpa**   **$jdbc**   **$beanValidation**  &#x20;
  * SQL :  **$sql** &#x20;
  * C#  :  **$csharp**&#x20;
  * PHP :  **$php** &#x20;
  * HTML :  **$html** &#x20;
* Deprecated objects (do not use, just for backward compatibility) : &#x20;
  * ~~**$jdbcFactory**~~  (use **$factory** instead)
  * ~~**$today**~~ (use **$now** instead)

## Objects reference documentation

The documentation reference for each object is available here :

* **Latest version** :&#x20;
  * [Telosys 4.1.0 - objects reference](https://www.telosys.org/doc/v410/objects/index.html)
* Previous version :&#x20;
  * [Telosys 4.0.0 - objects reference](https://www.telosys.org/doc/v400/objects/index.html)
  * [Telosys 3.3.0 - objects reference](https://www.telosys.org/doc/v330/objects/index.html)







