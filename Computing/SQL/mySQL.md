---
tags:
  - SQL
Links:
  - https://www.digitalocean.com/community/tutorials/how-to-install-mysql-on-ubuntu-20-04
---
#### mySQL
mySQL is an open-source database management system. It implements the relational model and uses [[SQL]] to manage its data. 

To create a [[Database]] then we can run the command:
```SQL
CREATE DATABASE example;
```

While a table can be made with: 
```sql
CREATE TABLE example_table (
	example_key1 INT PRIMARY KEY,
	example_key2 VARCHAR(20),
	example_key3 VARCHAR(02)
);
```

The `DESCRIBE` keyword can be use to access information on the table.
##### Deleting
`DROP` can used to remove the table 
##### Modifying 
`ALTER` allows for extra columns to be added 

>[!example]-
>Creating a database called giraffe: 
>```SQL
>CREATE DATABASE giraffe;
>```
>switch to the database: 
>```SQL
>USE giraffe;
>```
>
>Then add a table:
>```SQL
>CREATE TABLE student (
>	student_id INT PRIMARY KEY,
>	name VARCHAR(50)
>	major VARCHAR(50)
>);
>```
>
>Get information on the created table: 
>```SQL
>DESCRIBE student; 
>```
>
>Add a new column to the table: 
>```SQL
>ALTER TABLE student ADD gpa DECIMAL(3,2);
>```
>
>Remove a column: 
>```SQL
>ALTER TABLE student DROP gpa;
>```
>
>Delete the table: 
>```SQL
>DROP TABLE student;
>```



