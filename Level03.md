# Bandit Level 3 → Level 4

## Objective
The password for the next level is stored in a hidden file in the inhere directory.

---

## Server Details
- **Host:** bandit.labs.overthewire.org  
- **Port:** 2220  
- **Username:** bandit3 

---

## SSH Command Used
```bash
ssh bandit3@bandit.labs.overthewire.org -p 2220

## Commands Executed
cd
ls -la
cat \.\.\.Hiding-Form-You

```
___

## Explanation

- cd is used to change dirctory and here it is changed to ./inhere.

- ls is used with -l flag gives long including file permissions and other useful information.

- ls with -a flag list all files along with hidden files here password was in one of these files i.e. ...Hiding-From-You file.

- Note that . file represents current directory and .. represents privious directory. 

- Any other directories with ... prefix are hidden directories.

- cat will show contents of the hidden file we provided i.e. given here with some escape sequence character '\' as we want to take ... as it is to match filename.
