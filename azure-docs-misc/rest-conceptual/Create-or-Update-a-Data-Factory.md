---
title: "Create or Update a Data Factory"
ms.custom: na
ms.date: 2016-07-21
ms.prod: azure
ms.reviewer: na
ms.service: data-factory
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: reference
ms.assetid: 839a1d9e-a733-4202-8c64-4cff88044b6a
caps.latest.revision: 11
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
# Create or Update a Data Factory
  The Create or Update Data Factory operation creates a new data factory, or updates the content of an existing data factory.  
  
## Request  
 The Create or Update Data Factory request may be constructed as follows (HTTPS is recommended):.  
  
  
|**HTTP Verb**|**Request URI**|**HTTP Version**|  
|-------------|---------------|----------------|  
|PUT|https://management.azure.com/subscriptions/<SubscriptionID\>/resourcegroups/<ResourceGroupName\>/providers/Microsoft.DataFactory/datafactories/<DataFactoryName\>?api-version=<Api-Version>|HTTP/1.1|  
  
### URI Parameters  
  
  
|**URI Parameter**|**Required**|**Description**|  
| --------------- | ---------- | ------------- |   
|SubscriptionID|Yes|your Azure subscription ID.|  
|ResourceGroupName|Yes|Unique name for the resource group that hosts your Azure data factory Service.|  
|DataFactoryName|Yes|Name of data factory you want to create.|  
|Api-Version|Yes|Specifies the version of the protocol used to make this request.|  
  
### Request Headers  
 The following table describes the request headers.  
  
|**Request Header**|**Required**|**Description**|  
|-|-|-|  
|x-ms-client-request-id|Yes|The operation ID for this request.|  
  
### Request Body  
 The format of the request body is as follows:  
  
```  
  
{  
    "name": <name>,  
    "location": <location>,  
    "tags": <tags>,  
    "properties": <properties>  
}  
  
```  
  
 The following table describes the elements of the request body.  
  
|**Element Name**|**Required**|**Description**|  
|-|-|-|  
|name|Yes|Specifies the name of data factory.|  
|location|Yes|Specifies the supported Azure location of data factory.|  
|tags|No|A list of key-value pairs that describe the resource.|  
|properties|No|Properties of the data factory.|  
  
## Response  
 The response includes an HTTP status code, a set of response headers, and a response body.  
  
### Status Code  
  
-   200 (OK) - if the request completed successfully.  
  
-   202 (Accepted) - if the request was accepted.  
  
-   400 (Bad Request) - if the request body failed validation.  
  
-   404 (NotFound) - if the subscription or resource group does not exist.  
  
-   412 (Precondition Failed) - if the condition specified by If-Match header failed.  
  
-   501 (Not Implemented) - if validate is not implemented.  
  
#### Response Headers  
 The response for this operation includes the following headers. The response may also include additional standard HTTP headers. All standard headers conform to the [HTTP/1.1 protocol specification](http://go.microsoft.com/fwlink/?linkid=150478).  
  
|**Response Header**|**Description**|  
|-|-|  
|x-ms-request-id|A unique identifier for the current operation, which is generated by the Data Factory service.|  
|x-ms-ratelimit-remaining-subscription-writes|The remaining limit for current subscription.|  
|x-ms-correlation-request-id|Specifies the tracing correlation ID for the request; the resource provider **must** log this ID so that end-to-end requests can be correlated across Azure.|  
|x-ms-routing-request-id|Location+DateTime+correlation-request-ID|  
|Date|A UTC date/time value generated by the service that indicates the time at which the response was initiated.|  
|Location|URI of the object you want to create or get.|  
  
#### Response Body  
  
```  
  
{  
    "name": <Name>  
    "id": <ID>,  
    "type": "Microsoft.DataFactory/datafactories",  
    "location": <location>,  
    "tags": <tag>,  
    "properties":   
    {  
        "dataFactoryId": <DataFactoryID>  
        "hCatalogDescription": null,  
        "provisioningState": <provisioningstate>  
        "error": <Error>,  
        "errorMessage": <ErrorMessage>  
    }  
}  
  
```  
  
 The following table describes the elements of the response body.  
  
|**Element Name**|**Description**|  
|-|-|  
|name|Specifies the name of the data factory.|  
|id|Specifies the identifying URL of the Data Factory.|  
|location|Specifies the supported Azure location of data factory.|  
|tags|A list of key-value pairs that describe the resource.|  
|datafactoryID|Auto-generated ID for this Data Factory.|  
|provisioningstate|Specifies the current provisioning state of the Data Factory. When a Data Factory is successfully created, the value of the element is **Succeeded**.|  
|error|Specifies whether an error occurred during deployment.|  
|errormessage|Message related to the error.|  
  
## Sample Request and Response  
 For the following example URI:  
  
```  
PUT: https://management.azure.com/subscriptions/00000000-0000-0000-0000-000000000000/resourcegroups/adf/providers/Microsoft.DataFactory/datafactories/test?api-version=2015-10-01  
```  
  
 **Request header:**  
  
```  
  
Headers:  
x-ms-client-request-id        : 029a8839-027e-43c5-8854-af4388dcd232  
  
```  
  
 **Request body:**  
  
```  
  
Body:  
{  
  "name": "RestDataFactory",  
  "location": "West US",  
  "tags": {}  
}  
  
```  
  
 The following response is returned:  
  
```  
  
Status Code:  
Created  
  
Headers:  
Pragma                        : no-cache  
x-ms-request-id               : 00000000-1111-1111-1111-000000000000  
x-ms-ratelimit-remaining-subscription-writes: 11999  
x-ms-correlation-request-id   : 00000000-1111-2222-1111-000000000000  
x-ms-routing-request-id       : WESTUS:20141203T212810Z: 00000000-1111-2222-1111-000000000000  
Strict-Transport-Security     : max-age=31536000; includeSubDomains  
Cache-Control                 : no-cache  
Date                          : Wed, 03 Dec 2014 21:28:09 GMT  
Location                      : https://management.azure.com/subscriptions/00000000-0000-0000-0000-000000000000/resourcegroups/adf/providers/Microsoft.DataFactory/datafactories/test?api-version=2015-10-01  
Server                        : Microsoft-IIS/8.5  
X-Powered-By                  : ASP.NET  
client-tracking-id            : 10  
The response includes the following XML body.  
{  
  "name": "test",  
  "id": "/subscriptions/00000000-0000-0000-0000-000000000000/resourcegroups/adf/providers/Microsoft.DataFactory/datafactories/test",  
  "type": "Microsoft.DataFactory/datafactories",  
  "location": "westus",  
  "tags": {},  
  "properties": {  
    "dataFactoryId": "39d4e663-cfcb-4ee9-ad19-92cf87de9197",  
    "hCatalogDescription": null,  
    "provisioningState": "Succeeded",  
    "error": null,  
    "errorMessage": null  
  }  
}  
  
```  
  
  