# Bandit Level 26 → Level 27
## Objective
Good job getting a shell! Now hurry and grab the password for bandit27!

---

## Server Details
- **Host:** bandit.labs.overthewire.org  
- **Port:** 2220  
- **Username:** bandit26

---

## SSH Command Used
```bash
ssh bandit26@bandit.labs.overthewire.org -p 2220

## Commands Executed
ls
./bandit27-do cat /etc/bandit_pass/bandit27

```
___

## Explanation

- As shell is obtained through efforts taken in last level, now it is possible to run shell commands.

- ls is used to see file and dirctory names in the current directory.

- Using ls it is seen that there is setuid binary file which will allow to run any command given, to run as user bandit27. 

- So ./bandit27-do cat /etc/bandit\_pass/bandit27 is used to see password of Level27 as setuid binary will allow theaccess to this file.
