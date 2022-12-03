# Level 8 → Level 9

## Level Goal
The password for the next level is stored in the file `data.txt` and is the `only line of text that occurs only once`

## Commands you may need to solve this level
`grep`, `sort`, `uniq`, `strings`, `base64`, `tr`, `tar`, `gzip`, `bzip2`, `xxd`

## Solution

Connect to the challenge through SSH:

```sh
~$ ssh bandit8@bandit.labs.overthewire.org -p 2220 # password: TESKZC0XvTetK0S9xNwm25STk5iWrBvP
```

Sort `data.txt`, group/count entries, filter on the one that is uniq & print the result to standard output:

```sh
bandit8@bandit:~$ sort data.txt | uniq -c | grep "1 "
      1 EN632PlfYiZbn3PhVK3XOGSlNInNE00t
```

## Resources

Challenge: https://overthewire.org/wargames/bandit/bandit9.html