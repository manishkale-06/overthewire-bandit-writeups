# Bandit Level 13 → Level 14
## Objective
The password for the next level is stored in /etc/bandit\_pass/bandit14 and can only be read by user bandit14. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level. Look at the commands that logged you into previous bandit levels, and find out how to use the key for this level.

---

## Server Details
- **Host:** bandit.labs.overthewire.org  
- **Port:** 2220  
- **Username:** bandit13

---

## SSH Command Used
```bash
ssh bandit13@bandit.labs.overthewire.org -p 2220

## Commands Executed
ls
exit
scp -P 2220 bandit13@bandit.labs.overthewire.org:/home/bandit13/ssh.private /tmp
ssh -i /tmp/ssh.private bandit14@bandit.labs.overthewire.org -p 2220
cat /etc/bandit_pass/bandit14

```
___

## Explanation

- ls is used to currrent dirctory's contents.

- Once the SSH key file name is extracted using ls, then session is closed using exit command.

- After that scp command is used which allows us to copy file from source to destination as here bandit13 user of bandit.labs.overthewire.org is source and file location is specified. Then the destination location is also provided as here it is temp directory of local machine. -P option is used to specify port number. Using this command key is copied on local machine. /temp directory is special directory because it have temporary files once system is rbooted its contents will be deleted. 

- After that ssh command is used to login as bandit14 user using SSH key file. To do so -i flag is used which allows to log in by selecting identity file i.e. private key for public key authentication. This SSH key file was already copied to /tmp directory using scp command.

- Then it will log in as bandit14, then we can extract password using cat command from /etc/bandit\_pass/bandit14  
