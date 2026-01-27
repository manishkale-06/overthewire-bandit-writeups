# Bandit Level 11 → Level 12

## Objective
The password for the next level is stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions.

---

## Server Details
- **Host:** bandit.labs.overthewire.org  
- **Port:** 2220  
- **Username:** bandit11

---

## SSH Command Used
```bash
ssh bandit11@bandit.labs.overthewire.org -p 2220

## Commands Executed
ls
tr 'N-ZA-Mn-za-m' 'A-MN-Za-mn-z' < data.txt

```
___

## Explanation

- ls is used to currrent dirctory's contents.

- The tr command translates characters from one set to another.

- Here, N-ZA-Mn-za-m → A-MZa-mn-z performs a ROT13 transformation, rotating letters by 13 positions (both uppercase and lowercase).

- The redirection oprator '<' is used to feed data.txt file to translates its contents. 

- This decodes the contents of data.txt and reveals the password.
