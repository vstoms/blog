---
title: "Enabling Debug Logging for the Netlogon Service"
date: 2017-12-12T11:07:15+02:00
Description: ""
Tags: [Windows, Microsoft, Self-Reminder]
Categories: []
DisableComments: false
---
Here is a easy way to find out where the user is trying to logon to. Great way to find out why they always have account lockout.

To enable netlogon logging: `Nltest /DBFlag:2080FFFF`

An log under %windir%\\debug\\netlogon.log will be created and here we can see where the user is trying to logon to.

To disable netlogon logging: `Nltest /DBFlag:0x0`