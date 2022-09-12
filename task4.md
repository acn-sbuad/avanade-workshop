---
layout: default
title: Task 4
nav_order: 4
---


## Deploying the functions to Azure
Until now you have been running the functions locally. This step describes how deploy the function to Azure.

![Create Azure function app in Azure](images/create-azure-function.png)

When prompted to configure your function select:

1. **Create new function app in Azure..**
2. Name: **Pick a globally unique name**
3. Runtime stack: **.NET 6**
4. Location: **Norway East**


Once the creation process is complete you should be able see your newly created function app in the [azure portal](https://portal.azure.com/#blade/HubsExtension/BrowseResource/resourceType/Microsoft.Web%2Fsites/kind/functionapp).

**Deploy the code to your newly created function app**
![Deploy project to azure funciton app](images/deploy.png)


### Trigger functions / logs in Azure portals

In order to trigger a function navigate to the trigger:

![Select trigger](images/select_trigger.png)

Then click "Code + Test"

From the "Code + Test" view you can trigger functions (1) and see live logs(2).
![Function trigger & logs](images/trigger_logs_azure.png)
