# Lab Report 5
## Part 1 – Debugging Scenario
### 1. Student Post
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



### 2. TA response

1. Check to ensure that you have added the JUnit library to your project's build path.
2. Verify that the package declaration in your TestListExamples.java file matches the actual package structure.
3. Since you are running the command under Windows. The path separator on windows is ";", not ":".

## Part 2 – Reflection
