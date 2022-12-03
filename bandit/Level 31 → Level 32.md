# Level 31 → Level 32

## Level Goal
There is a git repository at `ssh://bandit31-git@localhost/home/bandit31-git/repo`.  
The password for the user `bandit31-git` is the same as for the user `bandit31`.  
  
Clone the repository and find the password for the next level.

## Commands you may need to solve this level
`git`

## Solution

Clone the remote repository, through SSH:

```sh
~$ git clone ssh://bandit31-git@bandit.labs.overthewire.org:2220/home/bandit31-git/repo # git password: OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt
~$ cd repo/
```

Print the `README.md` file to get instructions:

```sh
~/repo$ cat README.md
This time your task is to push a file to the remote repository.
Details:
    File name: key.txt
    Content: 'May I come in?'
    Branch: master
```

Push a commit according to those criteria:

```sh
~/repo$ echo May I come in? > key.txt
~/repo$ git add key.txt -f
~/repo$ git commit -m "Add a file"
~/repo$ git push
# <truncated>
remote: Well done! Here is the password for the next level:
remote: rmCBvG56y58BXzv98yZGdO7ATVL5dW8y
# <truncated>
```

## Resources

Challenge: https://overthewire.org/wargames/bandit/bandit32.html