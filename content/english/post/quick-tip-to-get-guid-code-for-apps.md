---
title: "Quick Tip to Get Guid Code for Apps"
date: 2019-03-03T08:33:25+02:00
Description: "Fast way to get the GUID code from applications."
Tags: [Intune, Powershell]
Categories: []
DisableComments: false
---
```
get-wmiobject Win32_Product | Format-Table IdentifyingNumber, Name, LocalPackage -AutoSize
```