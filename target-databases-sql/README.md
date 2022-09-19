# Target databases (SQL)

With Telosys you can generate SQL scripts to manage your database.&#x20;

As SQL statements may differ depending on the type of database you are targeting, Telosys has a configuration system that allows the generated SQL to be adapted to the target database.

### Predefined database type

The target database can be specified in the template files (.vm) using the following directive :

```
#set ( $env.database = 'databaseType' )
```

In version 4.0 Telosys as the following predefined database types:

* POSTGRESQL&#x20;
* MYSQL&#x20;
* ORACLE&#x20;
* SQLSERVER&#x20;
* ANSISQL  (for standard ANSI-SQL )

The predefined database types are not case sensitive.

Examples:

```
#set ( $env.database = 'postgresql' )
#set ( $env.database = 'PostgreSQL' )
#set ( $env.database = 'POSTGRESQL' )
```

If you try to use an unknown database name, an error will occur.



### Specific database type

If your database is not part of the predefined databases, or if the generated SQL does not suit you, you can define your own SQL generation rules.

To do this, you just need to create a **file** containing the **conversion rules**.

The rules file can be specified in the template files (.vm) using the following directive:&#x20;

```
#set ( $env.databaseConvFile = $myOwnFile )
```

Examples:&#x20;

```
#set ( $env.databaseConvFile = $fn.fileFromBundle('mydb.properties') )
#set ( $env.databaseConvFile = $fn.fileFromModel('mydb.properties') )
```

### Defining specific conversion rules

A specific rules file is a text file (properties) containing 2 parts:

* Naming conventions  (prefix "conv.")
* Type conversion (prefix "type.")

**Naming conventions:**

You can set the naming convention to be applied for tables, columns, primary keys and foreign keys.

There are 4 naming standards (choose one of these):

* camelCase
* PascalCase
* snake\_case
* ANACONDA\_CASE

Examples:&#x20;

```
conv.tableName  = ANACONDA_CASE
conv.columnName = snake_case
conv.pkName = PascalCase
conv.fkName = camelCase
```

**Type conversion:**

This part defines how to convert a neutral type (Telosys model type) to an SQL type (in the database).







### Database customization behavior

If you have defined both a predefined database name and a rules file, the rules file will apply (the more specific takes precedence).

If nothing has been defined, the "ANSI-SQL" will be used by default.

