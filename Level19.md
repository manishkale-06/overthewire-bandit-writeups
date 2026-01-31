# Bandit Level 19 → Level 20
## Objective
To gain access to the next level, you should use the setuid binary in the homedirectory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (/etc/bandit\_pass), after you have used the setuid binary.

---

## Server Details
- **Host:** bandit.labs.overthewire.org  
- **Port:** 2220  
- **Username:** bandit19

---

## SSH Command Used
```bash
ssh bandit19@bandit.labs.overthewire.org -p 2220

## Commands Executed
./bandit20-do cat /etc/bandit_pass/bandit20

```
___

## Explanation

- As stated in the problem, the home directory contains a setuid binary.
A setuid binary runs with the privileges of its owner, which allows this program to execute commands as another user.

- In this case, the binary can be used to access /etc/bandit\_pass/bandit20, where the password for the next level is stored and is normally only readable by user bandit20.

- Therefore, the cat command is used with the setuid binary to read the password.
