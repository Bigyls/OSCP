### Nmap

```shell
nmap -sn $TARGET/24
```

```shell
nmap -sn $TARGET/24 | grep -oE '\b([0-9]{1,3}\.){3}[0-9]{1,3}\b' # Get host up IPs from network
```

- https://github.com/andrew-d/static-binaries/tree/master/binaries

### Ping Sweep 

#### Bash

```shell
for i in {1..255};do (ping -c 1 192.168.0.$i | grep "bytes from" &); done
```

#### PowerShell 

```shell
for ($i=1;$i -lt 255;$i++) { ping -n 1 192.168.0.$i| findstr "TTL"}
```

### NetExec

```shell
nxc smb $TARGET/24
```

```shell
nxc smb $TARGET/24 --gen-relay-list relay_list.txt # Maps the network of live hosts and saves a list of only the hosts that don't require SMB signing.
```

### ARP

```shell
arp -a
```
