---
title: "Update Exchange Powershell Module"
date: 2021-05-16T18:11:27+02:00
Description: ""
Tags: ["Exchange",
"M365",]
Categories: []
DisableComments: false
---

If you try to update the Microsoft Exchange Powershell Module an get error that your administrator has blocked
this application because it potentially pose a security risk to your computer.

There is a quick fix to get pass this error:

![](/images/ps-module-error/1.png)

Open regedit and navigate to HKEY_LOCAL_MACHINE\SOFTWARE\MICROSOFT\.NETFramework\Security\TrustManager\PromptingLevel

Change Internet to Enabled:

![](/images/ps-module-error/2.png)

Then you should be able to update the module.