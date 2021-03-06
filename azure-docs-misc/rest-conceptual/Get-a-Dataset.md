---
title: "Get a Dataset"
ms.custom: na
ms.date: 2016-07-21
ms.prod: azure
ms.reviewer: na
ms.service: data-factory
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: reference
ms.assetid: 0f9e0ff7-03d9-47a0-a200-82f9e3a99aac
caps.latest.revision: 9
author: spelluru
manager: jhubbard
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
# Get a Dataset
  The Get Dataset operation gets information about datasets in a data factory.  
  
## Request  
 The Get Dataset request may be constructed as follows (HTTPS is recommended):  
  
|**HTTP Verb**|**Request URI**|**HTTP Version**|  
|-|-|-|  
|GET|https://management.azure.com/subscriptions/<SubscriptionID\>/resourcegroups/<ResourceGroupName\>/providers/Microsoft.DataFactory/datafactories/<DataFactoryName\>/datasets/<DatasetName\>?api-version=<Api-Version>|HTTP/1.1|  
  
### URI Parameters  
  
|**URI Parameter**|**Required**|**Description**|  
|-|-|-|  
|SubscriptionID|Yes|Your Azure subscription ID.|  
|ResourceGroupName|Yes|A unique name for the resource group that hosts your Azure data factory Service.|  
|DataFactoryName|Yes|Name for the data factory that you want to get your dataset in.|  
|DatasetName|Yes|Name of dataset you want to get.|  
|Api-Version|Yes|Specifies the version of the protocol used to make this request.|  
  
### Request Headers  
 The following table describes the request headers.  
  
|Request Header|Required|Description|  
|-|-|-|  
|x-ms-client-request-id|Yes|The operation id for this request.|  
  
### Request Body  
 None.  
  
## Response  
 The response includes an HTTP status code, a set of response headers, and a response body.  
  
### Status Code  
  
-   200 (OK) - if the request was completed successfully.  
  
-   400 (Bad Request) - if the request body fails validation.  
  
-   404 (NotFound) - if the subscription or resource group does not exist.  
  
-   412 (Precondition Failed) - if the condition specified by If-Match header failed.  
  
### Response Headers  
 The response for this operation includes the following headers. The response may also include additional standard HTTP headers. All standard headers conform to the [HTTP/1.1 protocol specification](http://go.microsoft.com/fwlink/?linkid=150478).  
  
|**Response Header**|**Description**|  
|-|-|  
|x-ms-request-id|A unique identifier for the current operation, service generated.|  
|x-ms-ratelimit-remaining-subscription-writes|The remaining limit for current subscription.|  
|x-ms-correlation-request-id|Specifies the tracing correlation Id for the request. The resource provider **must** log this so that end-to-end requests can be correlated across Azure.|  
|x-ms-routing-request-id|Location+DateTime+correlation-request-ID|  
|Date|A UTC date/time value generated by the service that indicates the time at which the response was initiated.|  
  
### Response Body  
 Response body depends on your dataset type. This example uses an AzureBlob dataset.  
  
```  
  
{  
  "name": "InputDataset",  
  "id":  
"/subscriptions/<subscription ID>/resourcegroups/<resource group name>/providers/Microsoft.DataFactory/datafactories/  
<data factory name>/tables/InputDataset",  
    "type": "AzureBlob",  
    "linkedServiceName": "<Name of the Data Factory linked service that contains the data>",  
    "typeProperties": {  
            "type specific property": "<value>",  
            "type specific property 2": "<value>"  
    },  
    "availability": {  
      "frequency": "<Hour | Day etc...>",  
      "interval": <number>  
    },  
    "external": true,  
    "policy": {},  
    "id": "7c4495bf-f12b-46b6-a653-d4cda899c91c",  
    "createTime": "2016-02-06T00:41:05.2978434Z",  
    "provisioningState": "Succeeded"  
  }  
}  
  
```  
  
 See [Datasets in Azure Data Factory](https://azure.microsoft.com/documentation/articles/data-factory-create-datasets/) article for descriptions of properties in the JSON.  
  
## Sample Request and Response  
 Example URI:  
  
```  
GET: https://management.azure.com/subscriptions/00000000-0000-0000-0000-000000000000/resourcegroups/adf/providers/Microsoft.DataFactory/datafactories/test/dataset/InputDataset?api-version=2015-10-01  
```  
  
 The request is sent with the following headers.  
  
```  
x-ms-client-request-id        : 00000000-1111-1111-1111-000000000000  
```  
  
 After the request has been sent, the following response is returned.  
  
 Header:  
  
```  
  
Status Code:  
OK  
  
Headers:  
Pragma                        : no-cache  
x-ms-request-id               : 00000000-1111-1111-1111-000000000000  
x-ms-ratelimit-remaining-subscription-reads: 14998  
x-ms-correlation-request-id   : 00000000-1111-2222-1111-000000000000  
x-ms-routing-request-id       : EASTUS:20160206T004938Z:00000000-1111-2222-1111-000000000000  
Strict-Transport-Security     : max-age=31536000; includeSubDomains  
Cache-Control                 : no-cache  
Date                          : Sat, 06 Feb 2016 00:49:37 GMT  
Server                        : Microsoft-IIS/8.5  
X-Powered-By                  : ASP.NET  
  
```  
  
 The response includes the following XML body.  
  
```  
  
{  
  "name": "InputDataset",  
  "id":  
"/subscriptions/<subscription ID>/resourcegroups/<resource group name>/providers/Microsoft.DataFactory/datafactories/<data factory name>/tables/InputDataset",  
  "properties": {  
    "structure": [  
      {  
        "name": "FirstName",  
        "type": "String"  
      },  
      {  
        "name": "LastName",  
        "type": "String"  
      }  
    ],  
    "published": false,  
    "type": "AzureBlob",  
    "linkedServiceName": "StorageLinkedService",  
    "typeProperties": {  
      "fileName": "emp.txt",  
      "folderPath": "adftutorial/",  
      "format": {  
        "type": "TextFormat",  
        "columnDelimiter": ","  
      }  
    },  
    "availability": {  
      "frequency": "Hour",  
      "interval": 1  
    },  
    "external": true,  
    "policy": {},  
    "id": "00000000-1111-1111-1111-000000000000",  
    "createTime": "2016-02-06T00:41:05.2978434Z",  
    "provisioningState": "Succeeded"  
  }  
}  
  
```  
  
  