---
tags:
  - SQL
---
#### UNIONs
Like [[Join]] the `UNION` keyword is used to combine tables together, however this will be done vertically instead of horizontally.  

> [!note]- 
> When using `UNION` the data types of both the columns must be the same 

To get all the values including any duplicates then the `UNION ALL` keyword should be used, while duplicated values can be dropped using the `UNION DISTINCT` keyword. 

> [!example]-
> This example creates a list of all the ages from the pets and owners tables: 
> ```SQL
> SELECT Age FROM `bigquery-public-data.pet_records.pets`
> UNION ALL
> SELECT Age FROM `bigquery-public-data.pet_records.owners`
>```

