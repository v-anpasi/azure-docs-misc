---
title: "Deciding when to use Azure Blobs, Azure Files, or Azure Data Disks"
ms.custom: na
ms.date: 2016-06-29
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: reference
ms.assetid: 9f59395e-b159-48d5-8cde-60acaecf2335
caps.latest.revision: 20
translation.priority.mt: 
  - de-de
  - es-es
  - fr-fr
  - it-it
  - ja-jp
  - ko-kr
  - pt-br
  - ru-ru
  - zh-cn
  - zh-tw
---
# Deciding when to use Azure Blobs, Azure Files, or Azure Data Disks
Microsoft Azure provides several ways to store and access data in the cloud. You have the following choices when deciding how to store and access data:  
  
-   **Azure Files** -  Provides an SMB interface, client libraries, and a [REST interface](../rest-conceptual/File-Service-REST-API.md) that allows easy access from anywhere to stored files.  
  
     Reasons you would use Azure Files:  
  
    -   You want to "lift and shift" an application to the cloud which already uses the native file         system APIs to share data between it and other applications running in Azure.  
  
    -   You want to store development and debugging tools that need to be accessed from many virtual        machines.  
  
-   **Azure Blobs** - Provides client libraries and a [REST interface](../rest-conceptual/Blob-Service-REST-API.md) that allows unstructured data to  be stored and accessed at a massive scale in block blobs.  
  
     Reasons you would use Azure Blobs:  
  
    -   You want your application to support streaming and random access scenarios.  
  
    -   You want to be able to access application data from anywhere.  
  
-   **Azure Data Disks** - Provides client libraries and a [REST interface](https://msdn.microsoft.com/library/azure/mt163591.aspx) that allows data to be  persistently stored and accessed from an attached virtual hard disk.  
  
     Reasons you would use Azure Data Disks:  
  
    -   You want to lift and shift applications that use native file system APIs to read and write          data to persistent disks.  
  
    -   You want to store data that is not required to be accessed from outside the virtual machine         to which the disk is attached.  
  
> [!NOTE]
>  For more information about using client libraries with storage services, see Developing Against Storage in [Introduction to Microsoft Azure Storage](https://azure.microsoft.com/en-us/documentation/articles/storage-introduction/).  
  
 The following table compares Azure Files with Azure Blobs.  
  
||||  
|-|-|-|  
|**Attribute**|**Azure Blobs**|**Azure Files**|  
|Durability options|LRS, ZRS, GRS (and RA-GRS for higher availability)|LRS, GRS|  
|Accessibility|REST APIs|REST APIs<br /><br /> SMB 2.1 and SMB 3.0 (standard file system APIs)|  
|Connectivity|REST APIs -- Worldwide|REST APIs - Worldwide<br /><br /> SMB 2.1 -- Within region<br /><br /> SMB 3.0 -- Worldwide|  
|Endpoints|http://myaccount.blob.core.windows.net/mycontainer/myblob|\\\myaccount.file.core.windows.net\myshare\myfile.txt<br /><br /> http://myaccount.file.core.windows.net/myshare/myfile.txt|  
|Directories|Flat namespace|True directory objects|  
|Case sensitivity of names|Case sensitive|Case insensitive, but case preserving|  
|Capacity|Up to 500 TB containers|5 TB file shares|  
|Throughput|Up to 60 MB/s per block blob|Up to 60 MB/s per share|  
|Object Size|Up to 200 GB/block blob|Up to 1TB/file|  
|Billed capacity|Based on bytes written|Based on file size|  
|Client libraries|Multiple languages|Multiple languages|  
  
 Azure Files complement Azure Data Disks. A data disk can only be attached to one Azure Virtual Machine at a time. Data disks are fixed format VHDs stored as page blobs in Azure Storage and are used by the virtual machine to store durable data. File shares based on Azure Files can be accessed in the same way as the local disk is accessed (using native file system APIs) and can be shared across many virtual machines.  
  
 The following table compares Azure Files with Azure Data Disks.  
  
||||  
|-|-|-|  
|**Attribute**|**Azure Data Disks**|**Azure Files**|  
|Scope|Exclusive to a single virtual machine|Shared access across multiple virtual machines|  
|Snapshots and Copy|Yes|No|  
|Configuration|Connected at startup of the virtual machine|Connected after the virtual machine has started|  
|Authentication|Built-in|Set up with net use|  
|Cleanup|Automatic|Manual|  
|Access using REST|Files within the VHD cannot be accessed|Files stored in a share can be accessed|  
|Max Size|1 TB disk|5 TB File Share and 1 TB file within share|  
|Max 8KB IOps|500 IOps|1000 IOps|  
|Throughput|Up to 60 MB/s per Disk|Up to 60 MB/s per File Share|  
  
 When making decisions about how your data is stored and accessed, you should also consider the costs involved. For more information, see [Storage Pricing Details](https://azure.microsoft.com/en-us/pricing/details/storage/).  
  
 Some SMB features are not applicable to the cloud. For more information, see [Features Not Supported By the Azure File Service](../rest-conceptual/Features-Not-Supported-By-the-Azure-File-Service.md).  
  
 For more information about data disks, see [Managing Disks and Images](https://azure.microsoft.com/en-us/documentation/articles/virtual-machines-disks-vhds/) and [How to Attach a Data Disk to a Windows Virtual Machine](https://azure.microsoft.com/en-us/documentation/articles/storage-windows-attach-disk/).