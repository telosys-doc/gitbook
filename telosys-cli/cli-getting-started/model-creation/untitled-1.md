# New model from scratch

This page describes how to create a new Telosys model from scratch.

### Create a DSL Model

To create a DSL Model use the **`nm`** ("New Model") command

Example :

**`nm cars`** will create the "cars" DSL model

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

{% hint style="info" %}
You can also **reuse an existing DSL model** (instead of creating a new one from scratch). For that you can download a basic DSL model from here : [http://www.telosys.org/download/models-v3/](http://www.telosys.org/download/models-v3/) \
After download just unzip the file in the "TelosysTools" folder.
{% endhint %}

### Create an ENTITY in the current model

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

### Edit an ENTITY

To define an entity you must define all its attributes, for that use the **`ee`** (Edit Entity) command.

Example :

**`ee Driver`** will launch the external editor to edit the "**Driver.entity**" file.

{% hint style="info" %}
Telosys cannot launch an external editor if your Operating System doesn't have a GUI, for example a Linux server without GUI. In this case you will have to edit the ".entity" files outside in a separated console.
{% endhint %}

### Delete an entity or a model

**`de Driver`** will delete the "Driver" entity

**`dm cars`** will delete the "cars" model

Example :

```
telosys#(cars.model)>de Foo
Entity 'Foo' deleted.
```
