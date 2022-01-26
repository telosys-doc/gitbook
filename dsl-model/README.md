# DSL model

A "DSL model" is a model based on a set of text files written in the Telosys "Domain Specific Language". The Telosys DSL uses a very simple grammar to define entities with their attributes and relationships.&#x20;

This type of model is the simplest way to define a model from scratch.

A DSL model is composed of a ".model" file and a folder that contains all the entities (e.g. for a model named "foo" : "foo.model" file and "foo\_model" folder).

Each entity is defined in a text file having the ".entity" extension (e.g. "Car" is defined in "Car.entity").&#x20;

Example : model "employees"&#x20;

```
employees.model (file)
employees_model (folder)
employees_model / Employee.entity (file)
employees_model / Company.entity (file)
employees_model / Project.entity (file) 
```

Below the main elements of a DSL model:

* [Entity](entity.md)
* [Attribute](attribute.md)
* [Annotations](attribute-annotations.md)
* [Tags](tags.md)
