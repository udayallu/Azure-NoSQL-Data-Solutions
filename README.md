# Azure-NoSQL-Data-Solutions
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
![alt text](https://github.com/udayallu/Azure-NoSQL-Data-Solutions-/blob/master/images/img1.PNG)


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

![alt text](https://github.com/udayallu/Azure-NoSQL-Data-Solutions-/blob/master/images/img1.PNG)
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

![alt text](https://github.com/udayallu/Azure-NoSQL-Data-Solutions-/blob/master/images/img3.PNG)
## Azure Storage Tables

- The Azure Storage Table service provides a non-relational database option for storage in Azure.
- Storage Tables offer a mechanism to store loosely structured data that is automatically partitioned on a pre-defined key.
![alt text](https://github.com/udayallu/Azure-NoSQL-Data-Solutions-/blob/master/images/img4.PNG)
![alt text](https://github.com/udayallu/Azure-NoSQL-Data-Solutions-/blob/master/images/img5.PNG)

## Initializing Azure Storage Tables
- To **create** an Azure Storage Table instance, you must first create an Azure Storage account. All Storage Table instance must be created within an Azure Storage account.
- For example, you may create an Azure Storage account named schooldata. The URI for this Azure Storage Account would be:
```
http://schooldata.[name of service].core.windows.net/
```
- If you would like to create a Table instance, you can either use an SDK, command-line interface or other tool to create a Table instance within the schooldata Storage account.

- Any tool you use would inevitably use the Azure Storage REST API to perform the specific actions. Specifically, creating a Storage Table instance would require a HTTP request using the POST method against the following URI:
```
http://schooldata.table.core.windows.net/Tables
```
- The request must include a body specifying the name of the table:
```
{
  "TableName": "classrooms"
}
```

## Installing Azure CLI 2.0

## Steps

1. First, you must ensure that you have Python 3.5 installed on your local machine.

2. If you are using a Linux distribution, you should install specific prerequisites listed as this link: https://docs.microsoft.com/en-us/cli/azure/install-azure-cli.

3. Open the command-line interface application for your operating system:
- Windows: Command Prompt
- Mac/Linux: Terminal
- Note: Leave the application open for the remainder of this lab as you will be using it to manage your resources.
- Linux and OSX: Install the CLI using the following curl command:
```
curl -L https://aka.ms/InstallAzureCli | bash
```
Restart your command-line interface application for the changes to take effect.

4. Windows: Install the CLI using the pip tool.
```
pip install --user azure-cli
```

## Login in to the cli and creating the table ( use power shell in windows)
1. Use the following command to validate that the Azure CLI 2.0 tool is installed. You should see a description of potential commands:
```
az --help
```
2. Use the interactive **login** to log in to Azure using your enterprise credentials or Microsoft account identity:
```
az login
```
![alt text](https://github.com/udayallu/Azure-NoSQL-Data-Solutions-/blob/master/images/img6.PNG)
3. Open a browser and navigate to **https://aka.ms/devicelogin** . The command prompt will display a device code that you can use to authenticate to Azure.
![alt text](https://github.com/udayallu/Azure-NoSQL-Data-Solutions-/blob/master/images/img7.PNG)
4. Once you enter the code, you will be prompted to allow access to the Microsoft Azure CLI. Click Continue.
![alt text](https://github.com/udayallu/Azure-NoSQL-Data-Solutions-/blob/master/images/img8.PNG)
5. Sign in using your identity associated with your Azure subscription.
6. Once you receive confirmation that you are signed in, you can close your browser window.

### Creating the Tables
1. connecting to the storage account
```
az storage account show -g UdayAlluRes -n udaydatastorage
```
![alt text](https://github.com/udayallu/Azure-NoSQL-Data-Solutions-/blob/master/images/img8.PNG)
2. saving the connection string to the environment varaible
```
$env:AZURE_STORAGE_CONNECTION_STRING = $(az storage account show-connection-string -g UdayAlluRes -n udaydatastorage)
```
![alt text](https://github.com/udayallu/Azure-NoSQL-Data-Solutions-/blob/master/images/img9.PNG)
3. Creating a table called **DemoTable**
```
az storage table create -n DemoTable
```
![alt text](https://github.com/udayallu/Azure-NoSQL-Data-Solutions-/blob/master/images/img10.PNG)
4.  Inserting the Data into the created table
```
az storage entity insert -t DemoTable -e PartitionKey=Students RowKey=asimpson
Age=12 Grade=4
```
![alt text](https://github.com/udayallu/Azure-NoSQL-Data-Solutions-/blob/master/images/img11.PNG)
5. Inserting new partition teacher
```
az storage entity insert -t DemoTable -e PartitionKey=Teachers RowKey=gwilliam Age=31
```
![alt text](https://github.com/udayallu/Azure-NoSQL-Data-Solutions-/blob/master/images/img12.PNG)
6. Checking the Table
```
az storage entity query -t DemoTable
```
![alt text](https://github.com/udayallu/Azure-NoSQL-Data-Solutions-/blob/master/images/img13.PNG)
7. Filter 1
```
az storage entity query -t DemoTable --filter "Age gt 25"
```
![alt text](https://github.com/udayallu/Azure-NoSQL-Data-Solutions-/blob/master/images/img14.PNG)
8. Filter 2
```
az storage entity query -t DemoTable --filter "PartitionKey eq 'Students'"
```
![alt text](https://github.com/udayallu/Azure-NoSQL-Data-Solutions-/blob/master/images/img15.PNG)

## Flexible Schema
- Entities are truly only stored as a collection of key-value pairs. This means that two entities in the same table do not necessarily need to share the same schema. In a basic table, you could have two entities like these examples:

- For example, we have an entity that represents a student. In this Storage Table instance, students are partitioned by the school they attend and the row key is their student ID. This student entity only starts with a key-value pair for the First Name and Last Name fields:
![alt text](https://github.com/udayallu/Azure-NoSQL-Data-Solutions-/blob/master/images/img16.PNG)

- Let's assume that you need to update this entity. For this entity, you have discovered that the Storage account is named cornfielddistrict and the table is named students. You need to update the student to a new age of 12. You also need to add a key-value pair indicating that the student now plays Tennis as her sport of choice.

- Your updated entity will now look like this:\
![alt text](https://github.com/udayallu/Azure-NoSQL-Data-Solutions-/blob/master/images/img17.PNG)

### Partitions
- In the context of the Table service, Tables are sets of entities that are related but do not necessarily share the same schema. Each table has a Sharding pattern1 implementation (called partitions) where data in the same partition will be stored on the same server.

- This pattern ensures that data in the same partition can be accessed very quickly. Inversely, data across partitions typically is accessed in a much slower manner that can be resource-expensive to your application.

Let's look at the following logical structure:
![alt text](https://github.com/udayallu/Azure-NoSQL-Data-Solutions-/blob/master/images/img18.PNG)

Partitions in Storage Tables

- In this very basic example, you can see that each partition is stored on a separate physical server. A query that would return both the poster and wallpaper entities would be slow because it would most likely be performed over multiple servers. With this information, we can inversely infer that queries over multiple entities within the same partition would be order of magnitudes faster than an entity across multiple partitions.
## JSON Serialization
- [Query Entities](https://docs.microsoft.com/en-us/rest/api/storageservices/query-entities)
- [Insert Entities](https://docs.microsoft.com/en-us/rest/api/storageservices/fileservices/insert-entity)
- [Table Service JSON Payload Types](https://docs.microsoft.com/en-us/rest/api/storageservices/payload-format-for-table-service-operations)

## RESTful API for CRUD Operations
### RESTful API for CRUD Operations
- Storage Tables offer a set of transactional functionality that mirrors the traditional Create, Read, Update, Delete (CRUD) methods found in many other data sources.
- Because of the CRUD model, you can use dedicated client libraries or REST API endpoints with HTTP methods to access and modify entities.
![alt text](https://github.com/udayallu/Azure-NoSQL-Data-Solutions-/blob/master/images/img19.PNG)

## Modifying Entities
- When entities are modified, only key-value pairs that are specified in the body of the HTTP request are modified (either created or updated). Existing key-value pairs are not lost.

- Let's return to an example from earlier in this module. To refresh, we have an entity that represents a student. In this Storage Table instance, students are partitioned by the school they attend and the row key is their student ID. This student entity only starts with a key-value pair for the First Name and Last Name fields:

![alt text](https://github.com/udayallu/Azure-NoSQL-Data-Solutions-/blob/master/images/img20.PNG)
Let's assume that you need to update this entity. For this entity, you have discovered that the Storage account is named cornfielddistrict and the table is named students. You need to update the student to a new age of 12. You also need to add a key-value pair indicating that the student now plays Tennis as her sport of choice.

- To accomplish this, you would use the following URL and JSON payload:

- PUT: https://cornfielddistrict.table.core.windows.net/students(appleorchardmiddle, 237548902)

JSON Payload
```
"Age": 12,
  "Sport": "Tennis"
```

![alt text](https://github.com/udayallu/Azure-NoSQL-Data-Solutions-/blob/master/images/img21.PNG)

## OData Queries
- Table Storage entities can also be accessed by using the OData protocol. The OData protocol provides a uniform way to query any data using an HTTP endpoint.
- Traditionally in a RESTful service, the GET endpoint can only return either a specific item or all items. OData solves this by offering a query syntax that allows you to search for a single item or set of items from a collection using familiar a**HTTP GET** requests.
- OData query parameters also allow you to filter, paginate, or project the result of your requests.
-With Storage tables, you can use OData as an easy way to search for particular entities in a table. Parameters such as the filter * ,*top and $select are supported. Results can be returned in either the AtomPub1 or JSON2 format. Formats are specified by including an Accept header in your request.
- **Note**: JSON is the most common format. Typically, JSON data provides up to a 70% reduction in bandwidth compared to XML-based 
formats.
- If you require a specific entity, the OData protocol provides a mechanism where you can retrieve a single entity in a collection by using the following URL format:

- https://[base url]/resource
- Storage tables deviate from the typical OData protocol by requiring you to specify both the row and partition keys. These form a composite index for an entity in Storage Tables:

- https://[account].table.core.windows.net/table
![alt text](https://github.com/udayallu/Azure-NoSQL-Data-Solutions-/blob/master/images/img22.PNG)

## .NET Core and Azure Storage

### Project.Json
```
{
  "version": "1.0.0-*",
  "buildOptions": {
    "debugType": "portable",
    "emitEntryPoint": true
  },
  "dependencies": {
    "WindowsAzure.Storage": "8.1.0"
  },
  "frameworks": {
    "netcoreapp1.0": {
      "dependencies": {
        "Microsoft.NETCore.App": {
          "type": "platform",
          "version": "1.0.0"
        }
      },
      "imports": "dnxcore50"
    }
  }
}
```

### Program.cs
```
using System;
using System.Threading.Tasks;
using Microsoft.WindowsAzure.Storage;
using Microsoft.WindowsAzure.Storage.Table;

namespace ConsoleApplication
{
    public class Program
    {
        public static void Main(string[] args)
        {
            GetStorageData().Wait();
        }

        public static async Task GetStorageData()
        {
            var account = CloudStorageAccount.Parse("[connection string]");

            var client = account.CreateCloudTableClient();

            var table = client.GetTableReference("people");
            await table.CreateIfNotExistsAsync();

            var condition = TableQuery.GenerateFilterCondition("PartitionKey", QueryComparisons.Equal, "Doe");
            var query = new TableQuery<PersonEntity>().Where(condition);

            TableContinuationToken token = null;
            do
            {
                var segment = await table.ExecuteQuerySegmentedAsync(query, token);
                token = segment.ContinuationToken;
                foreach(var entity in segment)
                {
                    Console.WriteLine($"{entity.RowKey} {entity.PartitionKey} [Age: {entity.Age} | IsRetired: {entity.IsRetired} | Hometown: {entity.Hometown}]");
                }
            }
            while (token != null);
        }

        public class PersonEntity : TableEntity
        {
            public PersonEntity(string lastName, string firstName)
            {
                this.PartitionKey = lastName;
                this.RowKey = firstName;
            }

            public PersonEntity() { }

            public int Age { get; set; }

            public bool? IsRetired { get; set; }

            public string Hometown { get; set; }
        }
    }
}
```
