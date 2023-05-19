Setup Delete any existing forks of the repository you have on your account

Setup Fork the repository

The real deal Start the timer!

## Log into ieng6

I typed the commands below to log into my student account. I have generated the SSH keys so I don't need to input my password again.

```
$ ssh cs15lsp23hd@ieng6.ucsd.edu
```

## Clone your fork of the repository from your Github account

The url is copied from github [link](https://github.com/chris-yanx/lab7).

```
git clone git@github.com:chris-yanx/lab7.git
```


## Run the tests, demonstrating that they fail

Change current directory to lab7/ and then run the test bash file.

```
cd lab7/
bash test.sh
```

## Edit the code file to fix the failing test

vim + <file name> to access the failed code.
  
```
vim ListExamples.java
```
 
`43 <enter>` to jump to the line that has wrong code.
  
`e` to jump the last character of first word.
  
`r2` to replace the character "1" to "2".
  
`:wq` to save and exit the file.
  

## Run the tests, demonstrating that they now succeed

## Commit and push the resulting change to your Github account (you can pick any commit message!)

