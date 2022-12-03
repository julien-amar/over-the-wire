# Level 4 → Level 5

## Level Goal
The password for the next level is stored in the only human-readable file in the inhere directory.  
Tip: if your terminal is messed up, try the `reset` command.

## Commands you may need to solve this level
`ls` , `cd` , `cat` , `file` , `du` , `find`

## Solution

Connect to the challenge through SSH:

```sh
~$ ssh bandit4@bandit.labs.overthewire.org -p 2220 # password: 2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe
```

Print humain readable content from all file (located in `inhere/`) to standard output:

```sh
bandit4@bandit:~$ for i in inhere/*; do echo $i:; strings $i; done
inhere/-file00:
inhere/-file01:
q$`8
inhere/-file02:
G)=I
inhere/-file03:
QEd8
inhere/-file04:
inhere/-file05:
inhere/-file06:
inhere/-file07:
lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
inhere/-file08:
inhere/-file09:
J,l6
PT4"
```

## Resources

Challenge: https://overthewire.org/wargames/bandit/bandit5.html