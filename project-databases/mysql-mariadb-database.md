# MySQL/MariaDB database

### Structure

Server → **Database** (= **Schema**) → Tables/Objects

<div align="left"><figure><img src="../.gitbook/assets/image (1).png" alt="" width="242"><figcaption></figcaption></figure></div>

* **Database**: The main organizational unit. In practice, a "**database**" in MySQL is what most people think of as a "**schema**". When you run `CREATE DATABASE`, it’s like creating a schema.
* **Schema**: Synonymous with database. \
  MySQL treats `CREATE DATABASE foo;` and `CREATE SCHEMA foo;` as the same operation.
* Cross-database queries are allowed within the same server instance (`db1.table1 JOIN db2.table2`)

### Telosys typical configuration for a MySQL/MariaDB database

```yaml
xxx


```
