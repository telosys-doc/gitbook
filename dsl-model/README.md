# Model (DSL model)

A "Telosys model" is a model based on a set of text files written with the Telosys "Domain Specific Language". The Telosys DSL uses a very simple grammar to define entities with their attributes and relationships.&#x20;

To create a model see : [Model creation](../telosys-cli/cli-getting-started/model-creation/)

Since Telosys version 4.0 there is only one type of model: the DSL model.

**In version 4.0, the DSL model has evolved in terms of structure and syntax.**

The model parser has been completely rewritten, it has more consistency and syntax checks.&#x20;

For example, the unnecessary comma between annotations is now prohibited and each annotation has a specific scope defining where it can be used or not (level : entity, attribute or link).&#x20;

In short, the parser is now stricter and some entities may need to be modified to comply with the new rules.

### Model structure since version 4.0

Since version 4.0 each model is a directory located in "TelosysTools/models".

Directory name is model name.

A model directory contains&#x20;

* a file "model.yaml"&#x20;
* n files ".entity" (1 for each entity)

Example : model "employees"&#x20;

```
employees (folder)
employees/model.yaml (model file)
employees/Employee.entity (entity file)
employees/Company.entity (entity file)
employees/Project.entity (entity file) 
```



### Model structure before version 4.0  (deprecated)

A model is composed of a ".model" file and a folder that contains all the entities (e.g. for a model named "foo" : "foo.model" file and "foo\_model" folder).

Each entity is defined in a text file having the ".entity" extension (e.g. "Car" is defined in "Car.entity").&#x20;

Example : model "employees"&#x20;

```
employees.model (file)
employees_model (folder)
employees_model / Employee.entity (file)
employees_model / Company.entity (file)
employees_model / Project.entity (file) 
```



### Model elements

Below the main elements of a DSL model:

* [Entity](entity.md)
* [Attribute](fields.md)
* [Annotations](annotations.md)
* [Tags](tags.md)
