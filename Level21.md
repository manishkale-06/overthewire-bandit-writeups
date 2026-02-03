# Bandit Level 20 → Level 21
## Objective
A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.

---

## Server Details
- **Host:** bandit.labs.overthewire.org  
- **Port:** 2220  
- **Username:** bandit21

---

## SSH Command Used
```bash
ssh bandit21@bandit.labs.overthewire.org -p 2220

## Commands Executed
cd /etc/cron.d
ls
cat cronjob_bandit22
cat /usr/bin/cronjob_bandit22.sh
cat /tmp/t706lds9S0RqQh9aMcz6ShpAoZKF7fgv

```
___

## Explanation

- As stated in the problem statement cronjobs resides on /etc/cron.d so to enter this directory cd is used.

- ls command is used to see the contents of current directory. Using this file containg clue of password can be identified.

- cat used then to see what is inside the file cron\_bandit22 which may contain clue to login to next level.

- Inside that file there is a script which runs automatically utilizing cron jobs.

- Again cat is used to see the script contains. Inside this script redirection of output of cat /etc/bandit\_pass/bandit22 is done to /tmp/t706lds9S0RqQh9aMcz6ShpAoZKF7fgv.

- Finally, cat is used to read this file to get the password of next level.

