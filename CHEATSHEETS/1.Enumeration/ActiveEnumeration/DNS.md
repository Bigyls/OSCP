### Locating the host records for the domain

```shell
host $DOMAIN_NAME # By default is A record
```

Get specific record of hostname:
```shell
host -t $DNS_RECORD $DOMAIN_NAME # $DNS_RECORD is like MX, TXT, ...
```

```shell
host -t ns $DOMAIN_NAME | cut -d " " -f 4 | sed 's/\.$//' # Get DNS servers for a given domain
```

```shell
for ip in $(cat `fzf-wordlists`); do host $TARGET.$DOMAIN_NAME; done | grep -v "not found" # Forward lookup brute force
```

```shell
for NS in $(host -t ns $DOMAIN_NAME | cut -d ' ' -f 4 | cut -d '.' -f 1); do host -l $DOMAIN_NAME $NS.$DOMAIN_NAME; done # Aumotamted DNS zone transfer for each name server
```

### DNSRecon

```shell
dnsrecon -d $DOMAIN_NAME -t $DNS_RECORD # Basic request
dnsrecon -d $DOMAIN_NAME -D `fzf-wordlists` -t brt # DNS zone transfer 
```

### DNSEnum
```shell
dnsenum $DOMAIN_NAME
```
