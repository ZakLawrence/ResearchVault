---
tags:
  - SQL
---
#### Nested Data
In some datasets it may be the case that instead of separating the information into two tables that one of the tables is simple collapsed into a single column. This is a *nested column* 
A Nested column has the type of `STRUCT` or `RECORD`. 

To access the data in a nested column we can use dot notation to access it. For example: 
- `Toy.Name` refers to the "Name" field in the "Toy" column
- `Toy.Type` refers to the "Type" field in the "Toy" column

#### Repeated Data
Another situation that often occurs is that there can be multiple items in a single column, such a column will show as `REPEATED` and contain an `array` of the data. 

When querying repeated data then we need to use the `UNNEST()` function which flattens the repeated data. 

#### Nested and Repeated Data
In the case that a column contains and `array` of data where each item is a dictionary with multiple items then we can access them with a [[SQL query|query]] of the form:
```SQL
SELECT Name AS Pet_Name,
t.Name AS Toy_Name
t.Type AS Toy_type 
FROM `bigquery-public-data.pet_records.more_pets_and_toys`,
UNNEST(Toys) AS t
```

Storing data in this way means that we can avoid having to use [[Join|JOIN]] statements which increases the performance and simplifies the [[SQL query|query]] process. 

> [!example]-
> This example makes use of [Google Analytics Sample](https://www.kaggle.com/datasets/bigquery/google-analytics-sample) dataset that contains information tracking the behaviour of visitors to Google's merchandise store. 
> There are many nested fields within this dataset, an example query that can be applied to this dataset is: 
> ```SQL
> SELECT device.browser AS device_browser, SUM(totals.transactions) AS total_transactions
> FROM `bigquery-public-data.google_analytics_sample.ga_sessions_20170801`
> GROUP BY device_browser
> ORDER BY total_transactions DESC
>```
>Which will give a table showing the total transactions from browsers of different types. 
>
>The `hits` column contains both nested and repeated data.
>- "hits" is a `STRUCT` and is repeated
>- "hitNumber", "page", and "type" are all nested inside the "hits" column
>- "pagePath" is nested within the "page" field. 
>
>The following query can be used to handle this data:
>```SQL
>SELECT hits.page.pagePath as path, 
>COUNT(hits.page.pagePath) as counts
>FROM `bigquery-public-data.google_analytics_sample.ga_sessions_20170801`, 
>UNNEST(hits) AS hits
>WHERE hits.type='PAGE' AND hist.hitNumber=1
>GROUP BY path 
>ORDER BY counts DESC
>```
>Which gives a table with information on how most users land on the the site from a given page.





