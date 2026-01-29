# Bandit Level 15 → Level 16
## Objective
The password for the next level can be retrieved by submitting the password of the current level to port 30001 on localhost using SSL/TLS encryption.

Helpful note: Getting “DONE”, “RENEGOTIATING” or “KEYUPDATE”? Read the “CONNECTED COMMANDS” section in the manpage.

---

## Server Details
- **Host:** bandit.labs.overthewire.org  
- **Port:** 2220  
- **Username:** bandit16

---

## SSH Command Used
```bash
ssh bandit16@bandit.labs.overthewire.org -p 2220

## Commands Executed
openssl s_client -connect localhost:30001 -tls1_2

```
___

## Explanation

- openssl is a command line programe used here with s\_client which is the openssl application command.

- This connects the system to specified host and port as here they are localhost and 30001 respectively.

- If encryption protocol is mensioned then it uses that protocol for communication, here it is tls1\_2.

- Once connected password of current level is sent and then next level passoword is obtained.
