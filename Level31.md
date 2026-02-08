# Bandit Level 31 → Level 32
## Objective
There is a git repository at ssh://bandit31-git@bandit.labs.overthewire.org/home/bandit31-git/repo via the port 2220. The password for the user bandit31-git is the same as for the user bandit31.

From your local machine (not the OverTheWire machine!), clone the repository and find the password for the next level. This needs git installed locally on your machine.

---

## Server Details
- **Host:** bandit.labs.overthewire.org  
- **Port:** 2220  
- **Username:** bandit32

---

## Command Used
```bash
cd /tmp
git clone ssh://bandit31-git@bandit.labs.overthewire.org:2220/home/bandit31-git/repo
cd repo
cat README.md
vim key.txt
git add key.txt
git commit -m "file upload"
git push origin master

```
___

## Explanation

- cd is used to change current directory to /tmp to make the cloned repository a temporary directory that will be deleted automatically on boot.

- git is version control tool widely used and git clone is used to clone(copy) the remote repository to local machine where command is executed.

- Here port is specified after ssh://bandit28-git@bandit.labs.overthewire.org with :2220 so that we can specify the connection port which is listening.

- After cloning is done cd is used to enter ./repo directory and ls is used to see contents of that ./repo dirctory.

- README.md file is then read with cat command. Where it is said to push a key.txt file containing "May I come in?" text on master baranch of remote repository.

- To do so vim is used to create and edit the key.txt file in vim text editor.

- Then git add command is used to stage the new file created. Along with it git commit command is used to commit the changes made in current repo branch. -m flag is used to add a message to the commit.

- Finnaly git push command is used to push the repository to remote host on master branch.
