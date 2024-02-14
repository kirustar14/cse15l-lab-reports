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

```
#Before

  // Returns a *new* array with all the elements of the input array in reversed
  // order
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }

```

```
#After

  // Returns a *new* array with all the elements of the input array in reversed
  // order
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }

```

Why fix worked? 

Iniitally we were changing the values in the original array (arr) and thats what we returned. However we needed to swap the newArray and arr and return the newArray, because we dont want to change the values in arr. We only want to change the values in newArray by accesing the vlaues in arr backwards so it is reversed. And then we return the newArray. So the fix worked because now we are storing the values from arr in newArray in reverse order but not changin the values in arr and we return the newArray which has the reversed order values. 


