# Level 7 → Level 8

## Level Goal
The password for the next level is stored in the file `data.txt` next to the word `millionth`

## Commands you may need to solve this level
`man`, `grep`, `sort`, `uniq`, `strings`, `base64`, `tr`, `tar`, `gzip`, `bzip2`, `xxd`

## Solution

Connect to the challenge through SSH:

```sh
~$ ssh bandit7@bandit.labs.overthewire.org -p 2220 # password: z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
```

Find the line containing `millionth` in `data.txt` & print the second column to standard output:

```sh
bandit7@bandit:~$ grep millionth data.txt | cut -f 2
TESKZC0XvTetK0S9xNwm25STk5iWrBvP
```

## Resources

Challenge: https://overthewire.org/wargames/bandit/bandit8.html