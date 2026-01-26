# Bandit Level 10 → Level 11

## Objective
The password for the next level is stored in the file data.txt, which contains base64 encoded data

---

## Server Details
- **Host:** bandit.labs.overthewire.org  
- **Port:** 2220  
- **Username:** bandit10

---

## SSH Command Used
```bash
ssh bandit10@bandit.labs.overthewire.org -p 2220

## Commands Executed
ls
base64 -d data.txt

```
___

## Explanation

- ls is used to currrent dirctory's contents.

- base64 command encodes/decodes the data that is provided. Here -d flag is used which decodes the given file.

