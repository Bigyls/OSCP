### Bash

```shell
for i in {1..65535}; do (echo > /dev/tcp/$TARGET/$i) >/dev/null 2>&1 && echo $i is open; done
```

### PowerShell

```powershell
1..1024 | % {echo ((new-object Net.Sockets.TcpClient).Connect(“$TARGET”,$_)) “Port $_ is open”} 2>$null
```

### NetCat

#### TCP

```shell
for i in {1..65535}; do nc -nv -w 1 -z 1$TARGET $i 2>&1 | grep "Connected"; done
```

#### UDP

```shell
for i in {1..65535}; do nc -nv -u -z -w 1 $TARGET $i 2>&1 | grep "UDP packet sent successfully"; done # Didn't work well
```

### Nmap

#### TCP

```shell
nmap -v -p- $TARGET # Scan all ports
```

```shell
TARGET=X.X.X.X; SCAN_NAME=XXX; PORTS=$(nmap -Pn -p- $TARGET | grep "/tcp" | cut -d '/' -f1 | paste -sd ',' -); echo $PORTS; nmap -v -A -O -sC -sT -sV -Pn -T5 -oA "$SCAN_NAME"_tcp --script vuln --osscan-guess -p $PORTS $TARGET
```

```shell
for ip in $(dig l$DOMAIN_NAME +short);do nmap -sC -sV -Pn $TARGET; done # SCan IP from DNS
```

#### UDP

```shell
nmap -v -sU --open --min-rate 5000 $TARGET/24 # Rapid (but maybe not fully trusted) Nmap UDP on all ports and precise all ports on specific machine
```

```shell
nmap -v -sU -sS --top-port 100 $TARGET# UDP Scan ++
```

```shell
TARGET=X.X.X.X; SCAN_NAME=XXX; PORTS=$(nmap -Pn -p- -sU --open --min-rate 5000 $TARGET | grep "/udp" | cut -d '/' -f1 | paste -sd ',' -); echo $PORTS; nmap -v -A -O -sC -sU -sV -Pn -oA "$SCAN_NAME"_udp --script vuln --osscan-guess -p $PORTS $TARGET
```

#### NSE scripts

Add script to `/usr/share/nmap/scripts/script.nse.`

```shell
nmap --script-updatedb # Update DB
```

```shell
nmap --script $NEW_SCRIPT $TARGET
```