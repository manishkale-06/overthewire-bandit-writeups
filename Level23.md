# Bandit Level 23 → Level 24
## Objective
A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.

NOTE: This level requires you to create your own first shell-script. This is a very big step and you should be proud of yourself when you beat this level!

NOTE 2: Keep in mind that your shell script is removed once executed, so you may want to keep a copy around…

---

## Server Details
- **Host:** bandit.labs.overthewire.org  
- **Port:** 2220  
- **Username:** bandit23

---

## SSH Command Used
```bash
ssh bandit23@bandit.labs.overthewire.org -p 2220

## Commands Executed
cd /etc/cron.d
ls
cd /var/spool/bandit24/foo
vim myscript.sh


## myscript.sh
&#35!/bin/bash
cat /etc/bandit_pass/bandit24 > /tmp/myfile66

## Later Commands Executed
chmod +x myscript.sh
cat /tmp/myfile66
```
___

## Explanation

- As stated in the problem statement cronjobs resides on /etc/cron.d so to enter this directory cd is used.

- ls command is used to see the contents of current directory. Using this file containg clue of password can be identified.

- cat used then to see what is inside file cron\_bandit24 which may contain clue to login to next level.

- Inside that file there is a script which runs automatically utilizing cron jobs.

- Again cat is used to see the script contains. This script is executing all file residing in /var/spool/"$myname"/foo where myname variable is set to output of command whoami which gives the username. After execution all files within this directory are deleted. So it is possible to create a script in this directory and use user name "bandit24" to run it as bandit24.

- To do so using vim a file is created in which contents of cd /var/spool/bandit24/foo is redirected to /tmp/myfile66 which is password of next level. After exiting the vim editor chmod is used to make the script executable. This script will be executed after some time through cron jobs. We can see if it is executed i.e. if it is deleted then it is executed otherwise have to wait a little longer.

- Finally, cat is used to read the file that is mentioned in the script /tmp/myfile66 to get the password of next level which is redircted in this directory.

