# Bandit Level 17 → Level 18
## Objective
There are 2 files in the homedirectory: passwords.old and passwords.new. The password for the next level is in passwords.new and is the only line that has been changed between passwords.old and passwords.new

NOTE: if you have solved this level and see ‘Byebye!’ when trying to log into bandit18, this is related to the next level, bandit19


---

## Server Details
- **Host:** bandit.labs.overthewire.org  
- **Port:** 2220  
- **Username:** bandit17

---

## SSH Command Used
```bash
ssh bandit17@bandit.labs.overthewire.org -p 2220

## Commands Executed
diff passwords.old passwords.new

```
___

## Explanation

- diff command compares two files and gives the lines where they differ.

- As here passwords.old and passwoeds.new file only differ at the actual password so it will give that line as output. passwords.old line will be followed by '<' symbol and password.new line which is actual password will be followed by '>' in the output.
