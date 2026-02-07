# Bandit Level 29 → Level 30
## Objective
There is a git repository at ssh://bandit29-git@bandit.labs.overthewire.org/home/bandit29-git/repo via the port 2220. The password for the user bandit29-git is the same as for the user bandit29.

From your local machine (not the OverTheWire machine!), clone the repository and find the password for the next level. This needs git installed locally on your machine.

---

## Server Details
- **Host:** bandit.labs.overthewire.org  
- **Port:** 2220  
- **Username:** bandit29

---

## Command Used
```bash
cd /tmp
git clone ssh://bandit28-git@bandit.labs.overthewire.org:2220/home/bandit28-git/repo
cd repo
git branch -a
git checkout remotes/origin/dev
ls
cat README.md

```
___

## Explanation

- cd is used to change current directory to /tmp to make the cloned repository a temporary directory that will be deleted automatically on boot.

- git is version control tool widely used and git clone is used to clone(copy) the remote repository to local machine where command is executed.

- Here port is specified after ssh://bandit28-git@bandit.labs.overthewire.org with :2220 so that we can specify the connection port which is listening.

- After cloning is done cd is used to enter ./repo directory and ls is used to see contents of that ./repo dirctory.

- As README.md file does not contain password of next level, git branch -a the list of all branches for currunt repo.

- Then all branches can be checked using git checkout command to see the password that may be in one of the branches.

- For each branch cat command is used to see the contents of the branch by which password can be obtained.
