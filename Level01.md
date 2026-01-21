# Bandit Level 1 → Level 2

## Objective
The password for the next level is stored in a file called - located in the home directory

---

## Server Details
- **Host:** bandit.labs.overthewire.org  
- **Port:** 2220  
- **Username:** bandit1  

---

## SSH Command Used
```bash
ssh bandit1@bandit.labs.overthewire.org -p 2220

## Commands Executed
ls                  (used to see contents of forlder)
cat ./-             (as '-' might be misread for flag argument in terminal I used ./- as full name of                              directory so cat will look for exact file name )
