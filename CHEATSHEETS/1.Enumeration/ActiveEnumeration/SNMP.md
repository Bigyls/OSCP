### Linux

```shell
sudo nmap -sU --open -p 161 $TARGET/24
```

```shell
onesixtyone -c `fzf-wordlists` -i ips.txt # Enumerate communities
```

#### snmpcheck 

```shell
snmp-check $TARGET -c $COMMUNITY
```

#### snmpwalk

```shell
snmpwalk -c $COMMUNITY -v $VERSION $TARGET # Enumerate entire MIB tree
```

```shell
snmpwalk -c $COMMUNITY -v $VERSION $TARGET 1.3.6.1.4.1.77.1.2.25 # Enumerates the Windows users
```

```shell
snmpwalk -c $COMMUNITY -v $VERSION $TARGET 1.3.6.1.2.1.25.4.2.1.2 # Enumerate all the currently running processes
```

```shell
snmpwalk -c $COMMUNITY -v $VERSION $TARGET 1.3.6.1.2.1.25.6.3.1.2 # Query all the software that is installed on the machine
```

```shell
snmpwalk -c $COMMUNITY -v $VERSION -Oa $TARGET 1.3.6.1.2.1.2.2.1.2 # List interface name
```

```shell
snmpwalk -c $COMMUNITY -v $VERSION $TARGET 1.3.6.1.2.1.6.13.1.3 # Enumeration technique is to list all the current TCP listening ports
```

##### Extended MIB

```shell
sudo apt install snmp-mibs-downloader # Installation
sudo download-mibs # Installation
```

```shell
snmpwalk -v $VERSION -c $COMMUNITY $TARGET NET-SNMP-EXTEND-MIB::nsExtendObjects
snmpwalk -v $VERSION -c $COMMUNITY $TARGET NET-SNMP-EXTEND-MIB::nsExtendOutputFull
```