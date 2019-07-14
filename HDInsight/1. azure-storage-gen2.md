# Data Lake Storage Gen2

#### Overview

This document covers the CLI steps to create Azure Gen2 storage, then assigning managed identity.

#### Steps


* **Environment variables**: Use the commands below to set the Resource group and other environment variables.

```
export LOC=westus
az account set --subscription 917f0e40-319a-462c-8d89-330f3bf4b45b
export RESOURCE_GROUP=rg-casestduy1
export IDENTITY=identity-casestudy1
```

* **Resource Group**: Only create if you do not have it already.

```
$az group create --name $RESOURCE_GROUP --location $LOC
```

* **Managed Identity**: Only create if you do not have it already.
```
az identity create -g $RESOURCE_GROUP -n $IDENTITY
```

* **Gen2 Extension**: Add extension to Azure CLI to use the new feature of Gen2
```
az extension add --name storage-preview
```

* **Storage Gen2 Creation**: Make sure the last parameter `hierarchical-namespace` is set to True. 
This allows one to manage BLOB as if it is file system. 
_For more information visit [Azure Gen2 link](https://docs.microsoft.com/en-us/azure/storage/blobs/data-lake-storage-namespace)_

```
az storage account create --name $AZ_DLAKE_GEN2 --resource-group $RESOURCE_GROUP --location $LOC --sku Standard_LRS --kind StorageV2 --hierarchical-namespace true
```

* **Assign Managed Identity**: This needs to be done from the Azure portal. In the portal, assign the the role of ""
_Note: The CLI option not available yet to assign._
