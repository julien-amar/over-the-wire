# Level 31

```sh
# git password: xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS
~$ git clone ssh://bandit30-git@bandit.labs.overthewire.org:2220/home/bandit30-git/repo
~$ cd repo/

~$ git tag -l
secret

~$ $ git show secret
OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt
```

Challenge: https://overthewire.org/wargames/bandit/bandit31.html

# Level 32

```sh
# git password: OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt
~$ git clone ssh://bandit31-git@bandit.labs.overthewire.org:2220/home/bandit31-git/repo
~$ cd repo/

~$ cat README.md
This time your task is to push a file to the remote repository.
Details:
    File name: key.txt
    Content: 'May I come in?'
    Branch: master

~$ echo May I come in? > key.txt
~$ git add key.txt -f
~$ git commit -m "Add a file"
~$ git push
# <truncated>
remote: Well done! Here is the password for the next level:
remote: rmCBvG56y58BXzv98yZGdO7ATVL5dW8y
# <truncated>
```

Challenge: https://overthewire.org/wargames/bandit/bandit32.html

# Level 33

```sh
# password: rmCBvG56y58BXzv98yZGdO7ATVL5dW8y
~$ ssh bandit32@bandit.labs.overthewire.org -p 2220

>> bash
sh: 1: BASH: not found
>> $0
$ cat /etc/bandit_pass/bandit33
odHo63fHiFqcWWJG9rLiLDtPm45KzUKy
```

Challenge: https://overthewire.org/wargames/bandit/bandit33.html

# Level 34

```sh
# password: odHo63fHiFqcWWJG9rLiLDtPm45KzUKy
~$ ssh bandit33@bandit.labs.overthewire.org -p 2220

bandit33@bandit:~$ cat README.txt
Congratulations on solving the last level of this game!

At this moment, there are no more levels to play in this game. However, we are constantly working
on new levels and will most likely expand this game with more levels soon.
Keep an eye out for an announcement on our usual communication channels!
In the meantime, you could play some of our other wargames.

If you have an idea for an awesome new level, please let us know!
```

Challenge: https://overthewire.org/wargames/bandit/bandit34.html
