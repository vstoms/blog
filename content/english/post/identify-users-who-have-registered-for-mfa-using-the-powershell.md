---
title: "Identify Users Who Have Registered for Mfa Using the Powershell"
date: 2018-06-26T08:43:48+02:00
Description: "Identify users who have registered for MFA"
Tags: [Powershell, MFA, M365]
Categories: []
DisableComments: false
---
Identify users who have registered for MFA:
```
Get-MsolUser -All | where {$_.StrongAuthenticationMethods -ne $null} | Select-Object -Property UserPrincipalName
```

Identify users who have not registered for MFA:
```
Get-MsolUser -All | where {$_.StrongAuthenticationMethods.Count -eq 0} | Select-Object -Property UserPrincipalName
```