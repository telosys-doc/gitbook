# Specific rules

If your database is not part of the predefined databases, or if the generated SQL does not match your needs, you can define your own SQL generation rules.

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

### Defining specific conversion rules in a file

A specific rules file is a text file (properties file) containing 2 parts:

* Naming conventions  (prefix "conv.")
* Type conversion (prefix "type.")



**1) Naming conventions:**

You can set the naming convention to be applied for **tables**, **columns**, **primary keys** and **foreign keys**.

There are 4 naming standards (choose one of these):

* **camelCase**
* **PascalCase**
* **snake\_case**
* **ANACONDA\_CASE**

Examples:&#x20;

```
conv.tableName  = ANACONDA_CASE
conv.columnName = snake_case
conv.pkName = PascalCase
conv.fkName = camelCase
```

**2) Type conversion:**

This part defines how to convert a **neutral type** (Telosys model type) to an **SQL type** (in the database).

Syntax:

* Left side:\
  the **neutral type** with "type." prefix and optionally the ".autoincr" suffix \
  if used for autoincremented attribute
*   Right side:\
    any string to be used as the **SQL type** for this neutral type\
    with placeholders for "**size**" and "**precision**":

    * "**(%s)**" : size (optional)
    * "**(%S)**" : size mandatory
    * "**(%p)**" : precision (optional)
    * "**(%P)**" : precision mandatory

    See [type size and precision](type-size-and-precision.md) for more information

Examples:&#x20;

```
type.string = VARCHAR(%s)
type.string = VARCHAR2(%s)
  
type.byte          = smallint
type.byte.autoincr = smallserial

type.short          = smallint
type.short.autoincr = smallserial

type.int           = integer
type.int.autoincr  = serial

type.long          = bigint
type.long.autoincr = bigserial

type.decimal   = numeric(%p)
type.decimal   = numeric(%P) 
type.float     = real
type.double    = double precision
  
type.boolean   = boolean
type.boolean   = CHAR(1)

type.date      = date

type.time      = time
type.time      = time with time zone

type.timestamp = timestamp
type.timestamp = timestamp with time zone
  
type.binary    = bytea
```
