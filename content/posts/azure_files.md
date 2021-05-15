---
title: 'Azure Storage MS Learn'
date: 2021-03-22T22:38:42+01:00
tags: ['Dev machine','Azure']
draft: true
---

Dans cet exercice, vous allez d’abord créer un compte de stockage et deux partages de fichiers pour les rapports et les données d’application. Vous allez ensuite créer une machine virtuelle Windows à utiliser comme exemple de machine cliente. Vous utiliserez la machine virtuelle Windows pour monter les lecteurs où vous accéderez aux partages de fichiers. Pour finir, vous mapperez deux lecteurs aux nouveaux partages de fichiers Azure et vous y copierez des rapports.

## Créer un compte de stockage GRS

Créez un compte de stockage en utilisant la commande CLI.

Azure CLI

~~~bash
export STORAGEACCT=learnazurefileshare$RANDOM

az storage account create \
    --name $STORAGEACCT \
    --resource-group learn-c9584804-9995-4e5f-953d-c90a396dd33a \
    --sku Standard_GRS
~~~

À l’aide des commandes Azure CLI, enregistrez la clé de compte de stockage dans une variable locale.

Azure CLI

~~~bash
STORAGEKEY=$(az storage account keys list \
    --resource-group learn-c9584804-9995-4e5f-953d-c90a396dd33a \
    --account-name $STORAGEACCT \
    --query "[0].value" | tr -d '"')
~~~

## Créer des partages de fichiers

1. Créez un partage de fichiers pour stocker les rapports de la société financière.

Azure CLI

~~~bash
az storage share create \
    --account-name $STORAGEACCT \
    --account-key $STORAGEKEY \
    --name "reports"
~~~

1. Créez un partage de fichiers pour stocker les données d’application de la société financière.

~~~bash
az storage share create \
    --account-name $STORAGEACCT \
    --account-key $STORAGEKEY \
    --name "data"
~~~

marco_ml_1@Azure:~$ echo $STORAGEKEY
XXXXXXXXXXXXXXX
marco_ml_1@Azure:~$ echo $STORAGEACCT
learnazurefileshareXXXXX

etc.
