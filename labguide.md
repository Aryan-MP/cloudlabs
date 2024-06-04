## Prerequisites

To complete this tutorial's steps, you need to have access to a resource group for which you are assigned the Owner role. Create the Synapse workspace in this resource group.

### Create a Synapse workspace in the Azure portal

#### Start the process

1. Open the Azure portal, in the search bar enter Synapse without hitting enter.

![img](./lab/1.png)
2. In the search results, under Services, select Azure Synapse Analytics.

![img](./lab/2.png)
3. Select Create to create a workspace.

![img](./lab/3.png)

#### Basics tab > Project Details

Fill in the following fields:

- **Subscription** - Pick any subscription.
- **Resource group** - Use any resource group.
- **Managed Resource group** - Leave this blank.

![img](./lab/4.png)

#### Basics tab > Workspace details

Fill in the following fields:

- **Workspace name** - Pick any globally unique name. In this tutorial, we'll use `myworkspace`.

![img](./lab/5.png)
- **Region** - Pick the region where you have placed your client applications/services (for example, Azure VM, Power BI, Azure Analysis Service) and storages that contain data (for example Azure Data Lake storage, Azure Cosmos DB analytical storage).

*Note: A workspace that is not co-located with the client applications or storage can be the root cause of many performance issues. If your data or the clients are placed in multiple regions, you can create separate workspaces in different regions co-located with your data and clients.*

#### Select Data Lake Storage Gen 2:

- By Account name, select Create New and name the new storage account . the name must be unique.

![img](./lab/6.png)

![img](./lab/7.png)

![img](./lab/8.png)
- By File system name, select Create New and name it `users`. This will create a storage container called `users`. The workspace will use this storage account as the "primary" storage account to Spark tables and Spark application logs.

![img](./lab/9.png)
- Check the "Assign myself the Storage Blob Data Contributor role on the Data Lake Storage Gen2 account" box.

## Completing the process

Select **Review + create** > **Create**. Your workspace is ready in a few minutes.

![img](./lab/10.png)

![img](./lab/11.png)

*Note: To enable workspace features from an existing dedicated SQL pool (formerly SQL DW) refer to How to enable a workspace for your dedicated SQL pool (formerly SQL DW).*

### Open Synapse Studio

After your Azure Synapse workspace is created, copy the link as shown in the picture and paste it in your browser's incognito mode.

![img](./lab/12.png)

![img](./lab/13.png)

Create a dedicated SQL pool

- In Synapse Studio, on the left-side pane, select Manage > SQL pools under Analytics pools.

![img](./lab/18.png)
- Select New.

![img](./lab/19.png)
- For Dedicated SQL pool name select SQLPOOL1.
- For Performance level choose DW100C.
- Select Review + create > Create. Your dedicated SQL pool will be ready in a few minutes.

![img](./lab/20.png)

![img](./lab/21.png)

Your dedicated SQL pool is associated with a SQL database that's also called SQLPOOL1.

- Navigate to Data > Workspace.
- You should see a database named SQLPOOL1. If you do not see it, select Refresh.

![img](./lab/22.png)

