### Nmap

```shell
nmap -sSUC -p111
```

#### MSRPC (Microsoft Remote Procedure Call)

```shell
nmap --script msrpc-enum -p 135 $TARGET
```

### Rpcinfo

```shell
rpcinfo $TARGET
```

```shell
rpcinfo $TARGET | grep ypbind # Probably able to list and download (and maybe upload) files (https://hacktricks.boitatech.com.br/pentesting/pentesting-rpcbind#nis)
```

#### Connection

```shell
rpcclient -N -U "" -p $PORT $TARGET # Anonymous logon (-N: No password)
```

```shell
rpcclient -U username $TARGET # Specify username
rpcclient -W WORKGROUP -U username $TARGET # -W: Workgroup
```

```shell
rpcclient -k $TARGET # -k: Kerberos authentication
```

#### Commands

```shell
srvinfo # Server info
```

```shell
enumdomains # Enumerate domains
```

```shell
enumdomusers # Enumerate domain users
```

```shell
enumdomgroups # Enumerate domain groups
```

```shell
querydominfo # Domain info
```

```shell
getusername # Current username
```

### Impacket

```shell
impacket-rpcdump -port 135 $TARGET | grep -E 'MS-EFSRPC|MS-RPRN|MS-PAR'
# MS-EFSRPC: It might be vulnerable to PetitPotam.
# MS-RPRN, MS-PAR: It might be vulnerable to PrintNightmare.
```