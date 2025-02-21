```powershell
Get-ExecutionPolicy -Scope CurrentUser # Get policy
```

```powershell
Set-ExecutionPolicy -ExecutionPolicy Unrestricted -Scope CurrentUser
```

```powershell
powershell -command "Add-MpPreference -ExclusionPath 'C:\Users\Public\Downloads' -ExclusionExtension '.exe'"
```