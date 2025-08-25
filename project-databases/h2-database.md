# H2 database

### Structure

**Database** → **Schema** → Tables/Objects

<div align="left"><figure><img src="../.gitbook/assets/image (2).png" alt="" width="246"><figcaption></figcaption></figure></div>

* **Database**: In H2, the "database" is basically the connection (in-memory or file). \
  There’s only one database per connection.
* **Schema**: H2 supports schemas, similar to PostgreSQL and SQL Server. Default schema is `PUBLIC`. You can create others (`CREATE SCHEMA sales;`). Objects belong to schemas.

### H2 modes

H2 can run in **3 main modes**:

1. **Embedded**  (in-process, `jdbc:h2:mem:`)
2. **Server mode** (with external connections)
3. **Mixed mode** (embedded + server at the same time)



### Telosys typical configuration for a H2 database

```yaml
xxx

```
