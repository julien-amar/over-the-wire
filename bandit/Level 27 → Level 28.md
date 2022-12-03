# Level 27 → Level 28

## Level Goal
There is a git repository at `ssh://bandit27-git@localhost/home/bandit27-git/repo`.  
The password for the user `bandit27-git` is the same as for the user `bandit27`.  
  
Clone the repository and find the password for the next level.

## Commands you may need to solve this level
`git`

## Solution

Clone the remote repository, through SSH:

```sh
~$ git clone ssh://bandit27-git@bandit.labs.overthewire.org:2220/home/bandit27-git/repo # git password: YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS
```

Print the content of the `README` file to the standard output:

```sh
~$ cat repo/README
The password to the next level is: AVanL161y9rsbcJIsFHuw35rjaOM19nR
```

## Resources

Challenge: https://overthewire.org/wargames/bandit/bandit28.html
