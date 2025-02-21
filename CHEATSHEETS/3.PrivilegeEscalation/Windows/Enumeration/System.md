```powershell
hostname
```

```powershell
systeminfo
```

```powershell
set # Print environment variable
```

```powershell
net start # List services
```

```powershell
Get-Service | Where-Object { $_.Status -eq "Running" } # List running services
```

### Watch-Command.ps1

```powershell
.\Watch-Command.ps1 { Get-Process -Name *$SERVICE_NAME* | Measure } -UntilChanged # Like pspsy on Linux
```