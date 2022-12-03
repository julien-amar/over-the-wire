# Level 22 → Level 23

## Level Goal
A program is running automatically at regular intervals from cron, the time-based job scheduler.  
Look in `/etc/cron.d/` for the configuration and see what command is being executed.  
  
NOTE: Looking at shell scripts written by other people is a very useful skill.  
The script for this level is intentionally made easy to read.  
If you are having problems understanding what it does, try executing it to see the debug information it prints.

## Commands you may need to solve this level
`cron`, `crontab`, `crontab(5)` _(use “man 5 crontab” to access this)_

## Solution

Connect to the challenge through SSH:

```sh
~$ ssh bandit22@bandit.labs.overthewire.org -p 2220 # password: WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff
```

List scheduled tasks, for user `bandit23`:

```sh
bandit22@bandit:~$ cat /etc/cron.d/cronjob_bandit23
@reboot bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
* * * * * bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
```

Print the content of scheduled script `/usr/bin/cronjob_bandit23.sh`:

```sh
bandit22@bandit:~$ cat /usr/bin/cronjob_bandit23.sh
#!/bin/bash
myname=$(whoami)
mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)
echo "Copying passwordfile /etc/bandit_pass/$myname to /tmp/$mytarget"
cat /etc/bandit_pass/$myname > /tmp/$mytarget
```

Considering the script is executed every minutes, we can simulate this execution and print the content of the temporary file:

```sh
bandit22@bandit:~$ myname=bandit23
bandit22@bandit:~$ mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)
bandit22@bandit:~$ cat /tmp/$mytarget
QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G
```

## Resources

Challenge: https://overthewire.org/wargames/bandit/bandit23.html