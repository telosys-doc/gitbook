# Telosys objects

Telosys provides a set of predefined objects usable in the templates :

* Current model elements :&#x20;
  * **$model**  (current model)
    * **$entity**  (entity defined in the model)
      * **$attribute**  (attribute defined in an entity)
        * **$fkPart** (part of foreign key, if attribute is involved in one or more FK)
      * **$link**  (link defined in an entity)
      * **$fk** (foreign key defined in an entity)
* Configuration : &#x20;
  * **$env** (environment configuration)
  * **$project** (project configuration)
* Generation in progress :&#x20;
  * **$target** (current target)
  * **$bundle** (current bundle)
  * **$generator** (generator engine)
* Utility functions and tools :&#x20;
  * **$fn** (set of utility functions)
  * **$const** (set of constants)
  * **$factory** (a factory to create objects)
  * &#x20;
  * **$file** (to use files located on the file system)&#x20;
  * **$loader**&#x20;
* Utility functions for generating Java code :  &#x20;
  * **$java**  &#x20;
  * **$jpa**  &#x20;
  * **$jdbc**  &#x20;
  * **$beanValidation**  &#x20;
* Utility functions for generating SQL code :  &#x20;
  * **$sql**
* Utility functions for generating HTML code :  &#x20;
  * **$html**
* Deprecated objects (do not use, just for backward compatibility) : &#x20;
  * _**$jdbcFactory**_&#x20;
  * _**$today**_

The documentation reference for each object is available here :

* **Latest version** :&#x20;
  * [Telosys 4.0.0 - objects reference](https://www.telosys.org/doc/v400/objects/index.html)
* Previous version :
  * [Telosys 3.3.0 - objects reference](https://www.telosys.org/doc/v330/objects/index.html)



