# Bandit Level 6 → Level 7

## Objective
The password for the next level is stored somewhere on the server and has all of the following properties:

    owned by user bandit7
    owned by group bandit6
    33 bytes in size

---

## Server Details
- **Host:** bandit.labs.overthewire.org  
- **Port:** 2220  
- **Username:** bandit6

---

## SSH Command Used
```bash
ssh bandit6@bandit.labs.overthewire.org -p 2220

## Commands Executed
find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
cat /var/lib/dpkg/info/bandit7.password

```
___

## Explanation

- find command is used to find some file in directory hierarchy. '/' after find tells find to search from root directory and '-user bandit7' tells to search for specific user who owns the file  which is bandit7 here, '-group bandit6' tells to search for group who owns the file which is bandit6 here and '-size 33c' tells to search file with 33 bytes size as 'c' represents bytes.  

- cat is used to see contents of file as it concatinates given files and stdout. Here result of find command is given as it contains password. 

- '2\>/dev/null' tells the terminal to send any standard errors to redirect to /dev/null directory. /dev/null directory just removes anything redirected to it. As 2 represents standard error here it used with redidirection operator '\>' to avoid any standard error messages to be displayed, like Permission denied,etc. 
