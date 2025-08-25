# H2 database

### Structure

**Database** → **Schema** → Tables/Objects

* **Database**: In H2, the "database" is basically the connection (in-memory or file). \
  There’s only one database per connection.
* **Schema**: H2 supports schemas, similar to PostgreSQL and SQL Server. Default schema is `PUBLIC`. You can create others (`CREATE SCHEMA sales;`). Objects belong to schemas.



### Telosys typical configuration for a H2 database

```yaml
xxx

```
