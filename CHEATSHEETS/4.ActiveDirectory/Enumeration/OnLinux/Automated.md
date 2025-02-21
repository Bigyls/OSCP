### NXC

```shell
nxc ldap $TARGET -u $USERNAME -p $PASSWORD --bloodhound --collection All --dns-server $TARGET
```

### Bloodhound-python

```shell
bloodhound.py --zip -c All -d $DOMAIN -u $USERNAME -p $PASSWORD -dc DCXX.$DOMAIN -gc $DOMAIN -ns $TARGET -v # --dc is based on hosts entry like "92.168.151.161 dc01.poseidon.yzx"
```

### Rusthound

```shell
rusthound -d $DOMAIN -i $TARGET -u $USERNAME@$DOMAIN -p $PASSWORD --zip --old-bloodhound
```
