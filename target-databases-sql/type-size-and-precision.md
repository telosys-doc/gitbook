# Type size and precision

### Type size

The "**size**" is often required for SQL types like:

* CHAR(size)
* VARCHAR(size)
* VARCHAR2(size)
* NVARCHAR(size)
* BINARY(size)
* VARBINARY(size)

This is how the size value is determined:

1. if the attribute has a "**@DbType**" annotation this database type will be used "as is"\
   regardless of the target database\
   Example:\
   &#x20;   `name : string {`` `**`@DbType('VARCHAR(20)')`**`  ``}`\
   the SQL type will be **`VARCHAR(20)`**
2. else  if the attribute has a "**@Size**" annotation this value will be used \
   Example: \
   &#x20;   `name : string {`` `**`@Size(20)`**`}`\
   the SQL type will be \
   &#x20; \- **`VARCHAR(20)`** for PostgreSQL \
   &#x20; \- **`VARCHAR2(20)`** for Oracle
3. else  if the attribute has a "**@MaxLen**" annotation this value will be used \
   Example:\
   &#x20;   `name : string {`` `**`@MaxLen(12)`**`}`\
   the SQL type will be \
   &#x20; \- **`VARCHAR(12)`**  for PostgreSQL \
   &#x20; \- **`VARCHAR2(12)`** for Oracle
4. else  if the size is not mandatory ("%s") for the SQL type\
   then the type is generated without size, for example:\
   &#x20; \- **`VARCHAR`**  for PostgreSQL&#x20;
5. else  size is mandatory ("%S") and cannot be determined:\
   an error is thrown

Reminder: "_@DbSize(xx)_" annotation is deprecated (do  not use it)



### Type precision&#x20;

The "**precision**" is often required (or indispensable) for SQL types like:

* NUMERIC(precision)&#x20;
* NUMBER(precision)&#x20;
* DECIMAL(precision)
* FLOAT(precision)

The "**precision**" defines the number of digits for a decimal type, \
it can contains a "**scale**" (number of digits after the decimal).

Examples:&#x20;

* "10"  :  precision = 10 digits
* "8,2"  :  precision = 8 digits with 2 digits after the decimal (scale = 2)

This is how the precision value is determined:

1. if the attribute has a "**@DbType**" annotation this database type will be used "as is"\
   regardless of the target database\
   Example:\
   &#x20;   `weight : decimal {`` `**`@DbType('DECIMAL(5,2)')`**` ``}`\
   the SQL type will be  **`DECIMAL(5,2)`**
2. else  if the attribute has a "**@Size**" annotation this value will be used \
   Example: \
   &#x20;   `weight: decimal {`` `**`@Size(8,5)`**` ``}`\
   the SQL type will be \
   &#x20; \- **numeric(8,5)**   for PostgreSQL \
   &#x20; \- **NUMBER(8,5)**   for Oracle
3. else  if the attribute has a "**@MaxLen**" annotation this value will be used \
   Example:\
   &#x20;   `weight : decimal {`` `**`@MaxLen(12)`**` ``}`\
   the SQL type will be \
   &#x20; \- **`numeric(12)`** for PostgreSQL \
   &#x20; \- **`NUMBER(12)`** for Oracle
4. else  if the precision is not mandatory ("%p") for the SQL type\
   then the type is generated without precision, for example:\
   &#x20; \- **`numeric`**  for PostgreSQL \
   &#x20; \- **`NUMBER`&#x20;**&#x20;for Oracle&#x20;
5. else  precision is mandatory ("%P") and cannot be determined:\
   an error is thrown\


Reminder: "_@DbSize(xx)_" annotation is deprecated (do  not use it)

