# AzureFiles2BlobStorage

.SYNOPSIS
   This PowerShell script is intended to be run by an Azure Functional App. The script
   will copy files from an Azure Files Share to an Azure Blob Container and overwrite existing files.

.AUTHOR
	Stephen Furniss

.DESCRIPTION
 	This script uses an Azure Functional App running as its Managed Identity to automate to transfer of
	files between an Azure File Share and an Azure Blob Container using PowerShell.

.REQUIREMENTS
	PowerShell Version:
	PowerShell Modules:

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
  $AzureSubscriptionName = "mysubscription-001"
  $resourceGroup = "rg-myapp-ukwest-001"
  $storageAccountBlobName = "sablobftp"
  $storageAccountFileName = "safileaccount"
  $storageContainerName = "my-container"
  $storageFileShareName = "my-file-share"
  $srcExportFolder = "ToSUPPLIER"
  $srcExportFile = "SupplierExport.csv"
  $dstExportFolder = "ToSUPPLIER"
  $dstExportFile = "SupplierExport.csv"
  $srcImportFolder = "ToSYSTEM"
  $srcImportFile = "SYSTEMImport.csv"
  $dstImportFolder = "ToSYSTEM"
  $dstImportFile = "SYSTEMImport.csv"
