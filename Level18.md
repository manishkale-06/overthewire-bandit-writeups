# Bandit Level 18 → Level 19
## Objective
The password for the next level is stored in a file readme in the homedirectory. Unfortunately, someone has modified .bashrc to log you out when you log in with SSH.

---

## Server Details
- **Host:** bandit.labs.overthewire.org  
- **Port:** 2220  
- **Username:** bandit18

---

## SSH Command Used
```bash
ssh bandit18@bandit.labs.overthewire.org -p 2220

## Commands Executed
scp -P 2220 bandit18@bandit.labs.overthewire.org:/home/bandit18/readme /home/username/
cat /home/username/readme

```
___

## Explanation

- scp command is used to copy file from remote host to local machine. Here -P option is used to specify port number.After that source file address which will be copied is specified and after that destination is specified.

- Once the command is executed then password is submitted to confirm coping.

- This method is used because .bashrc is logging user out time he logs in. As scp fetches file without login it is used here.

- Finnaly password is extracted from readme file using cat command.
