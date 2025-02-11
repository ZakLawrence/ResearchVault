---
tags:
  - SQL
---
#### ORDER BY
The `ORDER BY` keyword is typically the last clause in an [[SQL query]], it sorts the results returned by the rest of the query. 
The `DESC` option can be added to the query to reverse the order of the sorting. 

> [!example]-
> An example of a query that uses `ORDER BY` is:
>```sql
SELECT indicator_code, indicator_name, COUNT(1) AS num_rows
FROM `bigquery-public-data.world_bank_intl_education.international_education`
WHERE year = 2016
GROUP BY indicator_name, indicator_code
HAVING COUNT(1) >= 175
ORDER BY COUNT(1) DESC
>```
