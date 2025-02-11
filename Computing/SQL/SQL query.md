---
tags:
  - SQL
---
A [[SQL]] query is used to retrieve information from a [[Database]]. The are several keyword arguments that are used to do this:
- [[Select, From & Where]] 
- [[Aggregation Functions]]
- [[Order By]]
- [[Dates]]
- [[Extract]]
- [[As & With]] 
- [[Join]]
- [[Unions]] 
- [[Analytic Functions]]

#### Writing efficient queries
Often it is important not only to ensure that a query is working but that it is efficient. This is particularly true if it is being run multiple times on a large [[Database]]. A slow query is often a costly one, both in terms of time and money. 

The effectiveness of different queries can be compared by looking at the amount of data scanned and the time take to run the query. 
```python 
from google.cloud import bigquery 
from time import time 

client = bigquery.Client()

def show_amount_of_data_scanner(query):
	# dry_run lets us see the ammount of data used without running it
	dry_run_config = bigquery.QueryJobConfig(dry_run=True)
	query_job = client.query(query,job_config=dry_run_config)
	print('Data processed: {} GB'.format(rount(query_job.total_bytes_processes/10**9,3)))

def show_time_to_run(query):
	time_config = bigquery.QueryJobConfig(use_query_cache=False)
	start = time()
	query_result = client.query(query,job_config=time_config).result()
	end = time()
	print('Time to run: {} seconds'.format(round(end-start,3)))
```

##### Strategies
###### 1. Only selecting columns needed 
One clear strategy is to only select the columns that are actually needed. While it is easier to select all the columns this will result in a query returning more data than is actually needed. The following example shows this in action:

```python 
star_query = "SELECT * FROM `bigquery-public-data.github_repos.contents`"
show_amount_of_data_scanned(star_query)

basic_query = "SELECT size, binary FROM `bigquery-public-data.github_repos.contents`"
show_amount_of_data_scanned(basic_query)
```
Data processed: 2682.118 GB
Data processed: 2.531 GB

###### 2.Read less data 
It is also possible to reduce the data used by reading less of the data if we don't need to. 
```python
more_data_query = """
                  SELECT MIN(start_station_name) AS start_station_name,
                      MIN(end_station_name) AS end_station_name,
                      AVG(duration_sec) AS avg_duration_sec
                  FROM `bigquery-public-data.san_francisco.bikeshare_trips`
                  WHERE start_station_id != end_station_id 
                  GROUP BY start_station_id, end_station_id
                  LIMIT 10
                  """
show_amount_of_data_scanned(more_data_query)

less_data_query = """
                  SELECT start_station_name,
                      end_station_name,
                      AVG(duration_sec) AS avg_duration_sec                  
                  FROM `bigquery-public-data.san_francisco.bikeshare_trips`
                  WHERE start_station_name != end_station_name
                  GROUP BY start_station_name, end_station_name
                  LIMIT 10
                  """
show_amount_of_data_scanned(less_data_query)
```
Data processed: 0.076 GB
Data processed: 0.06 GB

###### 3. Avoid N:N JOINs
Most times that we have used `JOIN` has been a 1:1 `JOIN`, this is the case where each row in each table has at most one match in the other table. 
Another example is a N:1 `JOIN`, this is where each row in one table may have multiple potential matches to rows in the other table. 
Finally an N:N `JOIN` is the case that a group of rows in one table can match a group of rows in the other table. This will in general result in a table that has many more rows than either of the original tables. 
An example of how to avoid this is with 
```python 
big_join_query = """
                 SELECT repo,
                     COUNT(DISTINCT c.committer.name) as num_committers,
                     COUNT(DISTINCT f.id) AS num_files
                 FROM `bigquery-public-data.github_repos.commits` AS c,
                     UNNEST(c.repo_name) AS repo
                 INNER JOIN `bigquery-public-data.github_repos.files` AS f
                     ON f.repo_name = repo
                 WHERE f.repo_name IN ( 'tensorflow/tensorflow', 'facebook/react', 'twbs/bootstrap', 'apple/swift', 'Microsoft/vscode', 'torvalds/linux')
                 GROUP BY repo
                 ORDER BY repo
                 """
show_time_to_run(big_join_query)

small_join_query = """
                   WITH commits AS
                   (
                   SELECT COUNT(DISTINCT committer.name) AS num_committers, repo
                   FROM `bigquery-public-data.github_repos.commits`,
                       UNNEST(repo_name) as repo
                   WHERE repo IN ( 'tensorflow/tensorflow', 'facebook/react', 'twbs/bootstrap', 'apple/swift', 'Microsoft/vscode', 'torvalds/linux')
                   GROUP BY repo
                   ),
                   files AS 
                   (
                   SELECT COUNT(DISTINCT id) AS num_files, repo_name as repo
                   FROM `bigquery-public-data.github_repos.files`
                   WHERE repo_name IN ( 'tensorflow/tensorflow', 'facebook/react', 'twbs/bootstrap', 'apple/swift', 'Microsoft/vscode', 'torvalds/linux')
                   GROUP BY repo
                   )
                   SELECT commits.repo, commits.num_committers, files.num_files
                   FROM commits 
                   INNER JOIN files
                       ON commits.repo = files.repo
                   ORDER BY repo
                   """

show_time_to_run(small_join_query)
```
Time to run: 13.028 seconds
Time to run: 4.413 seconds

The first query has a large N:N `JOIN` which results in the time take being significantly increased. 