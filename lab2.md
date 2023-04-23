# Lab Report 2: Servers and bugs

## Part 1: StringServer
Code

![image](lab2_image/code%20(1).png)

![image](lab2_image/output%20(1).png)



![image](lab2_image/output%20(2).png)



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


## Part 3

