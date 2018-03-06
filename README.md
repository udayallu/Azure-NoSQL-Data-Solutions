# Azure-NoSQL-Data-Solutions-
will explore NoSQL technologies available to you both on-premise in Azure

## Introducing NoSQL Solutions in Azure:
In this module, we will introduce the concept of NoSQL at a very high level. Specifically, we will look at the value proposition behind NoSQL, and we’ll provide an overview of Azure Cosmos DB.

1. **Azure Storage Tables**: his module introduces the Azure Storage service and it’s Table storage component.

2. **Azure Cosmos DB**: We look at the SQL API in this module, an API in Azure Comos DB made for storing JSON documents.

3. **MongoDB**: This module is an introduction to the MongoDB and how it can be used with IaaS in Microsoft Azure.

4. **More NoSQL Database Solutions**: To wrap things up, this module covers many other NoSQL solutions that are available in Azure including:

- Cassandra
- Lucene & Solr
- Azure Search
- HBase
- Redis

## What is NoSQL?
- NoSQL is a name given to a category of databases that defy traditional relational database paradigms in favor of new features and practices that are optimized for data in the modern world.

- NoSQL databases focus on **performance** over **consistency** by doing things such as: - Allowing data to have a structure without enforcing the structure through a Schemas - Allow data to be replicated across many nodes asynchronously.

- These focus areas allow NoSQL databases to read, query and write data at speeds that were previously unattainable. They also allow NoSQL databases to be resilient across various nodes and geographies.
1. Simple replication support
2. Schema less
3. Designed to be distributed
4. Non relational

## How is NoSQL Different than Relational Databases?
- Relational Database Management Systems (RDBMS or relational databases) have been in widespread use throughout many different applications over the years.
#### Typically, but not in all cases, relational databases take advantage of two key features:
1. **Schemas**: Schemas allow you to control the data coming into a database and validate the data. A schema can validate that certain fields are included when a new record is created, manage the data type of field and ensure that data is structured in an intelligible way for your application workloads.

2. **Relationships**: Relationships allows you to enforce connections between various data sets. Using a relationship you can associate records from one table to another and create constraints that force operations on either table to account for the existing relationship.

- NoSQL databases shift the burden of Schemas and Relationships to the application-tier of your solution. If your application requires relationships and well-structured data, it would need to be implemented in your application's code as opposed to the database level.
- NoSQL databases also can create inferred relationships by nesting records (many times referred to as documents in NoSQL). For example, a parent document could have a child document nested directly within it. Many NoSQL query engines (like Azure Cosmos DB and MongoDB) natively support the ability to perform aggregation, queries and joins based on complex, nested documents.

## Types of NoSQL Databases

### Types of NoSQL Databases
NoSQL is an entire category of databases instead of simply a single type. Within this category, there are many types of databases. Some of the databases in this course will fall into the following categories:

### Key-Value Stores
A key-value store is a special type of NoSQL Database that stores data as collections of key-value pairs. Key-value stores are popular because they are considered the simplest to implement among NoSQL stores. They are the foundation behind many NoSQL databases and the store type shares a lot of basic features with other NoSQL store types.

### Document Stores
A Document-based NoSQL store is a special type of database that extends the functionality found in a typical key-value NoSQL store. In a key-value store, you are primarily restricted to making queries based on the key with the value of each entity remaining opaque. In a document store, you can perform operations and queries based on the keys or values.

### Column Stores
Relational databases often store data in a row-oriented fashion by including relevant "row" data together. Column stores are similar to relational-databases but they store data in a column-oriented fashion. Queries that perform operations on the same column across many items will see a performance increase with this type of database.

## NoSQL Services in Azure
Azure is home to many different NoSQL database services. Here are some of the services we will cover in this course:

1. **Storage Tables**: The Azure Storage service offers highly available storage that can be scaled to massive levels. Within the Storage service, there is a Tables feature that allows you to create NoSQL entities within a key-value store.

2. **Azure Cosmos DB**: Azure Cosmos DB is an Azure-native database service that focuses on providing a high-performance database regardless of your selected API or data model. Azure Cosmos DB offers multiple APIs and models that can be used interchangably for various application scenarios.

3. **Redis Cache**: Redis Cache is an implementation of the Redis Database engine that is offered as a service on Azure. Using the Redis Cache service, one could create a cache instance quickly using the key-value based store.

## Hosting NoSQL on Azure IaaS
While there are many NoSQL Azure services, it is just as important to remember that you can host your own NoSQL database solutions easily using Azure infrastructure. This supports many common scenarios such as:

1. Installing MongoDB on a Linux Virtual Machine.

2. Creating a cluster of search-engine shards using Lucene & Solr.

3. Implementing a Hadoop workload on Windows Machines using HDInsight.

4. Creating a Cassandra cluster on Linux Virtual Machines.

## JSON Documents in Azure SQL Database
Before we dig into the NoSQL services available in Azure, the Azure SQL Database service (along with SQL Server Standalone) has a new feature that allows you to store, modify and query data using JSON.

- The new JSON functionality in Azure SQL Database allows you to:

- Read and store JSON text using a special JSON data type.

- Convert JSON into a relational data format.

- Import existing JSON data into a relational table.

- Query a relational table using JSON in the query language.

- Query a column with JSON text directly using JSON in the query language.

- Format the results of a query as JSON.

```
SELECT TOP(1)
    CustomerID AS "id",
    FirstName AS "first",
    LastName AS "last",
    CompanyName AS "company"
FROM SalesLT.Customer
FOR JSON AUTO
```

So I'd like to create some type of contact object and also a root object

```

{
    "Customers": [
        {
            "id": 1,
            "name": {
                "first": "Orlando",
                "last": "Gee"
            },
            "company": "A Bike Store",
            "contact": {
                "email": "orlando0@adventure-works.com",
                "phone": "245-555-0173"
            }
        }
    ]
}

```
## Azure Storage

- In Azure, the base service for data storage is called Azure Storage (or simply Storage). Storage is the foundational service that supports all of the other Azure services. Storage was designed to make it possible for developers to build large-scale applications by providing a storage mechanism that automatically scales to handle various application[s]’ workloads.

- Storage, to put simply, is massively scalable and available to use as a service with minimal configuration.
- Storage partitions your assets, media and data automatically across partitions. All new data you add is automatically partitioned and load balanced without manual intervention. As your application grows, Storage can automatically allocate the correct quantity of partitions to scale and meet growing resource requirements.
## Types of Storage
The Storage service in Azure is composed of four primary types of storage data:
### Blob
Storage blobs provide a way to store files so that they can be consumed by other components of your application or client devices. These blobs represent files and can be protected such that tokens are required to access the blob.

### Table
The Table service is a NoSQL store that is based on the document paradigm. Each entity consists of a partition key and a row key that together form a unique index. The entities then contain a collection of key-value pairs for the document’s attributes.

### File
File is a service that publishes a Server Message Block (SMB) 2.1 endpoint. This endpoint can be used by virtual machines in Azure in the same way as a shared drive.

### Queue
Storage queues are externally managed queues that can persist requests to be consumed by modules in your application. The queue is implemented in a traditional first in, first out (FIFO) pattern. These queues can be measured and requests can also be reviewed (peek) without removing them from the queue.

## Key-Value NoSQL Stores
A key-value store is a special type of NoSQL Database that stores data as collections of key-value pairs:
- Key-value stores are popular because they are considered the simplest to implement among NoSQL stores. 
- They are the foundation behind many NoSQL databases and the store type shares a lot of basic features with other NoSQL store types. Key-Value stores are also simple to sort using their keys.
- At a lower level, a collection in a key-value store is composed of multiple key-value pairs. Each collection of key-value pairs is sometimes referred to as an entity. In the example below, the collection of key-value pairs compose a single entity:

## Azure Storage Tables

- The Azure Storage Table service provides a non-relational database option for storage in Azure.
- Storage Tables offer a mechanism to store loosely structured data that is automatically partitioned on a pre-defined key.\

