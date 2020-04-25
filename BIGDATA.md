# BIG DATA

Created by Vince Chang </br>

#### HADOOP

- [Hadoop Tutorial](https://www.youtube.com/watch?v=mafw2-CVYnA&t=713s)
- Hadoop is an open source, Java-based programming framework that supports the
  processing and storage of extremely large data sets in a distributed computing
  environment.
- Has enormous processing ower and the ability to handle virtually limitless
  concurrent tasks or jobs
- Hadoop is not a type of DB, but rather a software ecosystem that allows
  parallel computing

#### HADOOP DISTRIBUTED FILE SYSTEM (HDFS)

- A distributed file system that provides high-throughput access to application
  data

#### AMBARI

- A web-based tool for provisioning, managing, and monitoring Apache Hadoop
  clusters which includes support for HDFS, Sqoop, etc. Ambari also provides a
  dashboard for viewing cluster health such as Hive applications

#### SQOOP

- Sqoop is a tool designed for efficiently transferring bulk data between
  Hadoop and structured datastores such as relational databases

#### HIVE

- [Hive Tutorial](https://www.youtube.com/watch?v=dQueAnZSJRM)
- A data warehouse infrastructure that provides data summarization and ad hoc
  querying built on top of Hadoop
- Hive provides a mechanism to project structure onto the data and query the
  data using SQL-like language called HiveQL
- Hive uses Map Reduce and HDFS (data is in here) for Processing and storage/
  retrieval of data
- I write SQL and Hive talks to Hadoop to do MapReduce
- Client Side application with an interactive shell
- By default, Hive uses Embedded Metastore to keep metadata in a Derby Database
  but you can configure your own

#### ADVANTAGES OF HIVE

- It can be used as an ETL (extract, transform, load)
- Can handle large data sets
- SQL (filters, joins, group by) on top of Map Reduce
- All Hive queries will be converted to MapReduce job for execution, but is too
  complex to write ourselves.

#### DISADVANTAGES OF HIVE

- Queries are slow because of MapReduce, if you need a query right away, no
  need for Hive
- If you don't have big data, don't use Hive!
- If you don't have a schema, don't use Hive, because when you create a data
  table, you will use a schema (csv files etc)

#### DIFFERENCE FROM SQL

- Hive query executes on a Hadoop infrastructure rather than a traditional DB
- This allows Hive to scale to handle huge data sets
- The internal execution of a Hive query is via a series of automatically
  generated MapReduce jobs
