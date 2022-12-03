# Level 15 → Level 16

## Level Goal
The password for the next level can be retrieved by submitting the password of the current level to `port 30001` on `localhost` using `SSL encryption`.  
  
Helpful note: Getting “HEARTBEATING” and “Read R BLOCK”?  
- Use `-ign_eof` and read the `CONNECTED COMMANDS` section in the manpage.
- Next to `R` and `Q`, the `B` command also works in this version of that command...

## Commands you may need to solve this level
`ssh`, `telnet`, `nc`, `openssl`, `s_client`, `nmap`

## Solution

Connect to the challenge through SSH:

```sh
~$ ssh bandit15@bandit.labs.overthewire.org -p 2220 # password: jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
```

Send current exercise's password to localhost (port 30001, through TLS established connection) & print server's response to standard output:

```sh
bandit15@bandit:~$ openssl s_client -connect localhost:30001
CONNECTED(00000003)
# <truncated>
---
read R BLOCK
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
Correct!
JQttfApK4SeyHwDlI9SXGR50qclOAil1

closed
```

## Resources

Challenge: https://overthewire.org/wargames/bandit/bandit16.html