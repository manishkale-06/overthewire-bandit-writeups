# Bandit Level 2 → Level 3

## Objective
The password for the next level is stored in a file called --spaces in this filename-- located in the home directory

---

## Server Details
- **Host:** bandit.labs.overthewire.org  
- **Port:** 2220  
- **Username:** bandit2 

---

## SSH Command Used
```bash
ssh bandit2@bandit.labs.overthewire.org -p 2220

## Commands Executed
ls
cat ./--spaces\ in\ this\ filename--

```
___

## Explanation

ls lists the files in the home directory.

The filename starts with --, which Linux commands may treat as an option or flag.

Using ./ makes it explicit that the target is a file in the current directory.

The filename contains spaces, so each space is escaped using \ to prevent the shell from treating them as separate arguments.

cat displays the contents of the file, revealing the password for the next level.
