```shell
nmap -v --script rdp-ntlm-info,rdp-enum-encryption,rdp-vuln-ms12-020 -p 3389 -T4 $TARGET # Enumerate RDP protocol
```

### Check credentials 

```shell
rdp_check $DOMAIN_NAME/$USERNAME:$PASSWORD@$TARGET
```

### Connection to RDP

```shell
xfreerdp /u:$USERNAME /p:$PASSWORD +clipboard /dynamic-resolution /cert:ignore /v:$TARGET /drive:share,/tmp
```

```shell
rdesktop -u $USERNAME $TARGET
```
