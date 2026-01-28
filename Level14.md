# Bandit Level 14 → Level 15
## Objective
The password for the next level can be retrieved by submitting the password of the current level to port 30000 on localhost.

---

## Server Details
- **Host:** bandit.labs.overthewire.org  
- **Port:** 2220  
- **Username:** bandit14

---

## SSH Command Used
```bash
ssh bandit14@bandit.labs.overthewire.org -p 2220

## Commands Executed
telnet localhost 30000

```
___

## Explanation

- telnet command is used to connect to specific host on specfic port.

- Here using telnet command connection is made to port 30000 of localhost.

- Then on that connection currnt level password is sent to get password of next level as a response.
