# AzureFiles2BlobStorage

.SYNOPSIS
   This PowerShell script is intended to be run by an Azure Automation Account. The script
   will copy files from an Azure Files Share to an Azure Blob Container and overwrite existing files.

.AUTHOR
	Stephen Furniss

.DESCRIPTION
 	This script uses an Azure Automation Account running as its Managed Identity to automate to transfer of
	files between an Azure File Share and an Azure Blob Container using PowerShell via a Runbook.

.REQUIREMENTS
	PowerShell Version:
	PowerShell Modules: Az.Accounts,Az.ContainerInstance,Az.Storage

.PARAMETER <paramName>
   $AzureSubscriptionName - the name of your Azure subscription which the storage accounts and 
   resource groups are memebrs.
   $resourceGroup - the name of the resource group.
   $storageAccountBlobName - the name of the storage account containing the Block Blob container.
   $storageAccountFileName - the name of the storage account containing the File Share.
   $storageContainerName - the name of the Blob Container.
   $storageFileShareName - the name of the File Share
   $srcExportFolder - the name of the sub folder within the File Share.
   $srcExportFile - the name of the file we will copy from the File Share to the Blob Container.
   $dstExportFolder - the name of the sub folder in the Blob Container.
   $dstExportFile - the name of the file we will create in the Blob Container.
   $srcImportFolder - the name of the sub folder within the Blob Container.
   $srcImportFile - the name of the blob we will copy from the Blob Container to the File Share.
   $dstImportFolder - the name of the sub folder within the File Share.
   $dstImportFile - the name of the file we will create in the File Share.

.EXAMPLE PARAMETERS TO PASS
  $AzureSubscriptionName = "platform-sub-prod-001"
  $resourceGroup = "rg-claimscontrol-prod-ukwest-001"
  $storageAccountBlobName = "stclaimscontrolsftp"
  $storageAccountFileName = "stclaimscontrolfiles"
  $storageContainerName = "claimscontrol"
  $storageFileShareName = "claimscontrol"
  $srcExportFolder = "ToSUPPLIER"
  $srcExportFile = "SupplierExport.csv"
  $dstExportFolder = "ToSUPPLIER"
  $dstExportFile = "SupplierExport.csv"
  $srcImportFolder = "ToSAP"
  $srcImportFile = "SAPImport.csv"
  $dstImportFolder = "ToSAP"
  $dstImportFile = "SAPImport.csv"
