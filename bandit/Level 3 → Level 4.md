# Level 3 → Level 4

## Level Goal
The password for the next level is stored in a hidden file in the inhere directory.

## Commands you may need to solve this level
`ls` , `cd` , `cat` , `file` , `du` , `find`

## Solution

Connect to the challenge through SSH:

```sh
~$ ssh bandit3@bandit.labs.overthewire.org -p 2220 # password: aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
```

Print the content of the hidden file to standard output:

```sh
bandit3@bandit:~$ cat inhere/.hidden
2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe
```

## Resources

Challenge: https://overthewire.org/wargames/bandit/bandit4.html