---
title: 'Azure CLI WebApp Up'
date: Thu, 20 Mar 2021 18:00:00 +0000
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

Creating Web app with service plan with "az webapp up"

~~~bash
marc@Azure:~/weebappsite$ git clone <https://github.com/Azure-Samples/html-docs-hello-world.git>

Cloning into 'html-docs-hello-world'...
remote: Enumerating objects: 46, done.
remote: Total 46 (delta 0), reused 0 (delta 0), pack-reused 46
Unpacking objects: 100% (46/46), done.

marc@Azure:~/weebappsite$ ls
html-docs-hello-world
marc@Azure:~/weebappsite$ cd html-docs-hello-world/
marc@Azure:~/weebappsite/html-docs-hello-world$ az webapp up -l westeurope -n mywatchsite --html

az webapp up -l westeurope -n mywatchsite --html

az webapp up [--dryrun]
             [--html]
             [--ids]
             [--launch-browser]
             [--location]
             [--logs]
             [--name]
             [--os-type {Linux, Windows}]
             [--plan]
             [--resource-group]
             [--runtime]
             [--sku {B1, B2, B3, D1, F1, FREE, I1, I1v2, I2, I2v2, I3, I3v2, P1V2, P1V3, P2V2, P2V3, P3V2, P3V3, PC2, PC3, PC4, S1, S2, S3, SHARED}]
             [--subscription]

~~~
