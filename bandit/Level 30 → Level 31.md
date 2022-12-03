# Level 30 → Level 31

## Level Goal
There is a git repository at `ssh://bandit30-git@localhost/home/bandit30-git/repo`.  
The password for the user `bandit30-git` is the same as for the user `bandit30`.  
  
Clone the repository and find the password for the next level.

## Commands you may need to solve this level
`git`

## Solution

Clone the remote repository, through SSH:

```sh
~$ git clone ssh://bandit30-git@bandit.labs.overthewire.org:2220/home/bandit30-git/repo # git password: xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS
~$ cd repo/
```

List available GIT tags:

```sh
~/repo$ git tag -l
secret
```

Print `secret`'s tag description to the standard output:

```sh
~$ $ git show secret
OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt
```

## Resources

Challenge: https://overthewire.org/wargames/bandit/bandit31.html