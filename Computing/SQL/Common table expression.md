---
tags:
  - SQL
---
A *Common Table Expression* or *CTE* is a temporary table that is returned within an [[SQL query]]. They help to split the query up into readable chunks. We can take the information contained within a *CTE* and perform a query on that table. 
The  *CTE* will only exist within the query where it is created so it cannot be used in later queries. Therefore any query that used a *CTE* will be structured into two parts:
1. Creating the *CTE*
2. Writing a query that used the *CT*
 
> [!example]-
> An example use case is: 
>```SQL
>WITH Seniors AS 
>(
>	SELECT ID, Name
>	FROM `bigquery-public-data.pet_records.pets`
>	WHERE Years_old > 5
>)
>SELECT ID
>FROM Seniors
>```
