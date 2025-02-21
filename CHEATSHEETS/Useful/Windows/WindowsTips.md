---
status: todo
tags:
  - CheatSheet
  - Windows
  - ReverseShell
  - PowerShell
created_date: Tuesday 23 April 2024 (11:02)
---
# Tips


## FindNETFrameworkVersion

`reg query "HKLM\SOFTWARE\Microsoft\Net Framework Setup\NDP" /s`

## Bypass execution policy without problems

```powershell
Set-ExecutionPolicy -ExecutionPolicy bypass -Scope process
```

## Add windows defender exception

```shell
Add-MpPreference -ExclusionPath 'C:\Users\USERNAME\Downloads' -ExclusionExtension '.exe'
```

## Turn off windows defender

```powershell

```