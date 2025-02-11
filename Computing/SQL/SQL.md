---
tags:
  - SQL
---
#### SQL
*SQL* stands for Structured Query Language, it is a programming language used to work with [[Database]]s. 
It is a standardised language for interacting with [[Database management system#Relational Database Management Systems|Relational Database Management Systems (RDBMS)]]
and is used for performing *C.R.U.D* operations along with other administrative tasks. 

SQL is a hybrid language with four types of language in one: 
- *Data Query Language* (DQL)
	- Used to query the database for information 
	- Get information that is already stored in the database 
- *Data Definition Language* (DDL):
	- Used to define database schemas 
- *Data Control Language* (DCL):
	- Used for controlling access to the data in the database/ 
	- User & permission management
- *Data Manipulation Language* (DML):
	- Used for inserting, updating and deleting data from the database. 

As [[SQL query]] is a set of instructions given to the [[Database management system#Relational Database Management Systems|RDBMS]] that tells the system what information you want to retrieve. 

Within [[python]] it can be used with modules such as [[BigQuery]] to perform a [[SQL query]]. 

#### Data types 
Within SQL some of the possible variable types that can be added to a database are 
- `INT` - A whole number 
- `DECIMAL(M,N)`- decimal number with `M` total digits, `N` of which are decimals 
- `VARCHAR(N)` - string of text length `N`
- `BLOB`- binary large object 
- `DATE`
- `TIMESTAMP`