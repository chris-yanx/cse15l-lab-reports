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

<img width="340" alt="image" src="https://github.com/chris-yanx/cse15l-lab-reports/assets/77228505/8a557faf-083b-4089-802e-a3e68ec09347">


`43 <enter>` to jump to the line that has wrong code.

<img width="389" alt="image" src="https://github.com/chris-yanx/cse15l-lab-reports/assets/77228505/9e923ff6-03cb-40ae-a7ae-042c051e41c4">

`e` to jump the last character of first word.

<img width="371" alt="image" src="https://github.com/chris-yanx/cse15l-lab-reports/assets/77228505/f683a0d4-1256-4fb4-8e49-6ba58a5405fd">

`r2` to replace the character "1" to "2".

<img width="376" alt="image" src="https://github.com/chris-yanx/cse15l-lab-reports/assets/77228505/7ae2ff3f-a536-4188-b437-57ed6dee2ba2">

`:wq <enter>` to save and exit the file.

<img width="326" alt="image" src="https://github.com/chris-yanx/cse15l-lab-reports/assets/77228505/55f65a20-318b-405a-984a-dcbe7556bb72">


## Run the tests, demonstrating that they now succeed

`<up><up> <enter>` to run the test.sh file in the history. The test succeeds now.

<img width="272" alt="image" src="https://github.com/chris-yanx/cse15l-lab-reports/assets/77228505/8c222d36-3510-474e-9e2f-069ed2e34bc4">

## Commit and push the resulting change to your Github account

Commit and push my repository, the commit message is "bug fixed".

```
git commit -m "bug fixed"
git push
```

<img width="410" alt="image" src="https://github.com/chris-yanx/cse15l-lab-reports/assets/77228505/83915a81-8aae-4a56-b435-c4a24ee64a39">

