Hello World!!!

# Lab Report 3 - Bugs and Commands 
Name: Kiruthika Marikumaran 
PID: A17877875
 
---

# Part 1: Bugs 

Failure inducing input: 

```
# Reverse Array Method & Failure Inducing JUnit Test

  // Returns a *new* array with all the elements of the input array in reversed
  // order
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }

  //Failure Inducing JUnit Test
  @Test
  public void testReversed1() {
    int[] input1 = {4, 6, 7, 9};
    assertArrayEquals(new int[]{9, 7, 6, 4}, ArrayExamples.reversed(input1));
  }
  
```
  

Input that doesn't induce failure: 

```
# JUnit Test Not Inducing Failure For Reverse Method 
  @Test
  public void testReversed() {
    int[] input1 = {0};
    assertArrayEquals(new int[]{0}, ArrayExamples.reversed(input1));
  }

```

Symptom: 
<img width="830" alt="Screen Shot 2024-02-13 at 6 17 35 PM" src="https://github.com/kirustar14/cse15l-lab-reports/assets/148379107/d9a537d7-56cc-4e3e-85ef-25d918df9e98">


Bug Before/After: 







Choose one of the bugs from week 4's lab.

Provide:

A failure-inducing input for the buggy program, as a JUnit test and any associated code (write it as a code block in Markdown)

An input that doesn't induce a failure, as a JUnit test and any associated code (write it as a code block in Markdown)

The symptom, as the output of running the tests (provide it as a screenshot of running JUnit with at least the two inputs above)
The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown)
Briefly describe why the fix addresses the issue.
