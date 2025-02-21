```powershell
ipconfig /all
```

```powershell
arp -a # Enumerate know network hosts
```

```powershell
route print # Print the routing table
```

```powershell
netstat /a
netstat -ano # List all active network connections
```

```powershell
netsh firewall show state # Look for firewall
netsh firewall show config
```

```shell
nxc smb $TARGET -u $USERNAME -p $PASSWORD # Try all connection possibilities
nxc rdp $TARGET -u $USERNAME -p $PASSWORD
nxc winrm $TARGET -u $USERNAME -p $PASSWORD
```
