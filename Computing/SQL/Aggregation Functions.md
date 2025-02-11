---
tags:
  - SQL
---
#### COUNT()
`COUNT()` is an aggregation function that returns a count of the number of things passes as an argument. Some examples of other aggregation functions are: 
- `SUM()`
- `AVG()`
- `MIN()`
- `MAX()`

#### GROUP BY
The `GROUP BY` keyword takes one or more columns and treats all rows with the same value in the column as a single group when applying an aggregation function. 

#### HAVING
`HAVING` is used in combination with `GROUP BY` to ignore groups that don't meet certain criteria 
> [!example]-
> An example query that involves these keywords is: 
>```SQL
>SELECT parent, COUNT(id)
>FROM `bigquery-public-data.hacker_news.full`
>GROUP BY parent
>HAVING COUNT(id) > 10
>```

#### Aliasing
The aggregation function will give a column that will have a name of the form `f0__` which is not very descriptive. Therefore it is possible to use `AS` to assign a more descriptive name 
```SQL
SELECT parent, COUNT(1) AS NumPosts
FROM `bigquery-public-data.hacker_news.full`
GROUP BY parent
HAVING COUNT(1) > 10
```
