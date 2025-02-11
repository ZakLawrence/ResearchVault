---
tags:
  - SQL
---
The `AS` and `WITH` keywords are particularly useful for tidying up queries and making them easier to read. 

#### AS
The `AS` keyword is used for aliasing which works similarly to how it is done in [[python]]

#### WITH ... AS
The `AS` keyword can be used in combination with the `WITH` keyword to form a [[Common table expression]] 

An example use case is getting the number of bitcoin transactions on a given date: 
```SQL
WITH time AS 
(
	SELECT DATE(block_timestamp) AS trans_date
	FROM `bigquery-public-data.crypto_bitcoin.transactions`
)
SELECT COUNT(1) AS transactions, trans_date
FROM time
GROUP BY trans_date
ORDER BY trans_date
```

This allows for a lot of data cleaning to be done in SQL, which is faster than working in python packages such as pandas.  

An example of a query that will look at data for taxi trips in Chicago ordered by time of day is:
```SQL
WITH RelevantRides AS
(
    SELECT EXTRACT(HOUR FROM trip_start_timestamp) AS hour_of_day, 
	    trip_miles, 
	    trip_seconds  
    FROM `bigquery-public-data.chicago_taxi_trips.taxi_trips`
    WHERE trip_start_timestamp > '2016-01-01' AND 
		  trip_start_timestamp < '2016-04-01' AND 
		  trip_seconds >0 AND trip_miles >0
)
SELECT hour_of_day, 
	COUNT(1) AS num_trips, 
	3600 * SUM(trip_miles)/SUM(trip_seconds) AS avg_mph
FROM RelevantRides
GROUP BY hour_of_day
ORDER BY hour_of_day
```