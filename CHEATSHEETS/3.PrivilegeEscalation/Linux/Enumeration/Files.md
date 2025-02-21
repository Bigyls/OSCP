```shell
[ -w /etc/passwd ] && echo "VULNERABLE!" || echo "Not vulnerable" # Check if /etc/passwd is writable
```

```shell
find / -writable -type d 2>/dev/null # Print writable directories
```

```shell
find / -perm -u=s -type f 2>/dev/null # Print SUID-marked files
```

https://github.com/lypd0/SUIDump

```shell
find / -perm -g=s -type f 2>/dev/null # Print GUID-marked files
```

```shell
find / -perm -1000 -type d 2>/dev/null # Find sticky bit
```

```shell
find -perm -2 type -f 2>/dev/null # Files write access for any user
```

```shell
cat .bashrc
```

```shell
grep 'pass*' /etc/*.conf 2> /dev/null # Grep for interesting keywords in configuration files
grep 'key' /etc/*.conf 2> /dev/null # Grep for interesting keywords in configuration files
grep 'secret' /etc/*.conf 2> /dev/null # Grep for interesting keywords in configuration files
```

```shell
find /* -name *.*history* -print 2> /dev/null # Try to read other users history files
find /* -iname *.pdf 2>/dev/null
find /home/* -iname *.kdbx,*.txt,*.zip,*.ini,*.pdf,*.db,*.xls*,*.doc* 2>/dev/null
```


### SSH Keys

Check for all homes
```shell
cat ~/.ssh/authorized_keys
cat ~/.ssh/identity.pub
cat ~/.ssh/identity
cat ~/.ssh/id_rsa.pub
cat ~/.ssh/id_rsa
cat ~/.ssh/id_dsa.pub
cat ~/.ssh/id_dsa
cat ~/.ssh/id_ecdsa
cat ~/.ssh/id_ecdsa.pub
cat ~/.ssh/id_ecdsa-sk
cat ~/.ssh/id_ecdsa-sk.pub
cat ~/.ssh/id_ed25519
cat ~/.ssh/id_ed25519.pub
cat ~/.ssh/id_eddsa
cat ~/.ssh/id_eddsa.pub
cat ~/.ssh/id_ed25519-sk
cat ~/.ssh/id_ed25519-sk.pub
cat /etc/ssh/ssh_config
cat /etc/ssh/sshd_config
cat /etc/ssh/ssh_host_dsa_key.pub
cat /etc/ssh/ssh_host_dsa_key
cat /etc/ssh/ssh_host_rsa_key.pub
cat /etc/ssh/ssh_host_rsa_key
cat /etc/ssh/ssh_host_key.pub
cat /etc/ssh/ssh_host_key
```
