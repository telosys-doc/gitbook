# Telosys objects

Telosys provides a set of predefined objects usable in the templates :

* Current model elements :&#x20;
  * **$model**  (current model)
    * **$entity**  (entity defined in the model) \[0:N / model]
      * **$attribute**  (attribute defined in an entity) \[1:N / entity]
        * **$fkPart** (part of foreign key, if attribute is involved in one or more FK)
      * **$link**  (link defined in an entity) \[0:N / entity]
        * **$linkAttribute** (attribute involved in link definition) \[1:N / link]
      * **$fk** (foreign key defined in an entity) \[0:N / entity]
        * **$fkAttribute** (attribute involved in FK definition) \[1:N / fk]
      * **$reference** (reference to other entity) \[0:N / entity]
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
  * **$file** (to use files located on the file system)&#x20;
  * **$loader** (to load your own utility classes)
  * **$now**  (current date and time)
  * **$values** (literal values generator for attributes)
  * **$h2** (utility functions for H2 database)
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
  * _**$jdbcFactory**_  (use **$factory** instead)
  * _**$today**_ (use **$now** instead)

The documentation reference for each object is available here :

* **Latest version** :&#x20;
  * [Telosys 4.0.0 - objects reference](https://www.telosys.org/doc/v400/objects/index.html)
* Previous version :
  * [Telosys 3.3.0 - objects reference](https://www.telosys.org/doc/v330/objects/index.html)



