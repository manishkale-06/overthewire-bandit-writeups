# Bandit Level 25 → Level 26
## Objective
Logging in to bandit26 from bandit25 should be fairly easy… The shell for user bandit26 is not /bin/bash, but something else. Find out what it is, how it works and how to break out of it.

    NOTE: if you’re a Windows user and typically use Powershell to ssh into bandit: Powershell is known to cause issues with the intended solution to this level. You should use command prompt instead.

---

## Server Details
- **Host:** bandit.labs.overthewire.org  
- **Port:** 2220  
- **Username:** bandit25

---

## SSH Command Used
```bash
ssh bandit25@bandit.labs.overthewire.org -p 2220

## Commands Executed
ls
cat bandit26.sshkey
cat /etc/passwd | grep bandit26
cat /usr/bin/showtext

```
___

## Explanation

- ls is used to see file and dirctory names in the current directory.

- cat is used to see the contains of sshkey file and copy it so it can be used to login to bandit26.

- As problem says bandit26 is not using /bin/bash shell, so we can check what it is using by looking into /etc/passwd dirctory with cat command whose output is piped to grep for searching for bandit26.

- It says /usr/bin/showtext is used instead of /usr/bin/bash, so using cat command contents of /usr/bin/showtext can be seen for furthur clues.

- In this file it shown that more tool is used intead of bash which is showing contents of some text.txt file and exiting. In short, it is possible to use this clue to solve next level i.e. Level 26. 
