# Level 17 → Level 18

## Level Goal
There are 2 files in the home directory: `passwords.old` and `passwords.new`.  
The password for the next level is in `passwords.new` and is the only line that has been changed between `passwords.old` and `passwords.new`  
  
NOTE: if you have solved this level and see `Byebye!` when trying to log into `bandit18`, this is related to the next level, `bandit19`

## Commands you may need to solve this level
`cat`, `grep`, `ls`, `diff`

## Solution

Connect to the challenge through SSH, using previously obtained SSH private key:

```sh
~$ ssh bandit17@bandit.labs.overthewire.org -p 2220 -i sshkey.private
```

Check file difference between the two password files & print comparaison result to standard output:

```sh
bandit17@bandit:~$ diff passwords.{old,new}
42c42
< 09wUIyMU4YhOzl1Lzxoz0voIBzZ2TUAf
---
> hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
```

## Resources

Challenge: https://overthewire.org/wargames/bandit/bandit18.html