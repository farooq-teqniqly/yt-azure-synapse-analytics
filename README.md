# Azure Synapse Analytics Machine Learning Example

For more context please view the [YouTube](http://www.youtube.com) video.

## Create Azure Resources

The deployment script creates the following resources:

- An Azure Synapse Workspace
- An Apache Spark pool in the Azure Synapse Workspace
- An Azure Data Lake Storage Account

The script also uploads several CSV files to the Azure Data Lake.

1. Open a Powershell session and go to the repository root.
2. Login to Azure by running `az login`.
3. Get your subscription id by running `az account show --query id`.
4. Run the deployment script specifying your subscription id.

```powershell
.\deploy\deploy.ps1 -location westeurope -subscriptionId [your subscription id]
```

> NOTE: Use the **westeurope** region as this seems to work best with this example.

## Open the Azure Synapse Workspace

When the deployment script successfuly completes, your Azure Synapse Workspace URL is shown in the output:

```bash
Your Azure Synapse workspace url:

https://web.azuresynapse.net?workspace=%2fsubscriptions%2f1e32e17d-db2c-4254-ac01-5010575e89dd%2fresourceGroups%2fsynapsepoc-iauqiv-rg%2fproviders%2fMicrosoft.Synapse%2fworkspaces%2fiauqivsynws
```

Browse to that URL to open your workspace.

# View CSV Files

1. In the navigation menu on the left, click **Data**.
2. Click the **Linked** tab.
3. Expand the **Azure Data Lake Storage Gen2** node in the tree view.
4. The first child node is the Azure Synapse Workspace name. Expand that node and the child node is the name of the Azure Data Lake Filesystem (the name ends in **fs**). Click the file system node.
5. Drill down into the **data** folder until you see the 53 CSV files listed.
