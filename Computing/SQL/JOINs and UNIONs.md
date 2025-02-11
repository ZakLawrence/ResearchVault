---
tags:
  - SQL
---
#### JOINs and UNIONs
Both the [[Join]] and [[Unions]] keywords can be used in conjunction with [[Common table expression]]s to create an [[SQL query]] that performs relatively complex operations. 

>[!example]-
> From the Hacker News dataset there are two tables that we can consider, one containing information on `comments` and another with information on the `stories`. 
> 
> The following query pulls information from the `stories` and `comments` tables to create a new table showing all the stories that were posted on a given date and the number of comments. 
> ```SQL
> WITH c AS 
> (
> 	SELECT parent, COUNT(1) as num_comments
> 	FROM `bigquery-public-data.hacker_news.comments` 
> 	GROUP BY parent
> )
> SELECT s.id as story_id, s.by, s.title, c.num_comments
> FROM `bigquery-public-data.hacker_news.stories` AS s
> LEFT JOIN c
> ON s.id = c.parent
> WHERE EXTRACT(DATE FROM s.time_ts) = '2012-01-01'
> ORDER BY c.num_comments DESC
>```
>
>Next we can get any user that wrote a comment or a story on a given date. 
>```SQL
>SELECT c.by 
>FROM `bigquery-public-data.hacker_news.comments` AS c
>WHERE EXTRACT(DATE FROM c.time_ts ) = '2014-01-01'
>UNION DISTINCT
>SELECT s.by 
>FROM `bigquery-public-data.hacker_news.stories` AS s
>WHERE EXTRACT(DATA FROM s.time_ts) = '2014-01-01'
>```






