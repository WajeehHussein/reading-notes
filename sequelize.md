# Reading Day4

## [Home Page](/README.md)


## SQL vs NoSQL Database Differences Explained with few Example DB

## Differences between SQL & NOSQL
1. SQL as Relational DB ,NoSQL non-relational or distributed database.

2. SQL databases are table based databases whereas NoSQL databases are document. 

3. SQL databases have predefined schema whereas NoSQL databases have dynamic schema for unstructured data.

4. SQL databases are vertically scalable whereas the NoSQL databases are horizontally scalable. 

5. SQL database examples: MySql, Oracle, Sqlite, Postgres and MS-SQL. NoSQL database examples: MongoDB, BigTable, Redis, RavenDb, Cassandra, Hbase, Neo4j and CouchDb.

6. For complex queries: SQL databases are good fit for the complex query intensive environment whereas NoSQL databases are not good fit for complex queries.

7. For scalability: In most typical situations, SQL databases are vertically scalable. You can manage increasing load by increasing the CPU, RAM, SSD, etc, on a single server. On the other hand, NoSQL databases are horizontally scalable. You can just add few more servers easily in your NoSQL database infrastructure to handle the large traffic.

8. For properties: SQL databases emphasizes on ACID properties ( Atomicity, Consistency, Isolation and Durability) whereas the NoSQL database follows the Brewers CAP theorem ( Consistency, Availability and Partition tolerance )

9. For support: Excellent support are available for all SQL database from their vendors. There are also lot of independent consultations who can help you with SQL database for a very large scale deployments. For some NoSQL database you still have to rely on community support, and only limited outside experts are available for you to setup and deploy your large scale NoSQL deployments.

## Simplified Data Modeling

### Data Modeling – Table Elements

The Table Name, which is located at the top of the table.

The Primary Keys, the primary keys uniquely identify each row in a table.

Table Columns – There can be one or more table columns.

Foreign Key – This is a column or set of columns which match a primary key in another table.

### Data Modeling – Table Relationships

- one-to-many relationship: n entry in one table can be related to more than one entry in another.

- A many-to-one relationship is similar to a one-to-many relationship, but in reverse.

- zero or one-to-one

