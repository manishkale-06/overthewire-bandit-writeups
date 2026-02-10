# Bandit Level 32 → Level 33
## Objective
After all this git stuff, it’s time for another escape. Good luck!

---

## Server Details
- **Host:** bandit.labs.overthewire.org  
- **Port:** 2220  
- **Username:** bandit32

---

## Command Used
$0
whoami
cat /etc/bandit\_pass/bandit33

```
___

## Explanation

- Here Uppercase shell is running so whatever commands are given they are converted in uppercase resulting in errors as they are not recognized.

- $0 is used to switch to bash shell as it is not converted to uppercase.

- whoami command tells us the user we are operting as. So here it shows bandit 33.

- As user is bandit33 we can use cat command to see password of bandit33 residing in /etc/bandit_pass/bandit33.
