# Models management

### Current model

The current model is printed between "(...)" in the CLI prompt.

Example with "**cars**" as the current model:  **`telosys#(cars)>`**

Use "**`m`**" command to set/unset the current model :&#x20;

* `>m cars`  -> set "cars" as current model&#x20;
* `>m -none`  -> no current model&#x20;

All entities commands ( "le", "ne", ..) apply to the current model.

### Main commands for models management&#x20;

**Model commands:**&#x20;

* "**`m`**" Model : Set/print the current model&#x20;
* "**`lm`**" List Models : List the project models&#x20;
* "**`lmd`**" List Models in Depot : List models available in the depot&#x20;
* "**`im`**" Install Model(s) : Install model(s) from the depot&#x20;
* "**`nm`**" New Model : Create a new Telosys model (optionally from a database) .
* "**`em`**" Edit Model : Edit the current/given model .
* "**`cm`**" Check Model : Check the current/given model .
* "**`dm`**" Delete Model : Delete the current/given model&#x20;

**Entity commands:**&#x20;

* "**`le`**" List Entities : List the entities defined in the current model&#x20;
* "**`ee`**" Edit Entity : Edit an entity file&#x20;
* "**`ne`**" New Entity : Create a new entity in the current model&#x20;
* "**`de`**" Delete Entity : Delete the given entity in the current model

