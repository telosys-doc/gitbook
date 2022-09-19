# Predefined rules

Telosys provides predefined rules to generate SQL for the most common databases.

To use them, simply indicate the base type in the template file (.vm).

The target database can be specified using the following directive :

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
