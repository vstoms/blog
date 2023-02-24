---
title: Migrate Azure AD Connect to Cloud Sync
slug: migrate-to-cloud-sync
description: null
author: null
date: 2023-02-24T08:54:23+01:00
lastmod: 2023-02-24T10:18:35.935Z
draft: true
tags:
  - Azure AD
  - Sync
  - Migration
  - Server
  - Microsoft
categories: []
---

Today we are going to migrate from Azure AD Connect to the new Cloud Sync agent.

So why sohuld we use the new Cloud Sync? 
- Support for synchronizing to an Azure AD tenant from a multi-forest disconnected Active Directory forest environment: The common scenarios include merger & acquisition (where the acquired company's AD forests are isolated from the parent company's AD forests), and companies that have historically had multiple AD forests.
- Simplified installation with light-weight provisioning agents: The agents act as a bridge from AD to Azure AD, with all the sync configuration managed in the cloud.
- Multiple provisioning agents can be used to simplify high availability deployments, particularly critical for organizations relying upon password hash synchronization from AD to Azure AD.
- Support for large groups with up to 50,000 members. It's recommended to use only the OU scoping filter when synchronizing large groups.

As 24.02.23 there are some feature that are not yet in Cloud Sync, you can find the full list at Microsoft docs [here](https://learn.microsoft.com/en-us/azure/active-directory/cloud-sync/what-is-cloud-sync#comparison-between-azure-ad-connect-and-cloud-sync)


#### Prerequisites
- AD Connect sync version 1.4.32.0 or later
- OU or group that is in scope of sync and can be used the pilot
- Source anchor should be either objectGuid or ms-ds-consistencyGUID
- The Sync Agent can be installed on Windows Server 2012 R2 or newer.