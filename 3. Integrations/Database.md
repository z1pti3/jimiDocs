---
sort: 8
---

# Database

Basic Querying of Databases with JIMI Flow. Currently Supports MSSQL and Oracle

## Download

[Download](https://github.com/b1scuit-thi3f/jimiPlugin-database)

## Install

```
wget https://github.com/b1scuit-thi3f/jimiPlugin-database/archive/master.zip
unzip master.zip
mv jimiPlugin-database-master plugin/database
rm master.zip
```

## Actions

### databaseSearch

Perform a query against a chosen host 

**Properties:**

| Name | Required | Replacement Syntax | Description |
--- | --- | --- | ---
dbType | True | False | The type of database (e.g. mysql, oracle)
host | True | True | The hostname/IP of the database host. This could include instance names
username | False | True | The username for the database
password | False | True | The password for the database
connectionDetails | False | True | Additional Key-Value pairs for the DB connection string
search/query | False | True | The search query
timeout | False | False | How long to attempt connecting before timing out. Default is 30s
limit | False | False | The number of results to return. 0 returns all
count | False | False | Return a count of the results, not the results themselves

**Returns:**

If limit is set to 1:

A dictionary with the first row returned from the query

If count is enabled:

An integer representing the number of rows returned

Otherwise:

An array of results containing a dictionary for each row


| Name | Result Bool | Return Code | Other |
--- | --- | --- | ---
Failure | False | 404 | "Could Not Connect" OR Error Code
Success | True | 0 | Dict OR Int OR Array (depending on options set above)
