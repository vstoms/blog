---
title: How to onboard server to Azure Arc
slug: onboard-servers-to-azure-arc
description: null
author: null
date: 2022-12-17T12:09:53+01:00
lastmod: '2022-12-17T12:09:53+01:00'
draft: false
tags:
    - Defender
    - Install
    - Security
    - Server
    - Microsoft
categories: []
---

Onboarding Windows servers to Azure Arc allows you to manage your on-premises and edge Windows servers using the same Azure portal and tools that you use for cloud-based servers. In this blog post, we will outline the steps to onboard your Windows servers to Azure Arc.

#### Before you begin, you need to have the following:
- An Azure account
- An Azure subscription
- Access to the servers you want to onboard

#### To use Azure Arc on Windows servers, the following requirements must be met:
- Windows Server version: Azure Arc currently supports Windows Server 2016 and later versions.
- Azure Arc agent: The Azure Arc agent must be installed on the Windows server.
- Networking: The Windows server must have internet connectivity to be able to communicate with Azure services.
- Azure subscription: You need an Azure subscription to use Azure Arc.
- Permissions: You must have the necessary permissions to register the Windows server with Azure Arc and manage it using Azure tools.

In addition to the above requirements, there may be additional requirements depending on the specific Azure Arc features you want to use. For example, to use Azure Arc enabled Kubernetes, you need to have the Kubernetes CLI (kubectl) installed on the Windows server.


### Step 1: Install the Azure Arc agent

To onboard your Windows servers to Azure Arc, you need to install the Azure Arc agent on each of the servers you want to manage. You can download the Azure Arc agent from the Azure portal or use the following PowerShell command to install it:

```powershell
Invoke-WebRequest -Uri https://aka.ms/installazurearc | Invoke-Expression
```

### Step 2: Register the servers with Azure Arc

Once the Azure Arc agent is installed, you need to register the servers with Azure Arc. To do this, go to the Azure portal and navigate to the Azure Arc dashboard. Click on the "Add" button to add a new server. You will be prompted to enter the FQDN (fully qualified domain name) or the IP address of the server, as well as the login credentials.

### Step 3: Assign tags and resource groups to the servers

After the server is registered with Azure Arc, you can assign tags and resource groups to it to help with organization and management. To do this, select the server in the Azure Arc dashboard and click on the "Edit" button. You can then add tags and assign the server to a resource group.

### Step 4: Manage the servers

Once your Windows servers are onboarded to Azure Arc, you can manage them using the same tools and processes you use for managing cloud-based servers in Azure. This includes the ability to deploy Azure policies, run Azure Arc enabled Kubernetes, and use Azure Monitor to track the performance and health of your servers.

In summary, onboarding Windows servers to Azure Arc allows you to manage your on-premises and edge Windows servers using the same Azure tools and processes you use for cloud-based servers. By installing the Azure Arc agent, registering the servers with Azure Arc, assigning tags and resource groups, and using Azure tools to manage the servers, you can streamline the management of your hybrid infrastructure.

### How to offboard the server form Azure Arc

To offboard a Windows server from Azure Arc, you can follow these steps:

- Navigate to the Azure Arc dashboard in the Azure portal.
- Select the Windows server you want to offboard from the list of servers.
- Click on the "More actions" button and select "Delete" from the dropdown menu.
- Confirm the deletion by clicking on the "Delete" button.

Note that offboarding a Windows server from Azure Arc will not delete the server itself, but it will remove the server from Azure Arc management. The server will no longer be visible in the Azure Arc dashboard and you will not be able to use Azure tools to manage it.

Alternatively, you can use the following Azure CLI command to offboard a Windows server from Azure Arc:

```Azure
az resource delete --resource-type Microsoft.HybridCompute/machines --name <server-name> --resource-group <resource-group>
```

Replace server-name with the name of the Windows server and resource-group with the name of the resource group the server belongs to.

Offboarding a Windows server from Azure Arc is a one-way process and cannot be undone. Make sure you really want to offboard the server before you proceed.