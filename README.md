---
services: media-services
platforms: rest
author: Juliako
---

# Azure Media Services v3 postman collection 

The *Postman* folder in this repository contains a full Postman collection and Environment variables to test drive the new v3 REST API directly from within Postman 6.0 or higher.

The following files are included:

|File name|Description|
|---|---|
|*Media Services v3 (2018-03-30-preview).postman_collection.json*|The collection contains grouped definitions of HTTP requests that call Azure Media Services v3 REST APIs.|
|*Azure Media Service v3 Environment.postman_environment.json*|The environment file contains variables that are used by the collection. |

## Prerequisites

To import and use the json files in this repository, you need to install [Postman](https://www.getpostman.com/) 6.0 or higher.

## Set environment variables

Get the values that will enable you to access AMS v3 APIs. Then, set the environment variables to the values you got. 

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

