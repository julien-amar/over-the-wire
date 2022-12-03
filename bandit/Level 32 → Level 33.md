# Level 32 → Level 33

## Level Goal
After all this git stuff its time for another escape.  
Good luck!

## Commands you may need to solve this level
`sh`, `man`

## Solution

Connect to the challenge through SSH:

```sh
~$ ssh bandit32@bandit.labs.overthewire.org -p 2220 # password: rmCBvG56y58BXzv98yZGdO7ATVL5dW8y
```

Execute `$0` to execute another instance of the shell (as neither `$` or `0` is affected by the change of casing):

```sh
>> $0
```

Print the challenge's password to the standard output:

```sh
$ cat /etc/bandit_pass/bandit33
odHo63fHiFqcWWJG9rLiLDtPm45KzUKy
```

## Resources

As per `bash` documentation: `$0 expands to the name of the shell or shell script. This is set at shell initialization.`  
  
Challenge: https://overthewire.org/wargames/bandit/bandit33.html