# Bandit Level 7 → Level 8

## Objective
The password for the next level is stored in the file data.txt next to the word millionth

---

## Server Details
- **Host:** bandit.labs.overthewire.org  
- **Port:** 2220  
- **Username:** bandit7

---

## SSH Command Used
```bash
ssh bandit7@bandit.labs.overthewire.org -p 2220

## Commands Executed
ls
grep millionth data.txt

```
___

## Explanation

- ls is used to list all contents of current working dirctory. With ls we can get file name where password is stored

- grep searches the pattern provided in file and returns successful matches. Here instead of pattern direct string is matched in data.txt file as in problem statement it is told that password resides next to 'millionth'. 
