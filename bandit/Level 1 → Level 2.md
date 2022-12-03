# Level 1 → Level 2

## Level Goal
The password for the next level is stored in a file called `-` located in the home directory.

## Commands you may need to solve this level
`ls` , `cd` , `cat` , `file` , `du` , `find`

## Solution

Connect to the challenge through SSH:

```sh
~$ ssh bandit1@bandit.labs.overthewire.org -p 2220 # password: NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL
```

Print the content of the `-` file (dashed filename) to standard output, using either of the commands:

```sh
bandit1@bandit:~$ cat ./-
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi

bandit1@bandit:~$ cat < -
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
```

## Resources

Challenge: https://overthewire.org/wargames/bandit/bandit2.html
