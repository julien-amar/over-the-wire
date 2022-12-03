# Level 2 → Level 3

## Level Goal
The password for the next level is stored in a file called spaces in this filename located in the home directory.

## Commands you may need to solve this level
`ls` , `cd` , `cat` , `file` , `du` , `find`

## Solution

Connect to the challenge through SSH:

```sh
~$ ssh bandit2@bandit.labs.overthewire.org -p 2220 # password: rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
```

Print the content of the file (with spaces) to standard output:

```sh
bandit2@bandit:~$ cat spaces\ in\ this\ filename
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
```

## Resources

Challenge: https://overthewire.org/wargames/bandit/bandit3.html