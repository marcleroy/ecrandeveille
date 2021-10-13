---
title: 'Azure Functions CLI and templates'
date: Mon, 20 Sep 2021 14:00:00 +0000
draft: false
tags: ['Dev machine','Azure']
---


## Commands

In Azure CLI

List the subscription accounts

~~~bash
\$ az account list
~~~

Set the default subscription

~~~bash
\$ az account set --subscription mysubscription
~~~

![Function creation](/resources/_gen/images/creation.png)

Creating Function app with consomption plan

~~~bash
#!/bin/bash

# Function app and storage account names must be unique.
storageName=mystorageaccount$RANDOM
functionAppName=myserverlessfunc$RANDOM
region=westeurope

# Create a resource group.
az group create --name myResourceGroup --location $region

# Create an Azure storage account in the resource group.
az storage account create \
  --name $storageName \
  --location $region \
  --resource-group myResourceGroup \
  --sku Standard_LRS

# Create a serverless function app in the resource group.
az functionapp create \
  --name $functionAppName \
  --storage-account $storageName \
  --consumption-plan-location $region \
  --resource-group myResourceGroup \
  --functions-version 2

~~~
