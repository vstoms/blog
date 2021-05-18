---
title: "Gather Windows Autopilot Device Data"
date: 2019-05-14T08:45:13+02:00
Description: "Gather Windows Autopilot Device Data"
Tags: [Powershell, Intune, Autopilot]
Categories: []
DisableComments: false
---
[Link to powershell script ](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)

##### Export Computer AutoPilot Data
```
.\Get-WindowsAutoPilotInfo.ps1 -ComputerName MYCOMPUTER -OutputFile .\MyComputer.csv
```

##### Append Computer AutoPilot Data
```
.\Get-WindowsAutoPilotInfo.ps1 -ComputerName MYCOMPUTER -OutputFile .\MyComputer.csv -Append
```

##### Export AutoPilot Data from a SCCM Collection
```
Get-CMCollectionMember -CollectionName "All Systems" | .\GetWindowsAutoPilotInfo.ps1 -OutputFile .\MyComputers.csv
```

##### Export AutoPilot Data from a Active Directory
```
Get-ADComputer -Filter * | .\GetWindowsAutoPilotInfo.ps1 -OutputFile .\MyComputers.csv