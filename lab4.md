## Log into ieng6

I typed the commands below to log into my student account. I have generated the SSH keys so I don't need to input my password again.

```
$ ssh cs15lsp23hd@ieng6.ucsd.edu
```

<img width="462" alt="image" src="https://github.com/chris-yanx/cse15l-lab-reports/assets/77228505/3fe886d8-28b3-422c-9881-7411fc9ba174">


## Clone your fork of the repository from your Github account

The url is copied from github [link](https://github.com/chris-yanx/lab7).

```
git clone git@github.com:chris-yanx/lab7.git
```

<img width="431" alt="image" src="https://github.com/chris-yanx/cse15l-lab-reports/assets/77228505/4bc17566-c628-41e1-b0f6-2c3d93d52b5e">


## Run the tests, demonstrating that they fail

Change current directory to lab7/ and then run the test bash file.

```
cd lab7/
bash test.sh
```

<img width="503" alt="image" src="https://github.com/chris-yanx/cse15l-lab-reports/assets/77228505/cde455af-a494-4455-a41f-e56caf1cc405">


## Edit the code file to fix the failing test

`vim + <file name>` to access the failed code.

```
vim ListExamples.java
```

`43 <enter>` to jump to the line that has wrong code.

`e` to jump the last character of first word.

`r2` to replace the character "1" to "2".

`:wq <enter>` to save and exit the file.

<img width="314" alt="image" src="https://github.com/chris-yanx/cse15l-lab-reports/assets/77228505/be7c0485-9212-47c1-8a23-3b615fe5d7e1">

<img width="379" alt="image" src="https://github.com/chris-yanx/cse15l-lab-reports/assets/77228505/baf35ec5-b858-47ab-8216-a4ebd7d5a283">



## Run the tests, demonstrating that they now succeed

`<up><up> <enter>` to run the test.sh file in the history. The test succeeds now.


## Commit and push the resulting change to your Github account

Commit and push my repository, the commit message is "bug fixed".

```
git commit -m "bug fixed"
git push
```
