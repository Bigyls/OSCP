### Nmap

```shell
nmap -v -sV -p 111 --script rpcinfo $TARGET  # Get NFS version
```

```shell
nmap -v -p 111 --script nfs* $TARGET # View NFS shared directories
```

```shell
rpcinfo $TARGET | grep nfs # Get info to NFS
```

### Mount

```shell
showmount -e $TARGET # List mounts
```

```shell
mkdir /tmp/nfs_folder
mount -t nfs -o vers=4 <IP>:/folder /tmp/nfs_folder -o nolock # Mount NFS folder on machine
```

### Configuration files

```
/etc/exports
/etc/lib/nfs/etab
```

