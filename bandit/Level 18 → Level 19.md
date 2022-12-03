# Level 18 → Level 19

## Level Goal
The password for the next level is stored in a file `readme` in the home directory.  
Unfortunately, someone has modified `.bashrc` to log you out when you log in with SSH.

## Commands you may need to solve this level
`ssh`, `ls`, `cat`

## Solution

Connect to the challenge through SSH & execute a remote command `cat readme`:

```sh
~$ ssh bandit18@bandit.labs.overthewire.org -p 2220 cat readme # password: hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
awhqfNnAbc1naukrpqDYcF95h7HoMTrC
```

## Resources

Challenge: https://overthewire.org/wargames/bandit/bandit19.html