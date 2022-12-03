# Level 29 → Level 30

## Level Goal
There is a git repository at `ssh://bandit29-git@localhost/home/bandit29-git/repo`.  
The password for the user `bandit29-git` is the same as for the user `bandit29`.  
  
Clone the repository and find the password for the next level.

## Commands you may need to solve this level
`git`

## Solution

Clone the remote repository, through SSH:

```sh
~$ git clone ssh://bandit29-git@bandit.labs.overthewire.org:2220/home/bandit29-git/repo # git password: tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S
~$ cd repo/
```

List available GIT remote branches:

```sh
~/repo$ git branch -a
* master
  remotes/origin/HEAD -> origin/master
  remotes/origin/dev
  remotes/origin/master
  remotes/origin/sploits-dev
```

Check out the remote `dev` branch and print `README.md`'s content to the standard output:

```sh
~/repo$ git checkout origin/dev

~/repo$ cat README.md
# <truncated>
- password: xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS
```

## Resources

Challenge: https://overthewire.org/wargames/bandit/bandit30.html