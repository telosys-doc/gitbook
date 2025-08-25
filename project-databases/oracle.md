# Oracle

### Structure

Server (instance) → **Database** → **User=Schema** → Tables/Objects&#x20;

<div align="left"><figure><img src="../.gitbook/assets/image (5).png" alt="" width="301"><figcaption></figcaption></figure></div>

* **Database**: In Oracle, the "database" is the entire system of data files, control files, redo logs, etc. A database is tied to an **instance** (set of processes + memory structures). Usually, one instance ↔ one database, though RAC can have multiple instances for one database.
*   **Schema**: In Oracle, a schema is essentially **a user account**.

    When you create a user (`CREATE USER foo IDENTIFIED BY ...`), Oracle automatically creates a schema with the same name. That schema contains all objects owned by that user (tables, views, procedures, etc.).

    There isn’t a concept of multiple schemas under one user; it’s a **1:1 mapping** (**user = schema**).

    It is possible to query another user's objects (cross-schema access) if you have the permissions





