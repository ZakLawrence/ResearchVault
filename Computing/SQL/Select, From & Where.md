---
tags:
  - SQL
---
#### SELECT, FROM
The most basic query that can be made is to select a specific column from a single table. For example: 
```SQL
SELECT Name
FROM `bigquery-public-data.pet_records.pets`
```

The destination in `FROM` must be within back ticks. 
The `SELECT` keyword also allows us to provide wildcard arguments, such as `*` which will select all the columns in the dataset. 
#### WHERE
The `WHERE` keyword is used to retrieve data based on conditions. for example finding only the rows where `Animal` has the text `cat`. 
```SQL
SELECT Name
FROM `bigquery-public-data.pet_records.pets`
WHERE Animal = 'cat'
```

The `WHERE` keyword is also able to compare text using `LIKE`. This can make use of wildcards such as `%` which can be used in place of any number of characters.  