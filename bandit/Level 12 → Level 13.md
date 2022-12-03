# Level 12 → Level 13

## Level Goal
The password for the next level is stored in the file `data.txt`, which is a hexdump of a file that has been repeatedly compressed.  
For this level it may be useful to create a directory under `/tmp` in which you can work using `mkdir`.  
For example: `mkdir /tmp/myname123`. Then copy the datafile using `cp`, and rename it using `mv` (read the manpages!)

## Commands you may need to solve this level
`grep`, `sort`, `uniq`, `strings`, `base64`, `tr`, `tar`, `gzip`, `bzip2`, `xxd`, `mkdir`, `cp`, `mv`, `file`

## Solution

Connect to the challenge through SSH:

```sh
~$ ssh bandit12@bandit.labs.overthewire.org -p 2220 # password: JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv
```

Revert hexdump from `data.txt` file, chain several decompression steps (gz, bz, gz, tar, tar, bz, tar, gz) & print the result to standard output:

```sh
bandit12@bandit:~$ xxd -r data.txt | gunzip | bzip2 -d | gunzip | tar xvO | tar xvO | bzip2 -d | tar xvO | gunzip
data5.bin
data6.bin
data8.bin
The password is wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw
```

## Resources

Challenge: https://overthewire.org/wargames/bandit/bandit13.html