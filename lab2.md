# Lab Report 2: Servers and bugs

## Part 1: StringServer

Code:
```
import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;

class Handler implements URLHandler {
    String result = "";
    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return result;
        }
        else if (url.getPath().contains("/add-message")) {
            String[] parameters = url.getQuery().split("=");
            if (parameters[0].equals("s")) {
                result += parameters[1] + "\n";
                return result;
            }
        }
        return "404 Not Found!";
    }
}

class StringServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}
```

![image](lab2_image/output%20(1).png)

* It calls the main method and then calls the handleRequest method. 
* url is an object with string field: "localhost:2004/add-messages?s=hello". The string field Result was "How are you" before calling this method.
* The if statement checks if it contains "/add message". If so, it separate the query by "=". If the first part of query includes "s". If all requirements are satisfied, "\n hello" is added to result after calling this method.


![image](lab2_image/output%20(2).png)

* It calls the main method and then calls the handleRequest method. 
* url is an object with string field: "localhost:2004/add-messages?s=???". The string field Result was "How are you \n hello" before calling this method.
* The if statement checks if it contains "/add message". If so, it separate the query by "=". If the first part of query includes "s". If all requirements are satisfied, "\n ???" is added to Result after calling this method.


## Part 2: Bugs

A failure-inducing input: 

```
@Test 
public void testReverseInPlace1() {
    int[] input1 = {3, 2, 1};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{1, 2, 3}, input1);
}
```

An input that doesn’t induce a failure: 

```
@Test
public void testReverseInPlace2() {
    int[] input1 = {1};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{1}, input1);
}
```

Symptom: 

![image](lab2_image/Symptom.png)

The bug:

```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
}
```

The fixed code: 

```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length/2; i += 1) {
        int n = arr[i];
        arr[i] = arr[arr.length - i - 1];
        arr[arr.length - i - 1] = n;
    }
}
```

The bug in the original code tries to reverse an array in place but does so incorrectly. It mistakenly swaps elements on the left side of the array with elements on the right side of the array.
The fixed code improves on this by swapping pairs of elements symmetrically around the middle of the array. It only iterates over the first half of the array and for each iteration, swaps the element at the current index with the corresponding element on the opposite side of the array.

## Part 3
I learn how to use JUnit to test my methods. I gain some experiences of debugging and analyzing code. Also, by debugging the methods related to array, list and linked list methods, now I have better understanding of these data structures.
