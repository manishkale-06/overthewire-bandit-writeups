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
ls  
cat ./-

```
____

## Explaination

- ls is used to list all the files and directories present in current directory.

- cat concatinates the given files and stdout but as here only one argument is given it shows its content as standard output.

- './-' is used instead '-' because otherwise it will be misinterpreted as option or flag argument. ./ reprsents current directory so './-' will be treated as full directory name and not be misinterpreted as option or flag.               
