```powershell
Get-History # Print history of commands
```

```powershell
(Get-PSReadlineOption).HistorySavePath # Get file path of the history
```

```powershell
Get-ChildItem -Path 'C:\' -Filter '*transcript*.txt' -Recurse -ErrorAction SilentlyContinue # Search for powershell transcript in file (like history)
```

Checks the logs in `Event Viewer` at `Windows Powershell` and events from `Script Block Logging` that are in `Application and Services -> Microsoft -> Windows -> PowerShell -> Operational` (ID: 4104).

