# Bandit Level 0 → Level 1

## Objective
Log in to the Bandit server using SSH and find the password for the next level.

---

## Server Details
- **Host:** bandit.labs.overthewire.org  
- **Port:** 2220  
- **Username:** bandit0  

---

## SSH Command Used
```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220

## Commands Executed
ls              
cat readme      

```
___

## Explaination

- ls lists all contents of the current dirctory including files and directories.

- cat concatinates given file/files and gives to standard output showing its contents on the terminal.    
