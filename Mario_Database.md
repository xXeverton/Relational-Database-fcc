# Learn Relational Databases by Building a Mario Database

- Log in PostgreSQL:
```sql
psql --username=frecodecamp --dbname=postgres
```
- To see what database are there: `\l`

- To create your own database:
```sql
CREATE DATABASE database_name;
```

- You can connect to a database by entering:`\c database_name`

- To display the tables: `/d`
- You can create a table like this:
```sql 
CREATE TABLE table_name(); 
```

- You can view more details about a table by adding the table name after the display command like this: `\d table_name`

- Tables need columns to describe the data in them, yours doesn't have any yet. Here's an example of how to add one:
```sql
ALTER TABLE table_name ADD COLUMN column_name DATATYPE;
```

- You will probably need to know how to remove them. Here's an example:
```sql
ALTER TABLE table_name DROP COLUMN column_name;
```