#  Creating an Application Solution using Azure Storage Tables
- In this lab, we will build and populate a NoSQL data solution using Azure Storage Tables.
- We will then take an ASP.NET MVC web application written by our development team, deploy this application to Azure and then finally connect our database to the web application.
## Creating Database Assets

1. Navigate to the Azure Portal (<http://portal.azure.com).

2. In the left navigation menu, click the New button and then select the Storage category.

3. In the Storage blade, select the Storage Account option.

4. In the Create storage account blade, perform the following actions:

- In the Name box, give your account a globally unique name. Name validation will run immediately to ensure that your name does not conflict with another Storage account name in Azure.

- In the Resource Group section, select the Create new option and use the name StorageTables for your Resource Group.

- Click the Create button.

5. Wait for the deployment of your Storage account to complete before continuing on with this lab.

6. In the left navigation menu, click the More Services option.

7. In the list of services, scroll down and click the Storage accounts option.

8. In the Storage accounts blade, locate and click the account that you have just created.

9. In the Storage account blade, locate the Settings section in the left menu and click the Access keys option.
10. Record the following values:
- **[Account Name]**: Locate the Storage account name box and record the name of your account.
- **[Account Key]**: Locate the Keys section and record the value of key1.
- **[Connection String]**: Locate the ellipsis button to the right of the value of key2 and click this button. Select the View connection string option. Record the connection string that is displayed.

## Install Database Tooling and Assets
1. Download the CSV file from this link:[Download](https://prod-edxapp.edx-cdn.org/assets/courseware/v1/bbaa65b0f749dca45b122a90959b32d5/asset-v1:Microsoft+DAT221x+1T2018+type@asset+block/storage.typed.csv)
- This CSV file includes multiple entities that will be imported into our Storage Table instance.
2. On your local machine, save the downloaded [CSV File] to a directory that you will be able to access later in this lab.
3. Download the Azure Storage Explorer from this [link](http://storageexplorer.com)
### Populating Database Data

1. Within the **Azure Storage Explorer** tool, locate the navigation menu on the left side. Expand the **Local and Attached** node and then right-click the **Storage Accounts** node. Select the **Connect** to Azure storage... option.
2.In the Connect to Azure Storage dialog, perform the following actions:
- Select the Use a storage account name and key option.
- Click the Next button.
- Back in the tool, you should see a new node for your Storage account. Expand this node.
- Right-click the child Tables node under your Storage account node. Select the Create Table option.
- You will see a dialog to name your new table. Enter the name products for your new table.
- You will immediately see the products tab open in the explorer. Locate and click the Import button at the top of the tab.
## Querying Database Data
1. In the Azure Storage Explorer tool, locate the Query button at the top of the products tab.
2. Locate and click the Clear query button.
- This button has an eraser icon. If you are having a hard time finding the button, you can simply hover over each icon until you see the Clear query text.

## Deploy and Test Web Application
1. Click the following button to go to the Template Deployment blade in the Azure portal:[link](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FAzure-Architecture-Workshop%2Fasset-tracking%2Fstoragetables%2Fdeploy%2Farmdeploy.json)
2.Once you reach the Azure Portal, you will immediately see the Custom deployment blade. In the Custom deployment blade, perform the following actions:
- In the Resource Group section, select the Use existing option and then select the StorageTables Resource Group from the list.
- In the Terms and Conditions section, read the Marketplace terms and then click the I agree to the terms and conditions stated above checkbox.
- Click the Pin to dashboard checkbox to ensure that the Resource Group is visible on your dashboard and that the Resource Group is opened automatically when the deployment is complete.
- Click the Purchase button.
3. Wait for the Resource deployment operation to complete before continuing on with this lab.
4. Once the deployment has completed, you will immediately see the * Resource Group* blade. In this blade, locate and select your newly created Web App instance.
5. In the App Service blade, locate the Settings section in the left menu and click the Application Settings option.
6. In the Application Settings blade, scroll down and locate the App Settings section. Observe the settings that have been created in your Web App.
7. Locate and click the Overview option in the left menu.
8. In the App Service blade, locate and click the Browse button at the top of the blade. This will open your web application in a new browser window or tab.
9. On the Asset Tracking System, click the Configure link.

10. On the configuration page, perform the following actions:

- In the Connection String box, enter the [Connection String] value recorded earlier in this lab.
- In the Table Name box, enter the value: products.
- Click the Save Configuration button.
11. Click the Dashboard link.
