# Level 20 → Level 21

## Level Goal
There is a setuid binary in the home directory that does the following:
- it makes a connection to localhost on the port you specify as a commandline argument.
- It then reads a line of text from the connection and compares it to the password in the previous level (bandit20).
- If the password is correct, it will transmit the password for the next level (bandit21).
  
NOTE: Try connecting to your own network daemon to see if it works as you think

## Commands you may need to solve this level
`ssh`, `nc`, `cat`, `bash`, `screen`, `tmux`, `Unix job control` _(bg, fg, jobs, &, CTRL-Z, …)_

## Solution

Connect to the challenge through SSH, for this challenge, you need to open 2 SSH connections:

```sh
~$ ssh bandit20@bandit.labs.overthewire.org -p 2220 # password: VxCazJaVykI6W36BkBU0mJTCM8rR95XT
```

Start a listening server in the first terminal:

```sh
bandit20@bandit:~$ nc -l -p 1337
```

Connect to the listening server, using the second terminal:

```sh
bandit20@bandit:~$ ./suconnect 1337
```

Send current level's password by entering in first terminal:

```
VxCazJaVykI6W36BkBU0mJTCM8rR95XT
```

The second terminal should then display:

```
Read: VxCazJaVykI6W36BkBU0mJTCM8rR95XT
Password matches, sending next password
```

The first terminal should display:

```
NvEJF7oVjkddltPSrdKEFOllh9V1IBcq
```

## Resources

Challenge: https://overthewire.org/wargames/bandit/bandit21.html