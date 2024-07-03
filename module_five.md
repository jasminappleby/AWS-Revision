# Module 5

## Instance Stores and Amazon Elastic Book Store (Amazon ESB)

### Instance Stores
Block-level storage volumes behave like physical harddrives.

An instance store provices temporary block-level storage for an EC2 instance.
An instance store is disk storage that is physically attach to the host computer for an EC2 instance, and therefore has the same lifespace as the instance. When the instance is terminated, you lose any data in the instance store. 

1. An EC2 instance with an attach instance store is running
2. The instance is stopped or terminated
3. All data on the attached instance store is deleted

### Amazon Elastic Block Storage (Amazon EBS)
Amazon Elastic Block Store* is a service that provides block-level storage volumes that you can use with Amazon EC2 instances.
If you stop or terminate an Amazon EC2 instance, all the data on the attached EBS volume remains available.

To create an EBS volume, you define the configuration (such as volume size and type) and provision it. 
After you create an ESB volume, it can attach to an Amazon EC2 instance.

Because EBS volumes are for data that needs to persist, it is important to back up the data.
You can take incremental backups of ESB volumes by creating Amazon ESB snapshots.

### Amazon ESB Snapshots
An EBS snapshot is an incremental backup. This means that the first backup taken of a volume copies all the data.
For subsequent backups, only the blocks of data that have changed since the most recent snapshots are saved.

Incremental backups ae different from full backups, in which all the data in a storage volume copies each time a backup occurs.
The full backip includes data that has not changed since the most recent backup.

## Amazon Simple Storage Service (Amazon S3)

### Object Storage
In object storage, each object consists of data, metadata and a key. 

- The data might be an image, video, text document, or any other type of file. 
- Metadata contains information about what the data is, how it is used, the object size, and so on.
- An object's key is its unique indentifier.

Recall that when you modify a file in block storage, only the pieves that are changes are updated.
when a file in object storage is modified, the entire object is updated.

### Amazon Simple Storage Service (S3)
Amazon S3 is a service that provides object-level storage. 
Amazon S3 stores data as objects in buckets.

You can upload any type of file to Amazon S3, such as images, videos, text files, and so on. 
You might use Amazon S3 to store backup files, media files for a website, or archived documents.
Amazon S3 offers unlimited storage space. The maximum file size for an object in Amazon S3 is 5TB.

When you upload a file to Amazon S3, you can set permissions to control visibility and access to it.
You can also use the Amazon S3 versioning feature to track changes to your object over time.

### Amazon S3 Storage Classes
With Amazon S3, you pay only for what you use.
You can chose from a range of storage classes to select a fit for your business and cost needs. 
When selecting an Amazon S3 storage class, consider these two factors:

- How often you plan to retrieve your data
- How available you need your data to be
- Amazon S3 Standard Designed for frequently accessed data
- Stores data in a minimum of three Availablity Zones

Amazon S3 Standard provides high availability for objects. 
This makes it a good choice for a wide range of use cases, such as websites, content distribution and data analytics.

Amazon S3 Standard has a higher cost than other storage classes intended for infrequently accessed data and archival storage.

### Amazon S3 Standard-Infrequent Access (S3 Standard-IA)
Ideal for   accessed data.
Similar to Amazon S3 Standard but has a lower storage price and a higher retrieval price.

Amazon S3 Standard-IA is ideal for data infrequently accessed but requires high availability when needed.
Both Amazon S3 Standard and Amazon S3 Standard-IA store data in a minimum of three Availability Zones.
S3 Standard-IA provides the same level of availability as Amazon S3 Stanfdard but with a lower storage price and a higher retrieval price.

### Amazon S3 One Zone-Infrequent Access (S3 One Zone-IA)
Stores data in a single Availability Zone.
Has a lower storage price than Amazon S3 Standard-IA

Compared to Amazon S3 Standard and Amazon S3 Standard-IA, which store data in a minimum of three Availability Zones, Amazon S3 One Zone-IA stores data in a single Availability Zone.
This makes it a good storage class to consider if the following conditions apply:

- You want to save costs on storage.
- You can easily reproduce your data in the event of an Availability Zone failure. 
- Amazon S3 Intelligent-Tiering Ideal for data with unknown or changing access patterns. 
- Requires a small monthly monitoring and automation fee per object.

In the Amazon S3 Intelligent-Tiering storage class, Amazon S3 monitors objects' access patterns.
If you haven't accessed an object for 30 consecutive days, Amazon S3 automatically moves it to the infrequent access tier, Amazoon S3 Standard-IA.
If you access an object in the infrequent access tier, Amazon S3 Standard.

### Amazon S3 Glacier Instant Retrieval
Works well for archived data that requires immediate access.
Can retrieve objects within a few milliseconds. 

When you decide between the options for archival storage, consider how quickly you must retrieve the archived objects. You can retrieve objects stored in the Amazon S3 Glacier Instant Retrieval storage class within milliseconds, with the same performance as Amazon S3 Standard.

### Amazon S3 Glacier Flexible Retrieval
Low-cost storage designed for data archiving.
Able to retrieve objects within a few minutes to hours.
An example, you might use this storage class to store archived customer records or older photos and video files.

### Amazon S3 Glacier Deep Archive
Lowest-cost object storage class ideal for archiving.
Able to retrieve objects within 12 hours.
Supports long-term retention and digital preservation for data that might be accessed once or twice in a year.
This storage class is the lowest-cost storage in AWS Cloud, with data retrieval from 12 to 48 hours. 
All objects from this storage class are replicated and stored across at least three graphically dispersed Availability Zone.

### Amazon S3 Outposts
Creates S3 buckets on Amazon S3 Outputs.
Makes it easier to retrieve, store, and access data on AWS Outputs.
Delivers object storage to your on-premise AWS Outposts environment. 
Amazon S3 Outputs is designed to store data durably and redundantly acress multiple devices and servers on your Outposts.
It works well for workloads with local data residency requirements that must satify demanding performance needs by keeping data close to on-premise applications.


## Amazon Elastic File System (Amazon EFS) 

### File Storage
In file storage, multiple clients (such as user, applications, servers, and so on) can access data that is stored in shared file folders.
In this approach, a storage server uses block storage with a local file system to organise files.
Clients access data through file paths.

Compared to block storage and object storage, file storage is ideal for use cases in which a large number of services and resources need to access the same data at the same time. 

### Amazon EFS
A scalable file system used with AWS Cloud services and on-premises resources. 
As you add and remove files, Amazon EFS grows and shrinks automatically.
It can scale on demand to petabytes without distrupting applications.

### Comparing Amazon EBS and Amazon EFS

#### Amazon EBS
An Amazon EBS volume stores data in a single Availability Zone.
To attach an Amazon EC2 instance to an EBS volume, both the Amazon EC2 instance and the EBS volume must reside within the same Availability Zone.

#### Amazon EFS
Amazon EFS is a regional service. It stores data in and across multiple Availability Zones.
The duplicate storage enables you to access data concurrently from all the Availability Zones in the Region where a file system is located.
Additionally, on-premise servers can access Amazon EFS using AWS Direct Connect.


## Amazon Relational Database Service (Amazon RDS)
In relational databases, data is stored in a way that relates it to other pieces of data.

An example of relational database might be a coffee shops inventory management system.
Each record in the database would include data for a single item, such as product name, size, price and so on.

Relational databases use structured query language (SQL) to store and query data. 
This approach allows data to be stored in an easily understandable, consistent, and scalable way.
For example, the coffee shop owners can write a SQL query to identify all the customers whose most frequently purchased drink is a medium latte.

Example of a relational database:

| ID |Product Name|Size|Price|
|:---|:-----------|:---|:----|
|1|Medium Roast Ground Coffee|12 Oz.|£3.30|
|2|Dark Roast Ground Coffee|20 Oz.|£9.27|


## Amazon Relational Database Service (Amazon RDS)
In relational databases, data is stored in a way that relates it to other pieces of data.

An example of relational database might be a coffee shops inventory management system.
Each record in the database would include data for a single item, such as product name, size, price and so on.

Relational databases use structured query language (SQL) to store and query data. 
This approach allows data to be stored in an easily understandable, consistent, and scalable way.
For example, the coffee shop owners can write a SQL query to identify all the customers whose most frequently purchased drink is a medium latte.

Example of a relational database:

| ID |Product Name|Size|Price|
|:---|:-----------|:---|:----|
|1|Medium Roast Ground Coffee|12 Oz.|£3.30|
|2|Dark Roast Ground Coffee|20 Oz.|£9.27|

### Amazon Relational Database Service (RDS)
RDS is a service that enables you to run relational database in the AWS Cloud. 
RDS is a managed service that automates tasks such as hardware provisioning, database setup, patching, and backups.
With these capabilities, you can spend less time completing administrative tasks and more time using data to innovate your applications.

Amazon RDS is a managed service that automates tasks such as hardware provisioning, database setup, patching and backups.
With these capabilities, you can spend less time completing administractive tasks and more time using data to innovate your applications. 
You can integrate Amazon RDS with other services to fulfill your business and operational needs, such as using AWS Lambda to query your database from a serverless application.

Amazon RDS provides a number of different security options. Many Amazon RDS database engines offer encryption at rest (protecting data while it is stored) and encryption in transit (protecting data while it is being sent and received).

### Amazon RDS Database Engines
Amazon RDS is available on six database engines, which optimise for memory, performance, or input/output (I/O).

Supported database engines include:
- Amazon Aurora
- PostgreSQL
- MySQL
- MariaDB
- Oracle Database
- Microsoft SQL Server

## Amazon Aurora
Amazon Aurora is an enterprise-class relational database. It is compatible with MySQL and PostgreSQL relational database. It is up to five times faster than standard MySQL database and up to three times faster than standard PostgreSQL databases.

Amazon Aurora helps to reduce your database costs by reducing unnecessary input/output (I/O) operations, while ensuring that your database resources remain reliable and available. 

Consider Amazon Aurora if your workloads require high availability. It replicates six copies of your data across three Availability Zones and continuously backs up your data to Amazon S3.



## Amazon DynamoDB
- Nonrelational Database
- Serverless
- Automatic Scaling

#### Nonrelational Database
In a nonrelational database, you create tables. A table is a place where you can store and query data.
Is a key-value database service. It delivers single-digit millisecond performance at any scale.

Nonrelational databases are sometimes referred to as "NoSQL databases" because they use structures other than rows and columns to organise data. 
One type of structural approach for nonrelational databases is key-value pairs.
With key-value pairs, data is organised into items (keys), and items have attributes (values). you can think of attributes as being different features of your data. 

In a key-value database, you can add or remove attributes from items in the table at any time. Additionally, not every item in the table has to have the same attributes.

Examples of data in a nonrelational database:

|Key|Value|
|:---|:---|
|1|Name: John Doe|
||Address: 123 Any Street|
||Fave Drink: Vanilla Latte|
|:---|:---|
|2|Name: Mary Major|
||Address: 100 Main Street|
||Bday: 26/06/2000|

#### Serverless 
DynamoDB is serverless, which means that you do not have to provision, patch or manage servers.
You also do not have to install, maintain, or operate software. 

#### Automatic Scaling
As the suze of your database shrinks or gorws, DynamoDB automatically scales to adjust for changes in capacity while maintaining consistent performance.

This makes it suitable choice for use cases that require high performance while scaling. 

## Amazon Redshift
Amazon Redshift is a data warehousing service that you can use for big data analytics. It offers the ability to collect data from many sources and help you to understand relationships and trends across your data. 

## Amazon Database Migration Service (AWS DMS)
AWS Database Migration Service (AWS DMS) enables you to migrate relational database, nonrelational databases and other types of data stores. Using AWS DMS, you could migrate your data to a target database, such as an Amazon Aurora database. 

Other use cases for AWS DMS: 

### Development and test database migrations. 
Enabling developers to test applications against affecting production users.

### Database Consolidation
Combining several databases into a single database.

### Continuous replication
Sending ongoing copies of your data to other target sources instead of doing a one-time migration. 

## Additional Database Service

### Amazon DocumentDB
Amazon DocumentDB is a document database service that supports MongoDB workloads. (MongoDB is a document database program.)

### Amazon Neptune
Amazon Neptune is a graph database service.
You can use Amazon Neptune to build and run applications that work with highly connected datasets, such as recommendation engines, fraud detection, and knowledge graphs.

### Amazon Quantum Ledger Database (Amazon QLDB)
Amazon Quantum Ledger Database is a ledger database service.
You can use Amazon QLDB to review a complete history of all the channges that have been made to your application data.

### Amazon Managed Blockchain
Amazon Managed Blockchain is a service that you can use to create and managed blockchain networks with open-source frameworks.
Blockchain is a distributed ledger system that lets multiple parties run transactions and share data without a central authority.

### Amazon ElastiCache
Amazon ElastiCache is a service that adds caching layers on top of your databases to help improve the read times of common requests.
It supports two types of data stores: Redis and Memcached.

### Amazon DynamoDB Accelerator
Amazon DynamoDB Accelerator (DAX) is an in-memory cache for DynamoDB. 
It helps improve response times from single-digit milliseconds to microseconds. 








































