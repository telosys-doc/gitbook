# Entity

### Entity file

Each entity is defined in a text file editable with any editor. \
The file name is composed of the **name of the entity** followed by the extension "**.entity**".

Examples :

```
Car.entity
Driver.entity
```

### Entity name

The entity name can be composed of : **letters**, **numbers** and "**\_**" (underscore). Other characters are not allowed. \
By convention the name usually starts with an upper case character. The entity name must be the same as the file name, for example if the file is "Car.entity" then the entity name must be "Car".

{% hint style="success" %}
Examples of **valid** entity names :&#x20;

* **Car**&#x20;
* **Car123**&#x20;
* **CarOwner**&#x20;
* **Car\_owner**
{% endhint %}

{% hint style="danger" %}
Examples of **invalid** entity names :

* **Car#12** ( "#" not allowed )&#x20;
* **Car+Owner** ( "+" not allowed )
{% endhint %}

### Comments

Comments can be placed anywhere in the file.\
A comment starts with "**//**".\
All the end of line located after "//" is the comment.\
Comments are only "single line" (no multi lines comments).

Example :

```
xxx  // the comment
```

### Entity structure

The entity structure is made up of the **name of the entity** followed by a block containing all of its **attributes and links**. The block containing the attributes and the links starts with **'{'** and ends with **'}'**. \
"End Of Line" characters are not significant. They are used only for readability. Potentially all the entity can be described in a single line.

Example :

```
EntityName {
   // attributes 
   id   : int { @Id } ; // attribute 'id'
   name : string  ; // attribute 'name'
   // links
   town : Town ; // link to the 'Town' entity
}
```



