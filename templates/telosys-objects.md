# Telosys objects

## Objects by categories

Telosys provides a set of predefined objects usable in the templates :

* Objects representing the model elements :&#x20;
  * [**$model**](https://www.telosys.org/doc/latest/objects/model.html)  (current model)
    * [**$entity**](https://www.telosys.org/doc/latest/objects/entity.html)  (entity defined in the model) \[0:N entities in each model]
      * [**$attribute**](https://www.telosys.org/doc/latest/objects/attribute.html)  (attribute defined in an entity) \[1:N attributes in each entity]
        * **$fkPart** (part of foreign key, if attribute is involved in one or more FK)
      * [**$link**](https://www.telosys.org/doc/latest/objects/link.html)  (link defined in an entity) \[0:N links in each entity]
        * **$linkAttribute** (attribute involved in link definition) \[1:N / link]
      * [**$fk** ](https://www.telosys.org/doc/latest/objects/fk.html)(foreign key defined in an entity) \[0:N FK in each entity]
        * **$fkAttribute** (attribute involved in FK definition) \[1:N / fk]
      * &#x20; **$reference**  (reference to other entity) \[0:N / entity]
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



