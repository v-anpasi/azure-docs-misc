---
title: "Queue Service REST API"
ms.custom: na
ms.date: 2016-06-29
ms.prod: azure
ms.reviewer: na
ms.service: storage
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: reference
ms.assetid: 2793691c-e763-413d-93e7-e111312d5f4b
caps.latest.revision: 29
author: tamram
manager: carolz
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
# Queue Service REST API
The Queue service stores messages that may be read by any client who has access to the storage account.  
  
 A queue can contain an unlimited number of messages, each of which can be up to 64KB in size using version 2011-08-18 or newer. For previous versions, the maximum size of a message is 8KB. Messages are generally added to the end of the queue and retrieved from the front of the queue, although first in, first out (FIFO) behavior is not guaranteed.  
  
 If you need to store messages larger than 64KB, you can store message data as a blob or in a table, and then store a reference to the data as a message in a queue.  
  
 The REST API for the Queue service includes the operations shown in the following table.  
  
|Operation|Description|  
|---------------|-----------------|  
|[Set Queue Service Properties](../rest-conceptual/Set-Queue-Service-Properties.md)|Sets the properties of the Queue service.|  
|[Get Queue Service Properties](../rest-conceptual/Get-Queue-Service-Properties.md)|Gets the properties of the Queue service.|  
|[List Queues](../rest-conceptual/List-Queues1.md)|Lists all queues under the given account.|  
|[Preflight Queue Request](../rest-conceptual/Preflight-Queue-Request.md)|Queries the Cross-Origin Resource Sharing (CORS) rules for the Queue service prior to sending the actual request.|  
|[Get Queue Service Stats](../rest-conceptual/Get-Queue-Service-Stats.md)|Retrieves statistics related to replication for the Queue service. This operation is only available on the secondary location endpoint when read-access geo-redundant replication is enabled for the storage account.|  
|[Create Queue](../rest-conceptual/Create-Queue4.md)|Creates a new queue under the given account.|  
|[Delete Queue](../rest-conceptual/Delete-Queue3.md)|Deletes a queue.|  
|[Get Queue Metadata](../rest-conceptual/Get-Queue-Metadata.md)|Returns queue properties, including user-defined metadata.|  
|[Set Queue Metadata](../rest-conceptual/Set-Queue-Metadata.md)|Sets user-defined metadata on the queue.|  
|[Get Queue ACL](../rest-conceptual/Get-Queue-ACL.md)|Returns details on any stored access policies specified on the queue.|  
|[Set Queue ACL](../rest-conceptual/Set-Queue-ACL.md)|Sets stored access policies for the queue that may be used with Shared Access Signatures.|  
|[Put Message](../rest-conceptual/Put-Message.md)|Adds a message to the queue and optionally sets a visibility timeout for the message.|  
|[Get Messages](../rest-conceptual/Get-Messages.md)|Retrieves a message from the queue and makes it invisible to other consumers.|  
|[Peek Messages](../rest-conceptual/Peek-Messages.md)|Retrieves a message from the front of the queue, without changing the message visibility.|  
|[Delete Message](../rest-conceptual/Delete-Message2.md)|Deletes a specified message from the queue.|  
|[Clear Messages](../rest-conceptual/Clear-Messages.md)|Clears all messages from the queue.|  
|[Update Message](../rest-conceptual/Update-Message.md)|Updates the visibility timeout of a message and/or the message contents.|  
  
## In This Section  
 [Queue Service Concepts](../rest-conceptual/Queue-Service-Concepts.md)  
  
 [Operations on Queues](../rest-conceptual/Operations-on-Queues.md)  
  
 [Operations on Messages](../rest-conceptual/Operations-on-Messages.md)  
  
## See Also  
 [Storage Services REST](../rest-conceptual/Azure-Storage-Services-REST-API-Reference.md)