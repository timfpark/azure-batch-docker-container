# Containerized Azure Batch Workloads

This project is an adaption of the Azure Batch sample to run a sample containerized workload with Azure Batch. It runs a specified docker container for each input file in InputFiles and handles pool creation and deletion around this.

It requires as input the following environmental variables:

```
BATCH_ACCOUNT_NAME (name of your Azure batch account)
BATCH_ACCOUNT_KEY (key for your Azure batch account)
BATCH_ACCOUNT_URL (url of your Azure batch account, eg. 'https://batchtest.eastus.batch.azure.com')
POOL_ID (pool id to create and use)'
DEDICATED_POOL_NODE_COUNT (number of dedicated pool nodes to use. 0 recommended for lowest cost, a high number for lowest latency)
LOW_PRIORITY_POOL_NODE_COUNT (number of low priority VMs to use. large number for lowest cost, a small number for lowest latency)
POOL_VM_SIZE (VM SKU type. 'Standard_A1_v2' recommended for general purpose, 'Standard_F2s_v2' for compute heavy workloads, 'Standard_E2_v3' for memory heavy workloads)
JOB_ID (job id for run)

CONTAINER_IMAGE (image to run as batch process)

STORAGE_ACCOUNT_NAME = (storage account name for input and output)
STORAGE_ACCOUNT_KEY = (storage account key for input and output)
INPUT_STORAGE_CONTAINER (what storage container to use as input.  all files in this container will be enumerated for input file tasks)
OUTPUT_STORAGE_CONTAINER (what storage container to put output in - passed to the container as env var of the same name)
MODEL_URL (url of the model to use - passed to the container as env var of the same name)
```

Note, by default there is a limit of 100 cores for both dedicated and low priority cores per Azure Batch account. You can raise a support request to raise this for larger workloads.

For more details and explanation, see the accompanying article [Run a parallel workload with Azure Batch using the Python API](https://docs.microsoft.com/azure/batch/tutorial-parallel-python).

## Prerequisites

-   Azure Batch account and linked general-purpose Azure Storage account
-   Python 2.7 or 3.3 or later including pip

## Resources

-   [Azure Batch documentation](https://docs.microsoft.com/azure/batch/)
-   [Azure Batch code samples](https://github.com/Azure/azure-batch-samples)

## Project code of conduct

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/). For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.
