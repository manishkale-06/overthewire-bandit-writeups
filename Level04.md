# Bandit Level 4 → Level 5

## Objective
The password for the next level is stored in the only human-readable file in the inhere directory. Tip: if your terminal is messed up, try the “reset” command.

---

## Server Details
- **Host:** bandit.labs.overthewire.org  
- **Port:** 2220  
- **Username:** bandit4 

---

## SSH Command Used
```bash
ssh bandit4@bandit.labs.overthewire.org -p 2220

## Commands Executed
ls
cd inhere
file ./file0*
cat ./file07

```
___

## Explanation

- ls is used to currrent dirctory's contents.

- cd is used to change dirctory and here it is changed to ./inhere.

- file command is used to see the file type as in linux the extention of file may vary irrespective of the actual file type.

- Also ./-file0* is used; As * is a wildcart used to represent any (characters,number,symbol) so it will show all file types in current dirctory and the file type which is human readable will be found easily as ASCII text file.

- cat is used to see contents of file as it concatinates given files and stdout. Here as -file07 is only human readable file it contains password.  

