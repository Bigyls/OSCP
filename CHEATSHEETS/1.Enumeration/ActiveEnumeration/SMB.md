### Linux

https://github.com/p0dalirius/DumpSMBShare

```shell
nmap -v -A -O -sC -sV -Pn --osscan-guess --script 'smb-enum*' -p 139,445 $TARGET
```

```shell
nbtscan -r $TARGET/24
```

#### Enum4linux

```shell
enum4linux -A $TARGET
```

#### NetExec

```shell
nxc smb $TARGET -u '' -p '' # Null session enumeration
nxc smb $TARGET -u '' -p '' --shares
nxc smb $TARGET -u '' -p '' --pass-pol
nxc smb $TARGET -u '' -p '' --users
nxc smb $TARGET -u '' -p '' --groups
```

```shell
nxc smb $TARGET -u 'guest' -p '' # Guest session enumeration
nxc smb $TARGET -u 'guest' -p '' --shares
nxc smb $TARGET -u 'guest' -p '' --pass-pol
nxc smb $TARGET -u 'guest' -p '' --users
nxc smb $TARGET -u 'guest' -p '' --groups
```

```shell
nxc smb $TARGET -d $DOMAIN -u 'guest' -p '' # Guest session enumeration
nxc smb $TARGET -d $DOMAIN -u 'guest' -p '' --shares
nxc smb $TARGET -d $DOMAIN -u 'guest' -p '' --pass-pol
nxc smb $TARGET -d $DOMAIN -u 'guest' -p '' --users
nxc smb $TARGET -d $DOMAIN -u 'guest' -p '' --groups
```

```shell
nxc smb $TARGET/24 -u $USERNAME -p $PASSWORD --rid-brute # brute force RIDs
```

```shell
nxc smb $TARGET/24 -u $USERNAME -p $PASSWORD --local-group # Enumerate local groups
```

```shell
nxc smb $TARGET/24 -u $USERNAME -p $PASSWORD --pass-pol # Enumerate password policy
```

```shell
nxc smb $TARGET/24 -u $USERNAME -p $PASSWORD -M enum_av # Enumerate anti-virus & EDR
```

```shell
nxc smb $TARGET/24 -u $USERNAME -p $PASSWORD --sessions # Enumerate active sessions
```

```shell
nxc smb $TARGET/24 -u $USERNAME -p $PASSWORD --shares --filter-shares READ WRITE # Enumerate only readable or writable shares
```

```shell
nxc smb $TARGET/24 -u $USERNAME -p $PASSWORD --interfaces # Enumerate interfaces
```

```shell
nxc smb $TARGET/24 -u $USERNAME -p $PASSWORD --disks # Enumerate disks
```

```shell
nxc smb $TARGET/24 -u $USERNAME -p $PASSWORD --loggedon-users # Enumerate logged users
```

```shell
nxc smb $TARGET/24 -u '' -p '' --disks
nxc smb $TARGET/24 -u 'guest' -p '' --shares
nxc smb $TARGET/24 -u $USERNAME -p $PASSWORD --shares
```

```shell
nxc smb $TARGET -u 'guest' -p '' -M spider_plus -o DOWNLOAD_FLAG=True # Dump all shares (like DumpSMBShare)
```

#### DumpSMBShare

```shell
DumpSMBShare.py '$USERNAME:$PASSWORD@$TARGET' -s $SHARE
```

### Windows

```powershell
net view \\dc01 /all
```