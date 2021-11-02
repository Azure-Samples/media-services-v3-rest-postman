---
page_type: sample
languages:
- json
products:
- azure
- azure-media-services
description: "A full Postman collection and Environment variables to test drive the new v3 REST API directly from within Postman 6.0 or higher."
urlFragment: azure-media-services-postman-collection
---

# Azure Media Services v3 Postman collection 
 
The *Postman* folder in this repository contains a full Postman collection and Environment variables to test drive the new v3 REST API directly from within Postman 6.0 or higher.  These samples are built on top of the 2018-07-01 version of the REST API and may not be up-to-date. Please check the latest OpenAPI specifications published in the [azure-res-api-specs](https://github.com/Azure/azure-rest-api-specs/tree/master/specification/mediaservices/resource-manager/Microsoft.Media/stable) GitHub repository for Microsoft.Media resource provider. 

**WARNING**: It is not advised to attempt to wrap the REST API for Media Services directly into your own library code, as doing so properly for production purposes would require you to implement the full Azure Resource Management retry logic and understand how to manage long running operations in Azure Resource Management APIs.  This is handled by the client SDKs for various language - .NET, Java, TypeScript, Python, Ruby, etc. - for you automatically and reduces the chances of you having issues with rety logic or failed API calls.  The client SDKs all handle this for you already.  The Postman collection is provided more as a teaching tool, and to show you what the client SDKs are actually doing on the wire during your development with the various client SDKs. 

The following files are included:

|File name|Description|
|---|---|
|*Media Services v3.postman_collection.json*|The collection contains grouped definitions of HTTP requests that call Azure Media Services v3 REST APIs.|
|*Azure Media Service v3 Environment.postman_environment.json*|The environment file contains variables that are used by the collection. |

These files support the [Tutorial: Upload, encode, and stream videos with REST](https://docs.microsoft.com/azure/media-services/latest/stream-files-tutorial-with-rest) article.

## Prerequisites

To import and use the json files in this repository, you need to install [Postman](https://www.getpostman.com/) 6.0 or higher.

## Set environment variables

Get the values that will enable you to access AMS v3 APIs. Then, set the environment variables to the values from the CLI or portal. 

The following bash shell script creates a service principal for the account and returns the app.config settings as xml

    #!/bin/bash

    resourceGroup=amsResourceGroup
    amsAccountName=amsaccountname
    amsSPName=amsAADapplication

    # Create a service principal with password and configure its access to an Azure Media Services account.
    az ams account sp create \
    --account-name $amsAccountName \
    --name $amsSPName \
    --resource-group $resourceGroup \
    --role Owner \
    --xml \
    --years 2 \

For more information, see [Access APIs](https://docs.microsoft.com/azure/media-services/latest/access-api-cli-how-to).

