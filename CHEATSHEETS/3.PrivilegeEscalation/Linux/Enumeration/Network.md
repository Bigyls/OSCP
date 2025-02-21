```shell
ip a # List interfaces
```

```shell
cat /etc/resolv.conf # List DNS conf
cat /etc/hosts # List DNS conf
```

```shell
arp -en # Enumerate know network hosts
arp -a # Enumerate know network hosts
```

```shell
routel # Print network routes
```

```shell
ss -lntp # List TCP open ports
ss -lnup # List UDP open ports
ss -twurp # List all active TCP and UDP connections
```

```shell
cat /etc/iptables/rules.v4 # Print firewall configuration
```

```shell
cat /etc/NetworkManager/system-connections/* |grep -E "^id|^psk" # Dump clear text PSK keys from the Network manager
```

```shell
sudo tcpdump -i lo -A | grep "pass" # Intercept network traffic that contain cleartext password
```



