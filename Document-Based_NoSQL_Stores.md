# Document-Based NoSQL Stores
- A Document-based NoSQL store is a special type of database that extends the functionality found in a typical key-value NoSQL store.
-  In a document store, you can perform operations and queries based on the keys or values
-  Each item in the database is itself a collection of key-value pairs.
- This collection is essentially referred to as a "document" and it can be queried or modified in an interactive manner.
- Documents can have child documents embedded directly within them.
- These embedded documents can also be queries in the same manner.\

## Azure Cosmos DB
- Azure Cosmos DB is Microsoft's new globally distributed, multi-model database service.
- Azure Cosmos DB offers a turn-key database service that allows you to create a database and distribute the data globally so that the data users access or in datacenters closer to them.

#### The JSON documents stored in Azure Cosmos DB are managed through a well-defined hierarchy of database resources. These resources are automatically replicated to ensure that they are highly available while still allowing you to address each resource using a unique URI.
- The basic hierarchy structure is detailed in the following diagram:

## Getting Started: Creating an Azure Cosmos DB Instance
Important: Prior to getting starting with the hands-on exercises in this module, you should first complete this exercise. The data instances you create in this exercise will be used for subsequent exercises in this module.

1. In a new window, sign in to the Azure Portal **(http://portal.azure.com)**.

2. In the Jumpbar, click New, click **Databases**, and then click **Azure Cosmos DB**.

3. In the New account blade, specify the desired configuration for the new **Azure Cosmos DB account** using the following steps:

4. In the ID box, enter a name to identify the Azure Cosmos DB account. When the ID is validated, a green check mark appears in the ID box.

5. The ID value becomes the host name within the URI. The ID may contain only lowercase letters, numbers, and the ‘-’ character, and must be between 3 and 50 characters. Note that documents.azure.com is appended to the endpoint name you choose, the result of which becomes your Azure Cosmos DB account endpoint.

6. In the API section, **select SQL**.

7. In the Subscription section, select the Azure subscription that you want to use for the Azure Cosmos DB account.

8. If your account has only one subscription, that subscription is selected by default.

9. In the Resource Group section, Create a new resource group for your Azure Cosmos DB account named DocDB.

10. Use Location to specify the geographic location closest to your current location in which to host your Azure Cosmos DB account.

11. Once the new Azure Cosmos DB account options are configured, click the Create button.

12. To check the status of the deployment, check the Notifications hub at the top-right corner of your Azure portal.

13. After the Azure Cosmos DB account is created, you will receive a notification in the Notifications Hub indicating that the deployment action is complete.
14. Download the [documentdb-json-bulk.zip](https://d37djvu3ytnwxt.cloudfront.net/assets/courseware/v1/fc756eaab966f3a972174e6f82c70674/asset-v1:Microsoft+DAT221x+1T2017+type@asset+block/documentdb-json-bulk.zip) compressed folder and save it to your local machine.

15. In the Azure Cosmos DB blade that opens, locate and click the Azure Cosmos DB account instance you created earlier in this module.

16. In the menu at the top of the Azure Cosmos DB account blade, locate and click the Add Collection button.

17. The blade will automatically navigate to the Data Explorer pane and show the Add Collection popup.

## Uploading the Collection
1. In the Add Collection popup, specify the following values for your new collection and database:

2. In the Database Id box, enter the name **ecommerce**.

3. In the Collection Id box, enter the name **customers**.

4. In the Storage Capacity section, select the Fixed (10 GB) option.

5. In the Throughput (400 - 10,000 RU/s) section, enter the value 400 in the numeric box.

6. Click the OK button.

### Uploading the data
1. Wait for the “Creating collection customers” operation to complete.

2. Once the operation has completed, locate the menu on the left-side of the Azure Cosmos DB account blade. In the menu, locate the Collections section and then click the Document Explorer option.

3. In the Document Explorer blade, locate the drop-down list at the top of the blade. In the list, select the customers collection within the ecommerce database.

4. Click the Upload button at the top of the blade.

##  Querying Documents using SQL Syntax

1. In a new browser window, sign in to the Azure Portal (https://portal.azure.com).

2. In the Jumpbar, click More Services, locate the Databases section, and then click Azure Cosmos DB.

3. In the Azure Cosmos DB blade that opens, locate and click the Azure Cosmos DB account instance you created earlier in this module.

4. In the menu on the left-side of the Azure Cosmos DB account blade, locate the Collections section and then click the Query Explorer option in the menu.
5. In the Query Explorer blade, select the **ecommerce** database and the customers collection.
6. In the query editor, replace the current query with the following query:
```
SELECT *
FROM customers
```
- In the Query Explorer blade, locate the query editor and replace the current query with the following query:
```
SELECT *
FROM customers
WHERE customers.source = "direct-mail"
```
