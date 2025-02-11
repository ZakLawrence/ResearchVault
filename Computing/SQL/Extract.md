---
tags:
  - SQL
---
#### EXTRACT
The `EXTRACT` keyword can be used to get information from part of a column. As an example it can be used to get the day from a `DATE` object: 
```SQL
SELECT Name, EXTRACT(DAY from Date) AS Day
FROM `bigquery-public-data.pet_records.pets_with_date`
```

Along with the Day of the week it is possible to extract further information such as the week. 

```sql
SELECT COUNT(consecutive_number) AS num_accidents, EXTRACT(DAYOFWEEK FROM timestamp_of_crash) AS day_of_week
FROM `bigquery-public-data.nhtsa_traffic_fatalities.accident_2015`
GROUP BY day_of_week
ORDER BY num_accidents DESC
```
