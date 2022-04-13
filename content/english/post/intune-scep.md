---
title: "Intune Scep"
date: 2021-10-19T08:41:33+02:00
Description: "A reminder how to install and setup SCEP for Intune"
Tags: ["Intune","Scep","NDES","Certificate"]
Categories: []
DisableComments: false
---

A quick blog that describes how to set up Intune SCEP.  This guide is based on the blog [msendpointmgr.com](https:/msendpointmgr.com) which has described this very well. Here much of the same will be described but also how the new Intune Connector works.

#### What is SCEP
Intune supports use of the Simple Certificate Enrollment Protocol (SCEP) to authenticate connections to your apps and corporate resources. SCEP uses the Certification Authority (CA) certificate to secure the message exchange for the Certificate Signing Request (CSR). When your infrastructure supports SCEP, you can use Intune SCEP certificate profiles (a type of device profile in Intune) to deploy the certificates to your devices. The Certificate Connector for Microsoft Intune is required to use SCEP certificate profiles with Intune when you also use an Active Directory Certificate Services Certification Authority, also called a Microsoft CA

#### Prerequisites
 - Working internal PKI
 - Network Device Enrollment Service (NDES) server
 - Intune Certificate Connector (installed on the NDES server)
 - Member server for Azure AD Application Proxy (Could be installed on the NDES server)
 - Certificate templates.
 - Service account