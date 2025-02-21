### Fingerprinting

```shell
nmap -p $PORT --script=http-enum $TARGET
```

#### wappalyzer

- [https://www.wappalyzer.com/](https://www.wappalyzer.com/) (plugin in Firefox)

#### Whatweb

```shell 
whatweb http://$TARGET
```

### Debugging page content

Developer tools embedded in navigators:
- Inspector
- Console
- Network
- Storage
- ...

### nikto

```shell
nikto -host $TARGET -port $PORT -C all
```

### ffuf

/robots.txt
/.git/

#### Wordlists

```shell
/usr/share/dirb/wordlists/common.txt
/usr/share/dirb/wordlists/big.txt
/opt/seclists/Discovery/Web-Content/directory-list-2.3-big.txt
```

```shell
ffuf -c -w `fzf-wordlists` -u "http://$TARGET/FUZZ" -e .php,.html,.txt,.pdf,.xml,.aspx,.bak,.config # Simple directory brute force with extensions
ffuf -c -w `fzf-wordlists` -u "http://FUZZ.$TARGET" # subdomain enumeration
ffuf -c -w `fzf-wordlists` -u "http://$TARGET/?FUZZ=test_value" -fc 401 # GET parameter brute force with filter on HTTP response
ffuf -w /usr/share/SecLists/Usernames/top-usernames-shortlist.txt -X POST -d "username=FUZZ&&password=x" -H "Content-Type: application/x-www-form-urlencoded" -u http://mydomain.com/login -mr "username already exists" # Find usernames
ffuf -c -w `fzf-wordlists` -u "http://$TARGET/login.php" -X POST -d "username=admin\&password=FUZZ" -fc 401 # Brute force password
```

### API

```shell
gobuster dir -u http://192.168.50.16:5002 -w /usr/share/wordlists/dirb/big.txt -p pattern.txt # pattern.txt contain : {GOBUSTER}/v1\n {GOBUSTER}/v2
```

### CMSs

#### Wordpress

```shell
wpscan --url http://site.com/wordpress --api-token <your_token> --enumerate u,vp --plugins-detection aggressive
```

#### Joomla

```shell
python main.py -u $TARGET # https://github.com/oppsec/juumla
```

#### Drupal

```shell
droopescan scan drupal -u $TARGET -t 32 # https://github.com/SamJoan/droopescan
```

#### Magento

```shell
php magescan.phar scan:all $TARGET # https://github.com/steverobbins/magescan
```
