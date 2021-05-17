---
title: "Install Module Unable to Resolve"
date: 2020-05-20T08:52:44+02:00
Description: "If you try to install but get the error message unable to resolve package source 'https://www.powershellgallery.com/api/v2/'"
Tags: [Powershell, Reminder]
Categories: []
DisableComments: false
---
If you try to install but get the error message unable to resolve package source 'https://www.powershellgallery.com/api/v2/' then try:

```powershell
[Net.ServicePointManager]::SecurityProtocol = "tls12"
```