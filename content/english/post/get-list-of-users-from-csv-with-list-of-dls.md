---
title: "Get List of Users From Csv With List of Dls"
date: 2018-06-26T11:03:18+02:00
Description: "Powershell script export users in groups"
Tags: [Microsoft, M365, Self-Reminder]
Categories: []
DisableComments: false
---
Header in the csv file should be DL

```powershell
$PathToCsv = "groups.csv"

Import-Csv $PathToCsv |
    ForEach-Object {

        $group = $null

        $group = $_.DL
        Get-ADGroupMember $group |
            Select-Object samaccountname |
            ForEach-Object {

                New-Object psobject -Property @{
                    DL = $group
                    UserName = $_.samaccountname
                }
            }
    } |
    Export-Csv -NoTypeInformation "output.csv"
```