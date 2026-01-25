# Bandit Level 8 → Level 9

## Objective
The password for the next level is stored in the file data.txt and is the only line of text that occurs only once.

---

## Server Details
- **Host:** bandit.labs.overthewire.org  
- **Port:** 2220  
- **Username:** bandit8

---

## SSH Command Used
```bash
ssh bandit8@bandit.labs.overthewire.org -p 2220

## Commands Executed
ls
sort data.txt | uniq -u

```
___

## Explanation

- ls is used to currrent dirctory's contents.

- The sort command is used to sort the contents of a file. By default, it arranges the lines in alphabetical order.

- uniq command is commonly used to report duplicate lines, but here it is used with -u flag which shows only unique lines. uniq only works when duplicate lines are adjacent or one after another so here sort commands output is piped to uniq using pipe operator '|'. This will arrange the file contents and duplicate lines will be adjacent.

- pipe operator just takes standard output and feeds is standard input to next command.
