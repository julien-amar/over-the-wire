# Level 6 → Level 7

## Level Goal
The password for the next level is stored somewhere on the server and has all of the following properties:
- owned by user bandit7
- owned by group bandit6
- 33 bytes in size

## Commands you may need to solve this level
`ls` , `cd` , `cat` , `file` , `du` , `find`, `grep`

## Solution

Connect to the challenge through SSH:

```sh
~$ ssh bandit6@bandit.labs.overthewire.org -p 2220 # password: P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
```

Find `bandit7` user owned, `bandit6` group owned & 33 sized file (located in `/`) & print it to standard output:

```sh
bandit6@bandit:~$ find / -user bandit7 -group bandit6 -size 33c -exec cat {} \; 2>/dev/null
z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
```

## Resources

Challenge: https://overthewire.org/wargames/bandit/bandit7.html