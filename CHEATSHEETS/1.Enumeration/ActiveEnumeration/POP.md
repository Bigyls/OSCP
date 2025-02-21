```shell
nmap -v --script pop3-capabilities,pop3-ntlm-info -sV -p 110 $TARGET
```

### Login

```shell
telnet $TARGET 110
USER $USERNAME
PASS $PASSWORD
```

```shell
list # List messages
```

```shell
retr 1 # Show message 1
```