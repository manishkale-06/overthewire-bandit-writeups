# Bandit Level 20 → Level 21
## Objective
There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).

---

## Server Details
- **Host:** bandit.labs.overthewire.org  
- **Port:** 2220  
- **Username:** bandit21

---

## SSH Command Used
```bash
ssh bandit20@bandit.labs.overthewire.org -p 2220

## Commands Executed
tmux

## Window 1:
ls
./suconnect 30011

## Window 2:
nc -l 30011

```
___

## Explanation

- In window 1 ls is used to see dirctory contains. Then suid binary is executed with random port to establish connection as it is state in problem. This will establish a connection and will listen on spectfied port.

- In window 2 nc command is used which is used for TCP/UDP connections and -l option allows to listen on specified port which is same as port on which suconnect is listening. Once it is executed then current level password is sent over this connection to suconnect. Which in turn will reply with next level password if sent password is correct.
