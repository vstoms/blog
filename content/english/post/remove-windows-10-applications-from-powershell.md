---
title: "Remove Windows 10 Applications From Powershell"
date: 2018-07-08T08:20:16+02:00
Description: "You can remove application as Get Office, Calender and Mail from powershell, if you are using Intune. Create an script to remove the built-in applications from Windows 10."
Tags: [Intune, Powershell]
Categories: []
DisableComments: false
---
You can remove application as Get Office, Calender and Mail from powershell, if you are using Intune. Create an script to remove the built-in applications from Windows 10.

##### Calendar and Mail:
```
Get-AppxPackage *windowscommunicationsapps* | Remove-AppxPackage
```
##### Get Office:
```
Get-AppxPackage *officehub* | Remove-AppxPackage
```

##### Xbox:
```
Get-AppxPackage *xboxapp* | Remove-AppxPackage
```

##### Movies & TV:
```
Get-AppxPackage *zunevideo* | Remove-AppxPackage