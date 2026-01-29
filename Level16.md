# Bandit Level 16 → Level 17
## Objective
The credentials for the next level can be retrieved by submitting the password of the current level to a port on localhost in the range 31000 to 32000. First find out which of these ports have a server listening on them. Then find out which of those speak SSL/TLS and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.

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
nmap -p31000-32000 -v  localhost
nmap -p 31046,31518,31691,31790,31968 --script ssl-cert localhost
openssl s_client -connect localhost:31790 -tls1_2

```
___

## Explanation

- Using nmap and -v (verbose) flag port scannig is done with the help of -p flag form ports 31000 to 32000.

- nmap will give open ports in its output using them again nmap is exrcuted using ssl-cert script on localhost to see details about ssl certificate to determine which ports speak ssl and tls.

- Finally, conncection is made to port shortlisted from those three commands with the help of openssl s\_client and choosing tls1\_2. It's output will give server certificate i.e. private key which can be used to login to next level.
