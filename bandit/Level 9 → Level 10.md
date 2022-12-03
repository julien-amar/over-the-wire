# Level 9 → Level 10

## Level Goal
The password for the next level is stored in the file `data.txt` in one of the few human-readable strings, preceded by several `=` characters.

## Commands you may need to solve this level
`grep`, `sort`, `uniq`, `strings`, `base64`, `tr`, `tar`, `gzip`, `bzip2`, `xxd`

## Solution

Connect to the challenge through SSH:

```sh
~$ ssh bandit9@bandit.labs.overthewire.org -p 2220 # password: EN632PlfYiZbn3PhVK3XOGSlNInNE00t
```

Print human readable strings contained in `data.txt`, filter on the one containing at least 2 `=` & print the result to standard output:

```sh
bandit9@bandit:~$ strings data.txt | grep "=="
========== the
bu========== password
4iu========== is
b~==P
========== G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
```

## Resources

Challenge: https://overthewire.org/wargames/bandit/bandit10.html