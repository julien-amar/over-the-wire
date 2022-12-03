# Level 19 → Level 20

## Level Goal
To gain access to the next level, you should use the setuid binary in the home directory.  
Execute it without arguments to find out how to use it.  
The password for this level can be found in the usual place (`/etc/bandit_pass`), after you have used the setuid binary.

## Solution

Connect to the challenge through SSH:

```sh
~$ ssh bandit19@bandit.labs.overthewire.org -p 2220 # password: awhqfNnAbc1naukrpqDYcF95h7HoMTrC
```

Execute the `bandit20-do` to execute the command `cat /etc/bandit_pass/bandit20` under `bandit20`'s identity:

```sh
bandit19@bandit:~$ ./bandit20-do cat /etc/bandit_pass/bandit20
VxCazJaVykI6W36BkBU0mJTCM8rR95XT
```

## Resources

Challenge: https://overthewire.org/wargames/bandit/bandit20.html