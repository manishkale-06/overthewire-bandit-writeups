# Bandit Level 30 → Level 31
## Objective
There is a git repository at ssh://bandit30-git@bandit.labs.overthewire.org/home/bandit30-git/repo via the port 2220. The password for the user bandit30-git is the same as for the user bandit30.

From your local machine (not the OverTheWire machine!), clone the repository and find the password for the next level. This needs git installed locally on your machine.

---

## Server Details
- **Host:** bandit.labs.overthewire.org  
- **Port:** 2220  
- **Username:** bandit30

---

## Command Used
```bash
cd /tmp
git clone ssh://bandit30-git@bandit.labs.overthewire.org:2220/home/bandit30-git/repo
cd repo
git tag
git show <tag name>

```
___

## Explanation

- cd is used to change current directory to /tmp to make the cloned repository a temporary directory that will be deleted automatically on boot.

- git is version control tool widely used and git clone is used to clone(copy) the remote repository to local machine where command is executed.

- Here port is specified after ssh://bandit28-git@bandit.labs.overthewire.org with :2220 so that we can specify the connection port which is listening.

- After cloning is done cd is used to enter ./repo directory and ls is used to see contents of that ./repo dirctory.

- As README.md file does not contain password of next level, git tag is used to see tags given to the repo where a clue to solve this level might be seen.

- Then git show is used to see the contents in a tag which was obtained which consists the password for next level.
