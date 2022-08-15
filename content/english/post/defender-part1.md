---
title: Defender For Server - Licesning
slug: defender-for-server-licensing
description: null
author: null
date: '2022-08-14T07:38:02.997Z'
lastmod: '2022-08-14T07:38:47.148Z'
draft: false
tags:
    - Defender
    - Install
    - Security
    - Server
    - Microsoft
categories: []
---

![Defender for Server](/images/Defender.png "Defender for Server")


This is a miniseries about Microsoft Defender for Server, this series will be around licenses/requirements **this article**, how to onboard Servers, and tips around troubleshooting.

So why am I writing a miniseries about Defender for Server? Due to the last year, many people have migrated or are going to migrate to Defender for Server, so having gained some experience in this field lately, I want to document the journey.

**Warning**: I`m not a license expert, consult with your license partner if you need to get exact information about your license need.

### License
To begin this series, we have to start with the boring stuff and for many this is licenses. Microsoft is known for a jungle of different license options to choose from.

From previous solutions, it has been normal to pay for the number of servers you wanted to protect. Microsoft has now made some changes to this (asking which solution you get, we will return to this later). You need a license anyway, but there are several ways to obtain these. I will try to describe these so that you can make the right choice.

For those who currently have licenses for Defender for Endpoint (Windows 10/11). then the standalone versions of Defender for Endpoint Plan 1 and Plan 2 do not include server licenses. To onboard servers to those plans, you'll need Defender for Servers Plan 1 or Plan 2.

#### "Old way to get the licenses"
In order to be eligible to purchase Microsoft Defender for Endpoint Server SKU, you must have already purchased a combined minimum of any of the following, Windows E5/A5, Microsoft 365 E5/A5 or Microsoft 365 E5 Security subscription licenses. 

Microsoft Defender for Endpoint Server is an add-on for customers with a combined minimum of 50 licenses of eligible Microsoft Defender for Endpoint SKUs. 
This depending on what program you are on, the get the correct answer look up at [Microsoft Product Terms](https://www.microsoft.com/licensing/terms/productoffering/MicrosoftDefenderforEndpointServer/EAEAS).

There is no need/way to assign this to any servers that you have, but as long you have the correct amount of licenses then you are covered.

#### "The modern way"
If you are a small shop and can`t afford 50 SKU of M365 E5 to get Defender for Server, you can use Microsoft Defender for Cloud. 

Microsoft Defender for Cloud is a Cloud Security Posture Management (CSPM) and Cloud Workload Protection Platform (CWPP) for all of your Azure, on-premises, and multicloud (Amazon AWS and Google GCP) resources. Defender for Cloud fills three vital needs as you manage the security of your resources and workloads in the cloud and on-premises:

- [Defender for Cloud secure score](https://docs.microsoft.com/en-us/azure/defender-for-cloud/secure-score-security-controls)
- [Defender for Cloud recommendations](https://docs.microsoft.com/en-us/azure/defender-for-cloud/security-policy-concept)
- [Defender for Cloud alerts](https://docs.microsoft.com/en-us/azure/defender-for-cloud/alerts-overview)

In Defender for Cloud, you will easily just enable Defender for Servers and your servers that are running in Azure will be onboarded to Defender. We also have the options to choose between plan 1 and 2, this will be covered later on.

If you use Defender for Cloud to get Defender for Server, you will only pay as long the server is up and running. P1 - $0.007/Server/hour and P2 - $0.02/Server/hour
Included data - 500 MB/day.

![Defender for Cloud](/images/defender-miniseries/DefenderCloud.png "Defender for Cloud")

If you have servers hosted in your on-premises, AWS or GCP this will be covered in the next blog post.

#### Plans?
You can choose from two different plans in Defender for Server:

**Plan 1**

**MDE Integration**: Plan 1 integrates with Microsoft Defender for Endpoint Plan 2 to provide a full endpoint detection and response (EDR) solution for machines running a range of operating systems. Defender for Endpoint features include:
- Reducing the attack surface for machines.
- Providing antivirus capabilities.
- Threat management, including threat hunting, detection, analytics, and automated investigation and response.

**Licensing**: Charges Defender for Endpoint licenses per hour instead of per seat, lowering costs by protecting virtual machines only when they are in use.

**Provisioning**: Automatically provisions the Defender for Endpoint sensor on every supported machine that's connected to Defender for Cloud.

**Plan 2**

Includes everything in Defender for Servers Plan 1.

**Additional features**: All other enhanced Defender for Servers security capabilities for Windows and Linux machines running in Azure, AWS, GCP, and on-premises.

Next up will be about old vs new agents and how to onboard Defender for Server for your servers.