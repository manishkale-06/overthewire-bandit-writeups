# Bandit Level 5 → Level 6

## Objective
The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:

    human-readable
    1033 bytes in size
    not executable

---

## Server Details
- **Host:** bandit.labs.overthewire.org  
- **Port:** 2220  
- **Username:** bandit5 

---

## SSH Command Used
```bash
ssh bandit5@bandit.labs.overthewire.org -p 2220

## Commands Executed
ls
cd inhere
find . type -f ! -executable -size 1033c
cat ./maybehere07/.file2

```
___

## Explanation

- ls is used to currrent dirctory's contents.

- cd is used to change dirctory and here it is changed to ./inhere.

- find command is used to find some file in directory hierarchy. '.' after find tells find to search from current directory and '-type f' tells to search for readable file, '! -executable' tells to search non-executable file and '-size 1033c' tells to search file with 1033 bytes size as 'c' represents bytes.  

- cat is used to see contents of file as it concatinates given files and stdout. Here result of find command is given as it contains password. 
