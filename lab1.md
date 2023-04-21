# Lab Report 1 - Remote Access and FileSystem

## 1. Installing VScode
- [Download](https://code.visualstudio.com/)  VScode
- Install VScode, don't change any default options.
- The program looks like this (For windows).

![image](vs_code.png)

## 2. Remotely Connecting
- Install Git ([Git for Windows](https://gitforwindows.org/))
- Set `git bash` in VScode. (You can follow this [tutorial](https://stackoverflow.com/questions/42606837/how-do-i-use-bash-on-windows-from-the-visual-studio-code-integrated-terminal/50527994#50527994)) 
- Open a terminal in VScode and enter the command below. (Replace `zz` with specific account)
```
$ ssh cs15lsp23zz@ieng6.ucsd.edu
```
- Type yes to continue and enter your password. The correct output is shown below.
![image](remote.png)

## 3. Trying some commands
Try the commands below
* `cd ~`
* `cd`
* `ls -lat`
* `ls <directory>`
* `cp <path>`
* `cat <path>`

Here are some examples.

![image](command.png)

`ls ..` lists the files in parent directory.

![image](Screenshot%202023-04-21%20120214.png)

`cp <path>` copies the file from the target path to current path.

![image](Screenshot%202023-04-21%20120809.png)

`cat <path>` prints the content of text file.
