---
tags:
  - SQL
---
#### JOIN
In some cases the data that we are interested in may be split across multiple tables. In that case we need to make use of `JOIN`.
   
An example is one table that contains information on `pets` with the columns:
  - `ID`: ID number for the pet.
  - `Name`: Name of the pet.
  - `Animal`: type of animal. 

And another for the `owners` that contains the columns:
  - `ID`: ID number for the owner, this can be different from the pet.
  - `Name`: Name of the owner.
  - `Pet_ID`: ID number of the pet than belongs to the owner.

 Using join we can write a query to combine the tables:
```SQL
SELECT p.NAME AS Pet_Name, o.NAME AS Owner_Name
FROM `bigquery-public-data.pet_records.pets` AS p
INNER JOIN `bigquery-public-data.pet_records.owners` AS o ON p.ID = o.Pet_ID 
```

> [!tip]- Tip
In general, when you're joining tables, it's a good habit to specify which table each of your columns comes from. That way, you don't have to pull up the schema every time you go back to read the query.

The type of join can be specified, with `INNER JOIN` meaning that a row is only in the final output if the value in the columns being combined shows up in both tables. 
There are other types of `JOIN` that are encountered. 

> [!example]- How many files are covered by a software license?
> [[GitHub]] contains many repos which are shared under a specific legal license. The data set that we will look at contains two tables. One is the `licenses` table that contains the name of the repo and the license.
> The second table is the `sample_files` table, that contains the GitHub repo that each file belongs to. 
> 
> We can write a query for the number of files per license as: 
> ```SQL
> SELECT L.license, COUNT(1) AS number_of_files
> FROM `bigquery-public-data.github_repos.sample_files` AS sf
> INNER JOIN `bigquery-public-data.github_repos.licenses` AS L 
> 	ON sf.repo_name = L.repo_name
> GROUP BY L.license
> ORDER BY number_of_files DESC
>```
>

`LEFT JOIN` is used to return all the row of the two tables that have matching entries along with all the rows of the left table (whether there is a match or not)

`RIGHT JOIN` similarly returns all the rows of the two tables that have matching entries along with all the rows of the right table (whether there is a match or not)

`FULL JOIN` returns all the rows from both tables. 

For all the cases if there is not a matching entry then the corresponding table will have NULL entries. 

It is possible to chain multiple `JOIN` statements together to join multiple tables together: 
```SQL
SELECT o.Name AS Owner_name, p.Name AS Pet_Name, t.Treat AS Fav_treat
FROM `bigquery-public-data.pet_records.pets` AS p
FULL JOIN `bigquery-public-data.pet_records.owners` AS o 
ON p.ID = o.Pet_ID
LEFT JOIN `bigquery-public-data.pet_records.treats` AS t
ON p.ID = t.Pet_ID
```


