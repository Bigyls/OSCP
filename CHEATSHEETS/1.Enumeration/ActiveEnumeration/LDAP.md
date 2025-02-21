### Nmap

```shell
nmap -v -n -sV --script "ldap* and not brute" $TARGET
```

### NetExec

```shell
nxc ldap $TARGET -u $USERNAME -p $PASSWORD --users # Enumerate users
```

```shell
nxc ldap $TARGET -u $USERNAME -p $PASSWORD --active-users # Enumerate just active users
```

```shell
nxc ldap $TARGET -u $USERNAME -p $PASSWORD -k --get-sid # Get domain SID
```

### Ldapsearch

```shell
ldapsearch -h $TARGET -bx "DC=DOMAIN,DC=COM"
```

### Windapsearch

```shell
windapsearch --dc $TARGET --module users
```
