### TCP

```shell
nmap -v --script 'ftp-*' -p 21 $TARGET
```

```shell
ftp $USERNAME@$TARGET $PORT
binary # Binrary transfer
ascii # ASCII transfer
```

```shell
wget -r ftp://$USERNAME:$PASSWORD@$TARGET # Dump all
```

### UDP

```shell
nmap -sU -p 69 --script tftp-enum $TARGET
```

```shell
nmap -sU -p 69 --script tftp-enum.nse --script-args tftp-enum.filelist=`fzf-wordlists` $TARGET
```