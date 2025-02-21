---
tags:
  - OSCP
  - Checklist
created_date: Monday 06 January 2025 (21:19)
---
# Stucked

## ENUMERATE EVERYTHING

Enumeration is the foundation of every successful exploit. The TCP and UDP scan all on port is done ? Look for web title, anything else, it's impossible to not find hint.

## MACHINE NAMES CAN HELP TO FIND EXPLOIT ON WEIRD PORT 

Machine names are important and can help to find exploit. Try machine name as username/password.

## ENTER IP IN /ETC/HOSTS

Enter every ip/hostname known in the file `/etc/hosts`.

## USE MULTIPLE TOOLS

Relying on one tool may cause miss something.

## DON'T SKIP EASY WINS

Start simple. Weak password, open shares or misconfigurations can provide quick wins that boost confidence. Search for specific files anywhere (*.pdf, *.kdbx, ...)

## USE SPECIFIC SEARCHES

Google wisely! Advanced search operators can help to find exact solutions to error messages of CVEs. 

## SPRAY EVERYTHING

- Find a new user? `ADD IT TO USERS.TXT`
- Find a new password? or something that *might* be a password? `ADD IT TO PASSWORDS.TXT`
- `SPRAY SPRAY SPRAY`
- FTP, SSH, NXC (ALL PROTOCOL POSSIBLE), KERBEROS, ADMIN CONSOLES, ANYTHING THAT ACCEPTS CREDENTIALS JUST TRY IT

## TRY DEFAULT CREDS AND DUMB CREDS

- Find a software you've never heard of? `SEARCH FOR DEFAULT CREDENTIALS`
- Find a software you have heard of? `SEARCH FOR DEFAULT CREDENTIALS`
- Find a new user? `TRY THE USERNAME AS THE PASSWORD` `user:user` `admin:admin` `ftp:ftp` `$MACHINE_NAME:$MACHINE_NAME`
- Maybe with upper case ? `jack` => `Jack`
- Can't crack a password? `TRY THE USERNAME AS THE PASSWORD`
- Try simple wordlists like https://github.com/drtychai/wordlists/blob/master/fasttrack.txt or an other!

## TRY ALTERNATE CRACKING TECHNIQUES

- Hashcat didn't work? Tried with rules? `TRY IT WITH JOHN, TRY IT WITH CRACKSTATION`
- John didn't work? `TRY IT WITH HASHCAT, TRY IT WITH CRACKSTATION`
- Crackstation didn't work? `TRY IT WITH HASHCAT, TRY IT WITH JOHN`

## TRY AN OTHER EXPLOIT 

If one fails, don't give up. Modify it, debug it, or find a diffrent approach.

## GREP RESULTS

Use grep to filter large results

## REVERT SLOW MACHINE 

If a machine lags, revert it early to save time.

## DRINK WATER

## TAKE A BREATH AND START FROM THE TOP OF THE CHECKLIST YOU PROBABLY MISSED SOMETHING EASY

## TAKE A FUCKING BREAK

## DRINK SOME FUCKING WATER

## EAT SOME FUCKING FOOD

## MOVE ON TO SOMETHING ELSE AND COME BACK LATER

## AHHHHHHHHHHHHHHHHHHHHHHHH