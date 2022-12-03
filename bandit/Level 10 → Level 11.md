# Level 10 → Level 11

## Level Goal
The password for the next level is stored in the file `data.txt`, which contains `base64 encoded data`

## Commands you may need to solve this level
`grep`, `sort`, `uniq`, `strings`, `base64`, `tr`, `tar`, `gzip`, `bzip2`, `xxd`

## Solution

Connect to the challenge through SSH:

```sh
~$ ssh bandit10@bandit.labs.overthewire.org -p 2220 # password: G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
```

Base64 decode the file `data.txt` & print the result to standard output:

```sh
bandit10@bandit:~$ base64 -d data.txt
The password is 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
```

## Resources

Challenge: https://overthewire.org/wargames/bandit/bandit11.html