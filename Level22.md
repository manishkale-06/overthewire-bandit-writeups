# Bandit Level 21 → Level 22
## Objective
A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.

NOTE: Looking at shell scripts written by other people is a very useful skill. The script for this level is intentionally made easy to read. If you are having problems understanding what it does, try executing it to see the debug information it prints.

---

## Server Details
- **Host:** bandit.labs.overthewire.org  
- **Port:** 2220  
- **Username:** bandit22

---

## SSH Command Used
```bash
ssh bandit22@bandit.labs.overthewire.org -p 2220

## Commands Executed
cd /etc/cron.d
ls
cat cronjob_bandit23
cat /usr/bin/cronjob_bandit23.sh
myname=bandit23
mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)
cat /tmp/$mytarget

```
___

## Explanation

- As stated in the problem statement cronjobs resides on /etc/cron.d so to enter this directory cd is used.

- ls command is used to see the contents of current directory. Using this file containg clue of password can be identified.

- cat used then to what is indide file cron\_bandit22 which may contain clue to login to next level.

- Inside that file there is a script which runs automatically utilizing cron jobs.

- Here output of cat /etc/bandit\_pass/$muname is redirected to a file in /tmp/$my target where myname and mytarget are variables. myname=$(whoami) and mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1). '$' creates a subshell environment to run command whose output's value is given to these variables.

- So, in order to find the path of file that contains the password value of $mytarget must be known. To do so myname=bandit23 is set as we want password of bandit 23. Then mytarget variable is calculated as given in the script using this myname variable.

- After that, file name is obtained which is $mytarget. So, cat command to extract the password from /tmp/$mytarget file. 
