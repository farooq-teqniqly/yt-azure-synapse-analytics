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

When the deployment script successfuly completes, your Azure Synapse Workspace URL and file system endpoint is shown in the output:

```bash
Your Azure Synapse workspace url:
https://web.azuresynapse.net?workspace=%2fsubscriptions%2f1e32e17d-db2c-4254-ac01-5010575e89dd%2fresourceGroups%2fsynapsepoc-atjrra-rg%2fproviders%2fMicrosoft.Synapse%2fworkspaces%2fatjrrasynws

Your file system endpoint:
atjrrasynfs@atjrrasyndl.dfs.core.windows.net
```

> **NOTE**: you will need the file system endpoint value when running the notebooks.

Browse to the workspace URL.

# Run the "Basic" Notebook

Run a notebook that performs basic data exploration.

1. In the navigation menu on the left, click **Develop**.
2. Expand **Notebooks** and select **Basic**.
3. On **line 2 of the first cell**, set the value of the `filesystem_endpoint` variable to the name of your file system endpoint. The file system endpoint can be found in the deployment script output.
4. In the **Attach to** drop-down in the toolbar, select **sparkPool01**.
5. Click **Run all**.
6. The Spark cluster starts, and the code in the notebook is executed.

> **NOTE**: It can take several minutes to start the Spark cluster. Subsequent runs of the notebook will be much faster. The cluster is configured to shut down after 30 minutes of inactivity.

# Run the "K-means Clustering" Notebook

Run a notebook that performs basic data exploration.

1. In the navigation menu on the left, click **Develop**.
2. Expand **Notebooks** and select **K-means Clustering**.
3. On **line 2 of the second cell**, set the value of the `filesystem_endpoint` variable to the name of your file system endpoint. The file system endpoint can be found in the deployment script output.
4. In the **Attach to** drop-down in the toolbar, select **sparkPool01**.
5. Click **Run all**.
6. The Spark cluster starts, and the code in the notebook is executed.
