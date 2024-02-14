Hello World!!!

# Lab Report 3 - Bugs and Commands 
Name: Kiruthika Marikumaran 
PID: A17877875
 
---

# Part 1: Bugs 

Failure inducing input: 

```
# ReverseArrayMethod & Failure Inducing Junit Test

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

Symptom: 

Bug Before/After: 







Choose one of the bugs from week 4's lab.

Provide:

A failure-inducing input for the buggy program, as a JUnit test and any associated code (write it as a code block in Markdown)

An input that doesn't induce a failure, as a JUnit test and any associated code (write it as a code block in Markdown)

The symptom, as the output of running the tests (provide it as a screenshot of running JUnit with at least the two inputs above)
The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown)
Briefly describe why the fix addresses the issue.
