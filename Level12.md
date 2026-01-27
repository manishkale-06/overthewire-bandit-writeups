# Bandit Level 12 → Level 13
## Objective
The password for the next level is stored in the file data.txt, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work. Use mkdir with a hard to guess directory name. Or better, use the command “mktemp -d”. Then copy the datafile using cp, and rename it using mv (read the manpages!)

---

## Server Details
- **Host:** bandit.labs.overthewire.org  
- **Port:** 2220  
- **Username:** bandit12

---

## SSH Command Used
```bash
ssh bandit12@bandit.labs.overthewire.org -p 2220

## Commands Executed
ls
cd /tmp/datamy
cp /home/bandit12/data.txt ./
xxd -r data.txt > comdata
file comdata
mv comdata comdata.gz
gunzip comdata.gz
bunzip2 data2.bz2
tar -xf data6
cat data8

```
___

## Explanation

- ls is used to currrent dirctory's contents.

- cd command is used to change dirctory to temporary as there file can be created as need and will be removed on logout.

- cp command is used to copy the data.txt file in temp dirctory for further operations.

- xxd command used with -r flag simply reveses the hexdump file to its binary form and redirection operator is used to rediect to output in comdata file.

- file command is used to see the actual file type and decide which operations to perform. After each operation performes(like gunzip, tar, bunzip2, etc) again this command is used to determine next operation as it is mentioned in problem statment that file is commpressed several times.

- mv command is used to rename the files before performing extraction so that no naming error will occur.

- gunzip simply unzips the file which was compressed in gzip format.

- bunzip2 extracts the file which is compressed in bzip2 format.

- tar with -xf flag is used to force extract .tar file i.e. archived file.

- Operations like gunzip, bunzip2, tar -xf, file, has to perform again and again untill ASCII text format file is obtained.

- Once ASCII txt file is obtained then cat command can be used to see its contents and password.
