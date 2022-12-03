# Level 21 → Level 22

## Level Goal
A program is running automatically at regular intervals from cron, the time-based job scheduler.  
Look in `/etc/cron.d/` for the configuration and see what command is being executed.

## Commands you may need to solve this level
`cron`, `crontab`, `crontab(5)` _(use “man 5 crontab” to access this)_

## Solution

Connect to the challenge through SSH:

```sh
~$ ssh bandit21@bandit.labs.overthewire.org -p 2220 # password: NvEJF7oVjkddltPSrdKEFOllh9V1IBcq
```

List scheduled tasks, for user `bandit22`:

```sh
bandit21@bandit:~$ cat /etc/cron.d/cronjob_bandit22
@reboot bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
* * * * * bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
```

Print the content of scheduled script `/usr/bin/cronjob_bandit22.sh`:

```sh
bandit21@bandit:~$ cat /usr/bin/cronjob_bandit22.sh
#!/bin/bash
chmod 644 /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
cat /etc/bandit_pass/bandit22 > /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
```

Considering the script is executed every minutes, we can print the content of the temporary file:

```sh
bandit21@bandit:~$ cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff
```

## Resources

Challenge: https://overthewire.org/wargames/bandit/bandit22.html