# Level 11 → Level 12

## Level Goal
The password for the next level is stored in the file `data.txt`, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions

## Commands you may need to solve this level
`grep`, `sort`, `uniq`, `strings`, `base64`, `tr`, `tar`, `gzip`, `bzip2`, `xxd`

## Solution

Connect to the challenge through SSH:

```sh
~$ ssh bandit11@bandit.labs.overthewire.org -p 2220 # password: 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
```

Rotate each character by 13 from piped file `data.txt` & print the result to standard output:

```sh
bandit11@bandit:~$ cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
The password is JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv
```

## Resources

Challenge: https://overthewire.org/wargames/bandit/bandit12.html