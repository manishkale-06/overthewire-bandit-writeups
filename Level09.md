# Bandit Level 9 → Level 10

## Objective
The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.

---

## Server Details
- **Host:** bandit.labs.overthewire.org  
- **Port:** 2220  
- **Username:** bandit9

---

## SSH Command Used
```bash
ssh bandit9@bandit.labs.overthewire.org -p 2220

## Commands Executed
ls
strings data.txt | grep ====

```
___

## Explanation

- ls is used to currrent dirctory's contents.

- The string command is used to extract strings from the contents of a file. By default, it extracts human readable lines, and then its output is piped to grep commmand used match patterns through pipe opreator '|'.

- pipe operator feeds standard output of left side command to the right side command as standard an input.
