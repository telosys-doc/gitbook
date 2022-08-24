# New model from scratch

This page describes how to create a new Telosys model from scratch.

### Create a new model

To create a new model use the **`nm`** ("New Model") command

Example :

**`nm cars`** will create the "cars" model

Use the **`lm`** (List Models) command to see all models defined in the current project

When a new model has been created it is set as the "current model"

Example :

```
telosys#(cars.model)>lm
1 model(s) :
 . cars.model
 
telosys#(cars.model)>nm mymodel
Model 'mymodel' created (mymodel.model), current model is now 'mymodel'

telosys#(mymodel.model)>lm
2 model(s) :
 . cars.model
 . mymodel.model
```

### Create an entity in the current model

The **`le`** (List Entities) command can be used to see all the entities of the current model

Obviously, at the beginning there's no entity.

To create an entity use the **`ne`** (New Entity) command

Examples :

**`ne Car`** will create the "Car" entity in the "cars" model

**`ne Driver`** will create the "Driver" entity in the "cars" model

Example :

```
telosys#(cars.model)>le
 . Brand (table 'Brand')
 . Car (table 'Car')
 . Company (table 'Company')
 . Driver (table 'Driver')

telosys#(cars.model)>ne Foo
Entity 'Foo' created.
```

### Edit an entity

To define an entity you must define all its attributes, for that use the **`ee`** (Edit Entity) command.

Example :

**`ee Driver`**   will launch the external editor to edit the "**Driver.entity**" file.

{% hint style="info" %}
Telosys cannot launch an external editor if your Operating System doesn't have a GUI, for example a Linux server without GUI. In this case you will have to edit the ".entity" files outside in a separated console.
{% endhint %}

### Delete an entity&#x20;

To delete an entity in the current model use the "**de**" (Delete Entity) command.

Examples :&#x20;

**`de Driver`**   will delete the "Driver" entity&#x20;

```
telosys#(cars.model)>de Foo
Entity 'Foo' deleted.
```

### Delete a model

To delete a model use the "**dm**" (Delete Model) command.

Example :&#x20;

**`dm cars`**    will delete the "cars" model&#x20;

