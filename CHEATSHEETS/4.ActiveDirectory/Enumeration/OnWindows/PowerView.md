https://raw.githubusercontent.com/PowerShellMafia/PowerSploit/refs/heads/master/Recon/PowerView.ps1
https://powersploit.readthedocs.io/en/latest/Recon/

```powershell
Import-Module .\PowerView.ps1
```

```powershell
Get-NetDomain # Get basic informations about the domain (GetCurrentDomain)
```

### Users

```powershell
Get-NetUser # List of all users in the domain (all attributes)
```

```powershell
Get-NetUser | select cn, description # Filter attributes
```

```powershell
Find-LocalAdminAccess # Find admin acces on a computer (Depending on the size of the environment, it may take a few minutes for Find-LocalAdminAccess to finish.)
```

```powershell
Get-NetSession -Verbose # Find logged users (can be filter with "-ComputerName")
```

```powershell
PsLoggedon.exe \\$TARGET # If previous command have no required permissions use this
```

```powershell
Get-NetUser -SPN | select samaccountname,serviceprincipalname # Enumerate SPNs
```

### Groups

```powershell
Get-NetGroup 'Sales Department' | select member # Get members of a group in the domain
```

### Computers

```powershell
Get-NetComputer  # Enumerate the computer objects in the domain
```

```powershell
Get-NetComputer | select operatingsystem,dnshostname # Filter result from computer object
```

### Shares

```powershell
Find-DomainShare # Enumerate shares
```

```powershell
cat \\dc1.corp.com\sysvol\corp.com\Policies\oldpolicy\old-policy-backup.xml # Read file from share
```

### ACEs

```powershell
Get-ObjectAcl -Identity stephanie # Get ACL from specific user
```

```powershell
Convert-SidToName S-1-5-21-1987370270-658905905-1781884369-1104 # It's possible to convert SID to name
```

```powershell
Get-ObjectAcl -Identity "Management Department" | Where-Object {$_.ActiveDirectoryRights -eq "GenericAll"} | Select-Object @{Name="Name";Expression={Convert-SidToName $_.SecurityIdentifier}}, ActiveDirectoryRights # Enumerate permission of all objects the domain
```
