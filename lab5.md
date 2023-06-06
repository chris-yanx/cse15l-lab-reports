# Lab Report 5
## Part 1 – Debugging Scenario
### Student Post
**What environment are you using (computer, operating system, web browser, terminal/editor, and so on)?**

VSCode, Windows 11, Chrome.

**Detail the symptom you're seeing. Be specific; include both what you're seeing and what you expected to see instead. Screenshots are great, copy-pasted terminal output is also great. Avoid saying “it doesn't work”.**

* Expected Output: 

The bash file is successfully executed, the required file exists, a grade is printed based on the correctness of the code.

* Actual Output:

<img width="458" alt="image" src="https://github.com/chris-yanx/cse15l-lab-reports/assets/77228505/bb102cbc-186f-4a77-96fa-15ffbd27be38">



**Detail the failure-inducing input and context. That might mean any or all of the command you're running, a test case, command-line arguments, working directory, even the last few commands you ran. Do your best to provide as much context as you can.**

Screenshot of TestListExamples.java:

<img width="416" alt="image" src="https://github.com/chris-yanx/cse15l-lab-reports/assets/77228505/e79f0411-693b-4b03-b495-2acb4f4f6aaa">

Screeshot of grade.sh:

<img width="393" alt="image" src="https://github.com/chris-yanx/cse15l-lab-reports/assets/77228505/feaad02c-c015-4f50-8ff4-382dd7244979">

<img width="662" alt="image" src="https://github.com/chris-yanx/cse15l-lab-reports/assets/77228505/1110f499-855f-4409-b1db-629f2deee31e">


The errors suggest that JUnit library is either missing or not properly configured. The java file fail to find the junit test in my file, therefore it cannot successfully import the junit library.



### 1. TA response

1. Check to ensure that you have added to your project's build path.
2. Verify that the package declaration in your TestListExamples.java file matches the actual package structure.
3. Since you are running the command under Windows. The path separator on windows is ";", not ":".

### 2. Student retry

The bug is caused by wrong separator ":". After I changed the separator of classpath to ";", the error is fixed.  

<img width="392" alt="image" src="https://github.com/chris-yanx/cse15l-lab-reports/assets/77228505/55296adb-7083-4e71-a7f2-5dd148b14ece">

### 3. Setup
* File & directory structure

<img width="143" alt="image" src="https://github.com/chris-yanx/cse15l-lab-reports/assets/77228505/4ac659a8-f117-4216-843c-370539ba49ad">

* The contents of each file before fixing the bug

grade.sh

<img width="656" alt="image" src="https://github.com/chris-yanx/cse15l-lab-reports/assets/77228505/5f36d951-2f17-4039-8f86-01164169f304">

TestListExamples.java

<img width="496" alt="image" src="https://github.com/chris-yanx/cse15l-lab-reports/assets/77228505/33be89d5-5971-422b-b2d4-1d0c196e146b">

* The full command line (or lines) you ran to trigger the bug

```
bash grade.sh https://github.com/ucsd-cse15l-f22/list-methods-lab3
```

* A description of what to edit to fix the bug

Change the separator of classpath from ":" to ";", the correct classpath should be `CPATH=".；lib/hamcrest-core-1.3.jar；lib/junit-4.13.2.jar"`

## Part 2 – Reflection

Debugging command lines are really helpful. Before I knew this, I have to change my code to print out all the values to observe their changes to find the bug. It is good to know that by using the debugging tool, I can stop my code at any point to check if the behavior is correct. Vim is also a cool tool to edit files, it is convenient to use when I only want to make a few changes on my file, so I don't need to wait to load my JAVA IDE.
