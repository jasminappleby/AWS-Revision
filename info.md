
Amazon RDS is a managed service that automates tasks such as hardware provisioning, database setup, patching, and backups. With these capabilities, you can spend less time completing administrative tasks and more time using data to innovate your applications. You can integrate Amazon RDS with other services to fulfill your business and operational needs, such as using AWS Lambda to query your database from a serverless application.

Amazon RDS provides a number of different security options. Many Amazon RDS database engines offer encryption at rest (protecting data while it is stored) and encryption in transit (protecting data while it is being sent and received).

Amazon RDS database engines
Amazon RDS is available on six database engines, which optimize for memory, performance, or input/output (I/O). Supported database engines include:

Amazon Aurora

PostgreSQL

MySQL

MariaDB

Oracle Database

Microsoft SQL Server

Amazon Aurora
Amazon Aurora
 is an enterprise-class relational database. It is compatible with MySQL and PostgreSQL relational databases. It is up to five times faster than standard MySQL databases and up to three times faster than standard PostgreSQL databases.

Amazon Aurora helps to reduce your database costs by reducing unnecessary input/output (I/O) operations, while ensuring that your database resources remain reliable and available. 

Consider Amazon Aurora if your workloads require high availability. It replicates six copies of your data across three Availability Zones and continuously backs up your data to Amazon S3.










Amazon DynamoDB
Nonrelational Databases
In a nonrelational database, you create tables. A table is a place where you can store and query data.

Nonrelational databases are sometimes referred to as “NoSQL databases” because they use structures other than rows and columns to organize data. One type of structural approach for nonrelational databases is key-value pairs. With key-value pairs, data is organized into items (keys), and items have attributes (values). You can think of attributes as being different features of your data.

In a key-value database, you can add or remove attributes from items in the table at any time. Additionally, not every item in the table has to have the same attributes. 

Example of data in a nonrelational database:


Key

Value

1


Name: John Doe

Address: 123 Any Street

Favorite drink: Medium latte

2


Name: Mary Major

Address: 100 Main Street

Birthday: July 5, 1994


Amazon DynamoDB
Amazon DynamoDB
 is a key-value database service. It delivers single-digit millisecond performance at any scale.

Serverless

DynamoDB is serverless, which means that you do not have to provision, patch, or manage servers. 

You also do not have to install, maintain, or operate software.

Automatic Scaling

As the size of your database shrinks or grows, DynamoDB automatically scales to adjust for changes in capacity while maintaining consistent performance. 

This makes it a suitable choice for use cases that require high performance while scaling.












Amazon Redshift
Amazon Redshift
 is a data warehousing service that you can use for big data analytics. It offers the ability to collect data from many sources and helps you to understand relationships and trends across your data.








AWS Database Migration Service (AWS DMS)
AWS Database Migration Service (AWS DMS)
 enables you to migrate relational databases, nonrelational databases, and other types of data stores.

With AWS DMS, you move data between a source database and a target database. 
The source and target databases
 can be of the same type or different types. During the migration, your source database remains operational, reducing downtime for any applications that rely on the database. 

For example, suppose that you have a MySQL database that is stored on premises in an Amazon EC2 instance or in Amazon RDS. Consider the MySQL database to be your source database. Using AWS DMS, you could migrate your data to a target database, such as an Amazon Aurora database.

Other use cases for AWS DMS
Development and test database migrations

Enabling developers to test applications against production data without affecting production users

Database consolidation

Combining several databases into a single database

Continuous replication

Sending ongoing copies of your data to other target sources instead of doing a one-time migration












Additional Database Services
Amazon DocumentDB
Amazon DocumentDB
 is a document database service that supports MongoDB workloads. (MongoDB is a document database program.)

Amazon Neptune
Amazon Neptune
 is a graph database service. 

You can use Amazon Neptune to build and run applications that work with highly connected datasets, such as recommendation engines, fraud detection, and knowledge graphs.

Amazon Quantum Ledger Database (Amazon QLDB) 
Amazon Quantum Ledger Database (Amazon QLDB)
 is a ledger database service. 

You can use Amazon QLDB to review a complete history of all the changes that have been made to your application data.

Amazon Managed Blockchain
Amazon Managed Blockchain
 is a service that you can use to create and manage blockchain networks with open-source frameworks. 

Blockchain is a distributed ledger system that lets multiple parties run transactions and share data without a central authority.

Amazon ElastiCache
Amazon ElastiCache
 is a service that adds caching layers on top of your databases to help improve the read times of common requests. 

It supports two types of data stores: Redis and Memcached.

Amazon DynamoDB Accelerator
Amazon DynamoDB Accelerator (DAX)
 is an in-memory cache for DynamoDB. 

It helps improve response times from single-digit milliseconds to microseconds.










Course Updates
Module 5 contains an update to the Amazon Simple Storage Service (Amazon S3) reading content. As part of this update, the article lists the following new storage classes:

Amazon S3 Glacier Instant Retrieval

Amazon S3 Glacier Flexible Retrieval (previously known as Amazon S3 Glacier)

Amazon S3 Outposts
