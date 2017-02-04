# MySql: Analysis, understanding and optimization of queries

* MySQL 5.7
* Sakila Sample Database

## Query Execution PLan
* How to get from point a to point B
* EXPLAIN 'Query'
	* Explains the query to be executed in detail
* USE INDEX
	* CREATE INDEX name ON table(column);
* ANALYZE TABLE name;
* INDEXES ARE NOT FREE, there is always a cost in terms of storage and performance
* SHOW WARNINGS
* DEPENDENT SUBQUERY is something to investigate

## SUMMARY
* EXPLAIN at the beginning
* PROFILE
* TEST your queries, use a descent amount of data, synch prod in staging
* CHEAT take advantage of caching