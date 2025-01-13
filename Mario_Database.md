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

- Here's how you can rename a column:
```sql
ALTER TABLE table_name RENAME COLUMN column_name TO new_name;
``` 

- Rows are the actual data in the table. You can add one like this:
```sql
INSERT INTO table_name(column_1, column_2) VALUES(value1, value2);
```

- You can view the data in a table by querying it with the SELECT statement. Here's how it looks:
```sql
SELECT columns FROM table_name;
```
- Here's an example of how to delete a row:
```sql
DELETE FROM table_name WHERE condition;
```
- Drop second_table from your database. Here's an example:
```sql
DROP TABLE table_name;
```

- You can rename a database like this:
```sql
ALTER DATABASE database_name RENAME TO new_database_name;
```

- The `SERIAL` type will make your column an `INT` with a NOT NULL constraint, and automatically increment the integer when a new row is added.

- Adding rows one at a time is quite tedious. Here's an example of how you could have added the previous three rows at once:
```sql
INSERT INTO characters(name, homeland, favorite_color)
VALUES('Mario', 'Mushroom Kingdom', 'Red'),
('Luigi', 'Mushroom Kingdom', 'Green'),
('Peach', 'Mushroom Kingdom', 'Pink');
```

- It looks good, but there's a few mistakes. You can change a value like this:
```sql
UPDATE table_name SET column_name=new_value WHERE condition;
```

- Actually, you should put that in order. Here's an example:
```sql
SELECT columns FROM table_name ORDER BY column_name;
```

- How to add a primary key. It's a column that uniquely identifies each row in the table. Here's an example of how to set a PRIMARY KEY:
```sql
ALTER TABLE table_name ADD PRIMARY KEY(column_name);
```

- You can see the key for your name column at the bottom. It would have been better to use character_id for the primary key. Here's an example of how to drop a constraint:
```sql
ALTER TABLE table_name DROP CONSTRAINT constraint_name;
```

- Give it a type of `NUMERIC(4, 1)`. That data type is for decimals. `NUMERIC(4, 1)` has up to four digits and one of them has to be to the right of the decimal.

- To know what row is for a character, you need to set a foreign key so you can relate rows from this table to rows from your characters table. Here's an example that creates a column as a foreign key:
```sql
ALTER TABLE table_name ADD COLUMN column_name DATATYPE REFERENCES referenced_table_name(referenced_column_name);
```

- There's your foreign key at the bottom. These tables have a "one-to-one" relationship. One row in the characters table will be related to exactly one row in more_info and vice versa. Enforce that by adding the UNIQUE constraint to your foreign key. Here's an example:
```sql
ALTER TABLE table_name ADD UNIQUE(column_name);
```

- The column should also be NOT NULL since you don't want to have a row that is for nobody. Here's an example:
```sql
ALTER TABLE table_name ALTER COLUMN column_name SET NOT NULL;
```