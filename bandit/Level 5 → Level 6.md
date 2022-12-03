# Level 5 → Level 6

## Level Goal
The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:
- human-readable
- 1033 bytes in size
- not executable

## Commands you may need to solve this level
`ls` , `cd` , `cat` , `file` , `du` , `find`

## Solution

Connect to the challenge through SSH:

```sh
~$ ssh bandit5@bandit.labs.overthewire.org -p 2220 # password: lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
```

Find user readable, 1033 sized & not executable file (located in `inhere/`) & print it to standard output:

```sh
bandit5@bandit:~$ find inhere/ -perm /u+r-x -size 1033c
inhere/maybehere07/.file2

bandit5@bandit:~$ cat inhere/maybehere07/.file2
P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
```

## Resources

Challenge: https://overthewire.org/wargames/bandit/bandit6.html