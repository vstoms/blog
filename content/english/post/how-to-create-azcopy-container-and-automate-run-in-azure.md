---
title: "How to Create Azcopy Container and Automate Run in Azure"
date: 2019-03-12T08:30:29+02:00
Description: "Was working on an case where the customer wanted to copy files within an Azure blob to another blob every nigth."
Tags: [Microsoft, Azure, Powershell]
Categories: []
DisableComments: false
---
Was working on an case where the customer wanted to copy files within an Azure blob to another blob every nigth.


This is the way I wen`t to solve this:

1. Create an Azure Container instance with AzCopy.
2. Create an Azure Runbook to start the Container.


To create the Azure Container with AzCopy:

```
az account list --output table
az account set --subscription "Sub"
az container create -g RG-Azcopy --name azcopy --image vstoms/azcopy:latest --os-type Linux --restart-policy Never --command-line "azcopy --source Blob --destination Blob --source-key key --dest-key Key --recursive --exclude-older --quiet"
```

You have to have an Resource Group first, I have called this RG-Azcopy, and I`m using Docker image hawaku/azcopy.


To get your source key, go to the blob and open Access keys and copy your key:


![](/images/image.png)


Now we have an Azure Container instance with AzCopy, you could run the Container manually. But we will create an Azure Runbook to run this Container every nigth.


First create an Automation Account, and then create an runbook.


![](/images/image-1.png)



And the code to start the Azure Container

```
$Conn = Get-AutomationConnection -Name 'AzureRunAsConnection'

Add-AzureRMAccount -ServicePrincipal -Tenant $Conn.TenantID -ApplicationID $Conn.ApplicationID -CertificateThumbprint $Conn.CertificateThumbprint

Invoke-AzureRmResourceAction -ResourceGroupName RG-Azcopy -ResourceName azcopy -Action Start -ResourceType Microsoft.ContainerInstance/containerGroups -Force
```