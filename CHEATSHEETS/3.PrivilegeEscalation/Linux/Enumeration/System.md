```shell
uname -a # Get machine name, kernel version, ...
```

```shell
id # Check user and his groups
```

```shell
ls -la /.dockerenv # Check if it's docker container
```

```shell
cat /etc/passwd # Enumerate users
for user in $(cat /etc/passwd | cut -f1 -d ":"); do id $user; done # All users with UID and GUID informations
cat /etc/passwd |cut -f1,3,4 -d":" | grep "0:0" |cut -f1 -d":" |awk '{print $1}' # List all current users
```

```shell
cat /etc/shadow # Try to read shadow
```

```shell
cat /etc/group # Lok for groups
```

```shell
cat /etc/knockd.conf # Port knocking conf
```

```shell
last # Connection history
w # Who is connected
```

```shell
env # Print environment variable
```

```shell
echo $PATH | tr ":" "\n" # List path
```

```shell
ps -faux # List processes
```

```shell
sudo -l # Print allow comand to run as root
```

```shell
lsmod # Enumerate loaded kernel module 
```

```shell
/sbin/modinfo $MODULE_NAME # Info on specific module
```

```shell
aa-enabled # Check AppAmrmor status
aa-status # Check AppAmrmor status
```

