---
tags:
  - SQL
---
#### Analytic Functions 
In addition to the built in [[Aggregation Functions]] it is possible to define analytic function that operates on a set of rows but may return a different value for each row in the table. 

A use case may be where we want to calculate a moving average for data in a table. An example of one such query is 
```SQL
SELECT *, AVG(time) OVER (
	PARTITION BY id
	ORDER BY date
	ROWS BETWEEN 1 PRECEDING AND CURRENT ROW
) AS avg_time
FROM `bigquery-public-data.runners.train_time`
```

All analytic functions make use of the `OVER` clause which defines the sets of rows that are used in each calculation. The `OVER` clause has three optional parts: 
- The `PARTITION BY` divides the rows of the table into different groups, here it divides by `id` so that the calculation is done separately per runner. 
- The `ORDER BY` clause defines the ordering within each of the partition. Within this example it is ordered by the `date` so that the earlier sessions appear first. 
- The final clause is the window frame. It identifies the set of rows that are used in the calculation. 

> [!example]
> The *window frame* clause has many possible forms, some examples are: 
> - `ROWS BETWEEN 1 PRECEDING AND CURRENT ROW`- The previous row and current row 
> - `ROWS BETWEEN 3 PRECEDING AND 1 FOLLOWING` - The 3 previous, current and one following 
> - `ROWS BETWEEN UNBOUND PRECEDING AND UNBOUND FOLLOWING`- all rows in the partition. 

#### Three types of analytic functions 

##### 1. Analytic aggregation functions 
[[Aggregation Functions]] take all the values within the window frame and returns a single value:
- `MIN()` and `MAX()` returns the minimum or maximum of the input values 
- `AVG()` and `SUM()` returns the average or sum of the input values 
- `COUNT()` returns the number of rows in the input. 

##### 2. Analytic navigation functions 
[[Navigation Functions]] assign a value based on the value in a different row to the current row: 
- `FIRST_VALUE()` or `LAST_VALUE()` returns the first or last value in the input 
- `LEAD()` and `LAG()` return the value on a subsequent or preceding row. 

##### 3. Analytic numbering functions 
[[Numbering Functions]] assign integer values to each row based on the ordering:
- `ROW_NUMBER()` returns the order in which the row appears in the input
- `RANK()` all rows with the same value in the ordering column receive the same rand value

> [!example]- 
> We can use an analytic function to calculate the number of bike trips taken on a given day using the following query:
> 
> ```SQL
> WITH trips_by_day AS 
> (
> SELECT DATE(start_date) AS trip_date, COUNT(*) as num_trips 
> FROM `bigquery-public-data.san_francisco.bikeshare_trips`
> WHERE EXTRACT(YEAR FROM start_date) = 2015
> GROUP BY trip_date
> )
> SELECT *, 
> SUM(num_trips) OVER (
> 	ORDER BY trip_date
> 	ROWS BETWEEN UNBOUND PRECEDING AND CURRENT ROW
> ) AS cumulative_trips
> FROM trips_by_day
>```
>
>Another potential query is one that calculates the stations where each bike began and ended the day:
>```SQL
>SELECT bike_number, TIME(start_date) as trip_time,
>FIRST_VALUE(start_station_id) OVER(
>	PARTITION BY bike_number
>	ORDER BY start_date
>	ROWS BETWEEN UNBOUNDED PRECEDING AND UNBOUNDED FOLLOWING 
>) AS first_station_id,
>LAST_VALUE(end_station_id) OVER(
>	PARTITION BY bike_number
>	ORDER BY start_date
>	ROWS BETWEEN UNBOUNDED PRECEDING AND UNBOUNDED FOLLOWING
>) AS last_station_id,
>start_station_id,
>end_station_id
>FROM `bigquery-public-data.san_francisco.bikeshare_trips`
>WHERE DATE(start_date) = '2015-10-25'
>``` 




l
