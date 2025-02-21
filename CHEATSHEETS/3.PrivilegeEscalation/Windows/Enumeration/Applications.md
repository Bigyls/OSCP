```powershell
Get-Process # "tasklist" in cmd.exe
```

```powershell
wmic product get name,version,vendor # List installed apps
```

```powershell
Get-ItemProperty 'HKLM:\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Uninstall\*' | select displayname # Print installed applications (32-bits) REMOVE DISPLAYNAME TO GET MORE INFORMATIONS
```

```powershell
Get-ItemProperty 'HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Uninstall\*' | select displayname # Print installed applications (64-bits) REMOVE DISPLAYNAME TO GET MORE INFORMATIONS
```

```powershell
wmic process where "name='file.exe'" get ExecutablePath # Get path from exe
```