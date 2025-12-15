# Model structure

### Model structure&#x20;

Since version 4.0 each model is a **directory** located in "<mark style="color:purple;">**TelosysTools/models**</mark>".

The **directory name** is the **model name**.

<div align="left"><figure><img src="https://res.cloudinary.com/dhcihuzk8/image/upload/v1735580746/model-struct-001.png" alt=""><figcaption></figcaption></figure></div>

A model directory contains&#x20;

* a file "<mark style="color:purple;">**model.yaml**</mark>"&#x20;
* n files "<mark style="color:purple;">**.entity**</mark>" (1 for each entity)

Example : model "**employees**"&#x20;

<pre><code><strong>In "employees" directory:
</strong>- model.yaml (model file)
- Employee.entity (entity file)
- Company.entity (entity file)
- Project.entity (entity file) 
</code></pre>

The "model.yaml" contains basic informations about the model

Each ".entity" file defines an entity, see [Entity](entity.md) page for more information about the grammar.



### How to use Git to clone and push a model?

See  [Install with Git](/broken/pages/P37qwNGxA9VBV9yiSFkU)  and  [Publish with Git](/broken/pages/aAH24lA3MNXizn2RPiS1)

