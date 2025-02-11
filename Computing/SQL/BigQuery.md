---
tags:
  - SQL
---
BigQuery is a [[python]] package used for working with [[Database]]s by sending [[SQL]] query's .  

Example usage:
```python
from google.cloud import bigquery

# create a "client" object 
client = bigquery.Client()

# construct a reference to the "hacker_news" dataset
dataset_ref = client.dataset("hacker_news", project="bigquery-public-data")

# API request to fetch the dataset
dataset = client.get_dataset(dataset_ref)

# construct a reference to the "full" table in the dataset
table_ref = dataset_ref.table("full")

table = client.get_table(table_ref)
```

The `Client` plays a key role in retrieving the datasets from the BigQuery. 
*projects* are a collection of datasets. 
A *dataset* is a collection of tables. 
*tables* store the data.

An [[SQL query]] can be made to the dataset by passing the information to the client. 
Example usage: 
```python
# Query to select all the items from the "city" column where the "country" column is 'US'
query = """
        SELECT city
        FROM `bigquery-public-data.openaq.global_air_quality`
        WHERE country = 'US'
        """

# Create a "Client" object
client = bigquery.Client()

# Set up the query
query_job = client.query(query)
```
 
 In some cases it is important to ensure that the query we are making is not too large. This is important when working with large [[Database]]s that can contains many TB of data. Therefore, it is recommended to check how large the query will be beforehand and to set a maximum for how large the query can be. 

```python
# create a QueryJobConfig to estimate the size of the job without running it 
dry_run_config = bigquery.QueryJobConfig(dry_run=True)

# API request to estimate the size of the job
dry_run_job = client.query(query, job_config=dry_run_config)

# Get the total size of the job
Total_size = dry_run_job.total_bytes_processed

print(f"Total size of job: {Total_size}")
```

```python 
# Config to limit the ammount of data read to 1GB
safe_config = bigquery.QueryJobConfig(maximum_bytes_billed=10**9)

safe_query_job = client.query(query,safe_config)
```