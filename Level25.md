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
exit
vim /tmp/pass26.sshkey
ssh -i /tmp/pass26.sshkey bandit26@bandit.labs.overthewire.org -p 2220
v
:set shell=/usr/bin/bash
:shell

```
___

## Explanation

- ls is used to see file and dirctory names in the current directory.

- cat is used to see the contains of sshkey file and copy it so it can be used to login to bandit26. So it is copied.

- As problem says bandit26 is not using /bin/bash shell, so we can check what it is using by looking into /etc/passwd dirctory with cat command whose output is piped to grep for searching for bandit26.

- It says /usr/bin/showtext is used instead of /usr/bin/bash, so using cat command contents of /usr/bin/showtext can be seen for furthur clues.

- In this file it shown that more tool is used intead of bash which is showing contents of some text.txt file and exiting. In short, it is possible to use this clue to solve next level i.e. Level 26. 

- exit is used to logout of current user i.e. bandit25. 

- A sshkey file is created to login with in bandit26.

- ssh command is used with -i flag to login with sshkey file which is created, by giving its path.

- bandit26 will automatically logout as text.txt file contents is printed as written earlier. So to avoid this first terminal window is resized to narrow sized such that the text cannot be prited fully so it will suspend and logout is avoided for the time being.

- Now, as more tool is vulnarable as one can run command through it, but we cannot directly access shell because as soon as one command is executed text file gets reloaded. To avoid it first vi editor can be opened by simply pressing 'v'. In vi editor shell can be accessed.

- To do so first shell must be defined by running command in vi edior which is allowed by using ':'.

- :set shell=/usr/bin/bash is used to intialized shell and set it.

- :shell will open an interactive shell session in vi editor.
