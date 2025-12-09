---
icon: bullseye-arrow
---

# Target SQL scripts

With Telosys you can generate SQL scripts to manage your database (create table, drop table, foreign key definition, etc).

As SQL statements may differ depending on the type of database you are targeting, Telosys has a configuration system that allows the generated SQL to be adapted to the target database.

This can be done in 2 ways:

* using [**predefined rules**](predefined-rules.md)&#x20;
* using [**specific rules**](specific-rules.md)

### Database customization behavior

If **no rules** have been defined (neither predefined nor specific), then the "**ANSI-SQL**" will be used by default.

If you have defined both predefined rules and specific rules, the specific rules will apply (the more specific takes precedence).

Whatever your rules definition, if an entity or an attribute has database annotations in the model (@DbName, @DbType, @DbTable, etc) those annotations will be used first.

In the templates the database configuration has an influence on:&#x20;

* $entity.sqlTableName&#x20;
* $entity.sqlPrimaryKeyColumns&#x20;
* $entity.sqlPrimaryKeyColumnsAsString<br>
* $attribute.sqlColumnName&#x20;
* $attribute.sqlColumnType&#x20;
* $attribute.sqlColumnConstraints<br>
* $fk.sqlName&#x20;
* $fk.sqlOriginTableName&#x20;
* $fk.sqlOriginColumns&#x20;
* $fk.sqlOriginColumnsAsString&#x20;
* $fk.sqlReferencedTableName&#x20;
* $fk.sqlReferencedColumns&#x20;
* $fk.sqlReferencedColumnsAsString<br>
* $sql object



