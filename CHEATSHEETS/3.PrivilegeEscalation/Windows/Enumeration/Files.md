```powershell
dir /a # Show hidden & unhidden files
Get-ChildItem -Force -Attributes Hidden,System # Show hidden & unhidden files
dir /Q # Show permissions
dir filename /s # Search filename
```

```powershell
dir C:\Users\*.txt /S /A:-D # Search for files in the home of the user (adapt for other files)
```

```powershell
Get-ChildItem -Path C:\ -Include *.kdbx,*.zip,*.pdf,*.db,*.xls*,*.doc* -File -Recurse -ErrorAction SilentlyContinue # Find all Keepass databases (adapt for other files)
```

```powershell
Get-ChildItem -Path C:\Users -Include *.kdbx,*.txt,*.zip,*.ini,*.pdf,*.db,*.xls*,*.doc* -File -Recurse -ErrorAction SilentlyContinue # Search for files in the home of the user 
```

```powershell
Get-ChildItem -Path 'C:\Users' -Filter '*.txt' -Recurse | Select-String -Pattern 'password' -ErrorAction SilentlyContinue # Search for words in file (like grep)
```

The icacls utility outputs the corresponding principals and their permission mask.[4](https://portal.offsec.com/courses/pen-200-44065/learning/windows-privilege-escalation-45276/leveraging-windows-services-185051/service-binary-hijacking-45284#fn-local_id_62-4) The most relevant permissions and their masks are listed below:

|Mask|Permissions|
|---|---|
|F|Full access|
|M|Modify access|
|RX|Read and execute access|
|R|Read-only access|
|W|Write-only access|

```powershell
icacls "C:\xampp\apache\bin\httpd.exe"
```