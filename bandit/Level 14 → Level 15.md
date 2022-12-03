# Level 14 → Level 15

## Level Goal
The password for the next level can be retrieved by submitting the password of the current level to `port 30000` on `localhost`.

## Commands you may need to solve this level
`ssh`, `telnet`, `nc`, `openssl`, `s_client`, `nmap`

## Solution

Connect to the challenge through SSH, using previously obtained SSH private key:

```sh
~$ ssh bandit14@bandit.labs.overthewire.org -p 2220 -i sshkey.private
```

Send current exercise's password to localhost (port 30000) & print server's response to standard output:

```sh
bandit14@bandit:~$ cat /etc/bandit_pass/bandit14 | nc localhost 30000
Correct!
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
```

## Resources

Challenge: https://overthewire.org/wargames/bandit/bandit15.html