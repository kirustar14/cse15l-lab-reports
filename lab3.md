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

 
---

# Part 2: Researching Commands: grep

Option #1: -c 
Source: https://www.geeksforgeeks.org/grep-command-in-unixlinux/ 

Example #1: 

```
# Command
grep -c "Introduction" 1468-6708-3-1.txt

#Output
1
```

The command is looking for the number of lines that contain the pattern "Introductions" withought the quotes, in the spefied file (1468-6708-3-1.txt) and we are in the biomed directory. This is useful because we can quickly search for how many instances of a pattern we have in our file, and since it counts how many lines we can use it to verify if every line has a required pattern by seeing if the number of lines containing the pattern matches the total number of lines in this file. 

Example #2: 

```
#Command
grep -c "adults" biomed/*.txt

#Output
biomed/1468-6708-3-1.txt:18
biomed/1468-6708-3-10.txt:0
biomed/1468-6708-3-3.txt:0
biomed/1468-6708-3-4.txt:0
biomed/1468-6708-3-7.txt:0
biomed/1471-2091-2-10.txt:0
biomed/1471-2091-2-11.txt:0
biomed/1471-2091-2-12.txt:0
biomed/1471-2091-2-13.txt:0
biomed/1471-2091-2-16.txt:0
biomed/1471-2091-2-5.txt:0
biomed/1471-2091-2-7.txt:0
biomed/1471-2091-2-9.txt:0
biomed/1471-2091-3-13.txt:0
biomed/1471-2091-3-14.txt:0
biomed/1471-2091-3-15.txt:0
biomed/1471-2091-3-16.txt:0
biomed/1471-2091-3-17.txt:0
biomed/1471-2091-3-18.txt:0
biomed/1471-2091-3-22.txt:0
biomed/1471-2091-3-23.txt:0
biomed/1471-2091-3-30.txt:0
biomed/1471-2091-3-31.txt:0
biomed/1471-2091-3-4.txt:0
biomed/1471-2091-3-8.txt:0
biomed/1471-2091-4-1.txt:0
biomed/1471-2091-4-5.txt:0
biomed/1471-2105-1-1.txt:0
biomed/1471-2105-2-1.txt:0
biomed/1471-2105-2-8.txt:0
biomed/1471-2105-2-9.txt:0
biomed/1471-2105-3-12.txt:0
biomed/1471-2105-3-14.txt:0
biomed/1471-2105-3-16.txt:0
biomed/1471-2105-3-17.txt:0
biomed/1471-2105-3-18.txt:0
biomed/1471-2105-3-2.txt:0
biomed/1471-2105-3-22.txt:0
biomed/1471-2105-3-23.txt:0
biomed/1471-2105-3-24.txt:0
biomed/1471-2105-3-26.txt:0
biomed/1471-2105-3-28.txt:0
biomed/1471-2105-3-3.txt:0
biomed/1471-2105-3-30.txt:0
biomed/1471-2105-3-34.txt:0
biomed/1471-2105-3-37.txt:0
biomed/1471-2105-3-38.txt:0
biomed/1471-2105-3-4.txt:0
biomed/1471-2105-3-6.txt:0
biomed/1471-2105-4-13.txt:0
biomed/1471-2105-4-24.txt:0
biomed/1471-2105-4-25.txt:0
biomed/1471-2105-4-26.txt:0
biomed/1471-2105-4-27.txt:0
biomed/1471-2105-4-28.txt:0
biomed/1471-2105-4-31.txt:0
biomed/1471-2121-1-2.txt:0
biomed/1471-2121-2-1.txt:0
biomed/1471-2121-2-10.txt:0
biomed/1471-2121-2-11.txt:0
biomed/1471-2121-2-12.txt:0
biomed/1471-2121-2-15.txt:0
biomed/1471-2121-2-18.txt:0
biomed/1471-2121-2-21.txt:0
biomed/1471-2121-2-22.txt:0
biomed/1471-2121-2-3.txt:0
biomed/1471-2121-2-6.txt:0
biomed/1471-2121-3-10.txt:0
biomed/1471-2121-3-11.txt:0
biomed/1471-2121-3-12.txt:0
biomed/1471-2121-3-13.txt:1
biomed/1471-2121-3-15.txt:0
biomed/1471-2121-3-16.txt:0
biomed/1471-2121-3-18.txt:0
biomed/1471-2121-3-19.txt:0
biomed/1471-2121-3-2.txt:0
biomed/1471-2121-3-21.txt:0
biomed/1471-2121-3-22.txt:0
biomed/1471-2121-3-25.txt:0
biomed/1471-2121-3-30.txt:1
biomed/1471-2121-3-4.txt:0
biomed/1471-2121-3-6.txt:0
biomed/1471-2121-3-8.txt:0
biomed/1471-2121-4-1.txt:0
biomed/1471-2121-4-2.txt:0
biomed/1471-2121-4-3.txt:0
biomed/1471-2121-4-4.txt:0
biomed/1471-2121-4-5.txt:0
biomed/1471-2121-4-6.txt:0
biomed/1471-213X-1-1.txt:1
biomed/1471-213X-1-10.txt:0
biomed/1471-213X-1-11.txt:0
biomed/1471-213X-1-12.txt:2
biomed/1471-213X-1-13.txt:0
biomed/1471-213X-1-15.txt:0
biomed/1471-213X-1-2.txt:0
biomed/1471-213X-1-3.txt:0
biomed/1471-213X-1-4.txt:0
biomed/1471-213X-1-6.txt:0
biomed/1471-213X-1-9.txt:0
biomed/1471-213X-2-1.txt:0
biomed/1471-213X-2-7.txt:0
biomed/1471-213X-2-8.txt:0
biomed/1471-213X-3-2.txt:0
biomed/1471-213X-3-3.txt:0
biomed/1471-213X-3-4.txt:0
biomed/1471-213X-3-7.txt:1
biomed/1471-2148-1-1.txt:0
biomed/1471-2148-1-14.txt:0
biomed/1471-2148-1-4.txt:0
biomed/1471-2148-1-6.txt:0
biomed/1471-2148-1-8.txt:0
biomed/1471-2148-2-12.txt:0
biomed/1471-2148-2-14.txt:0
biomed/1471-2148-2-15.txt:0
biomed/1471-2148-2-17.txt:0
biomed/1471-2148-2-2.txt:0
biomed/1471-2148-2-5.txt:0
biomed/1471-2148-2-7.txt:0
biomed/1471-2148-2-8.txt:0
biomed/1471-2148-3-1.txt:0
biomed/1471-2148-3-18.txt:0
biomed/1471-2148-3-3.txt:0
biomed/1471-2148-3-4.txt:0
biomed/1471-2148-3-7.txt:0
biomed/1471-2156-2-1.txt:0
biomed/1471-2156-2-12.txt:0
biomed/1471-2156-2-17.txt:0
biomed/1471-2156-2-18.txt:0
biomed/1471-2156-2-3.txt:0
biomed/1471-2156-2-5.txt:0
biomed/1471-2156-2-7.txt:0
biomed/1471-2156-2-8.txt:0
biomed/1471-2156-3-10.txt:0
biomed/1471-2156-3-11.txt:0
biomed/1471-2156-3-16.txt:0
biomed/1471-2156-3-17.txt:0
biomed/1471-2156-3-22.txt:0
biomed/1471-2156-3-3.txt:0
biomed/1471-2156-3-4.txt:0
biomed/1471-2156-4-10.txt:0
biomed/1471-2156-4-5.txt:0
biomed/1471-2156-4-6.txt:0
biomed/1471-2156-4-9.txt:0
biomed/1471-2164-2-1.txt:0
biomed/1471-2164-2-2.txt:0
biomed/1471-2164-2-4.txt:0
biomed/1471-2164-2-6.txt:0
biomed/1471-2164-2-7.txt:0
biomed/1471-2164-2-8.txt:0
biomed/1471-2164-2-9.txt:0
biomed/1471-2164-3-1.txt:0
biomed/1471-2164-3-10.txt:0
biomed/1471-2164-3-13.txt:0
biomed/1471-2164-3-15.txt:0
biomed/1471-2164-3-16.txt:0
biomed/1471-2164-3-18.txt:0
biomed/1471-2164-3-19.txt:0
biomed/1471-2164-3-23.txt:0
biomed/1471-2164-3-24.txt:0
biomed/1471-2164-3-26.txt:0
biomed/1471-2164-3-27.txt:0
biomed/1471-2164-3-28.txt:0
biomed/1471-2164-3-29.txt:0
biomed/1471-2164-3-30.txt:0
biomed/1471-2164-3-31.txt:0
biomed/1471-2164-3-32.txt:0
biomed/1471-2164-3-33.txt:0
biomed/1471-2164-3-34.txt:0
biomed/1471-2164-3-35.txt:0
biomed/1471-2164-3-4.txt:0
biomed/1471-2164-3-6.txt:0
biomed/1471-2164-3-7.txt:0
biomed/1471-2164-3-8.txt:0
biomed/1471-2164-3-9.txt:0
biomed/1471-2164-4-13.txt:0
biomed/1471-2164-4-14.txt:0
biomed/1471-2164-4-15.txt:0
biomed/1471-2164-4-16.txt:0
biomed/1471-2164-4-19.txt:0
biomed/1471-2164-4-2.txt:0
biomed/1471-2164-4-21.txt:0
biomed/1471-2164-4-22.txt:0
biomed/1471-2164-4-23.txt:0
biomed/1471-2164-4-24.txt:0
biomed/1471-2164-4-25.txt:0
biomed/1471-2164-4-26.txt:0
biomed/1471-2164-4-28.txt:0
biomed/1471-2164-4-4.txt:0
biomed/1471-2164-4-5.txt:0
biomed/1471-2164-4-6.txt:0
biomed/1471-2172-1-1.txt:0
biomed/1471-2172-2-10.txt:0
biomed/1471-2172-2-3.txt:0
biomed/1471-2172-2-4.txt:0
biomed/1471-2172-2-9.txt:1
biomed/1471-2172-3-1.txt:0
biomed/1471-2172-3-10.txt:0
biomed/1471-2172-3-12.txt:5
biomed/1471-2172-3-16.txt:0
biomed/1471-2172-3-2.txt:0
biomed/1471-2172-3-4.txt:0
biomed/1471-2172-3-9.txt:0
biomed/1471-2172-4-1.txt:0
biomed/1471-2172-4-2.txt:0
biomed/1471-2180-1-12.txt:0
biomed/1471-2180-1-16.txt:0
biomed/1471-2180-1-26.txt:0
biomed/1471-2180-1-28.txt:0
biomed/1471-2180-1-29.txt:0
biomed/1471-2180-1-31.txt:0
biomed/1471-2180-1-33.txt:0
biomed/1471-2180-1-34.txt:0
biomed/1471-2180-1-7.txt:0
biomed/1471-2180-1-8.txt:0
biomed/1471-2180-2-1.txt:0
biomed/1471-2180-2-13.txt:0
biomed/1471-2180-2-16.txt:0
biomed/1471-2180-2-2.txt:0
biomed/1471-2180-2-20.txt:0
biomed/1471-2180-2-22.txt:0
biomed/1471-2180-2-26.txt:0
biomed/1471-2180-2-29.txt:0
biomed/1471-2180-2-32.txt:0
biomed/1471-2180-2-35.txt:0
biomed/1471-2180-2-38.txt:0
biomed/1471-2180-2-7.txt:9
biomed/1471-2180-3-10.txt:0
biomed/1471-2180-3-11.txt:0
biomed/1471-2180-3-13.txt:0
biomed/1471-2180-3-15.txt:0
biomed/1471-2180-3-4.txt:0
biomed/1471-2180-3-5.txt:0
biomed/1471-2180-3-9.txt:0
biomed/1471-2199-2-1.txt:0
biomed/1471-2199-2-10.txt:0
biomed/1471-2199-2-12.txt:0
biomed/1471-2199-2-2.txt:0
biomed/1471-2199-2-3.txt:0
biomed/1471-2199-2-4.txt:0
biomed/1471-2199-2-5.txt:0
biomed/1471-2199-2-6.txt:0
biomed/1471-2199-3-10.txt:0
biomed/1471-2199-3-11.txt:0
biomed/1471-2199-3-12.txt:0
biomed/1471-2199-3-17.txt:0
biomed/1471-2199-3-3.txt:0
biomed/1471-2199-3-7.txt:0
biomed/1471-2199-4-4.txt:0
biomed/1471-2199-4-5.txt:0
biomed/1471-2202-1-1.txt:0
biomed/1471-2202-2-1.txt:0
biomed/1471-2202-2-10.txt:0
biomed/1471-2202-2-12.txt:0
biomed/1471-2202-2-14.txt:1
biomed/1471-2202-2-15.txt:0
biomed/1471-2202-2-16.txt:0
biomed/1471-2202-2-17.txt:0
biomed/1471-2202-2-18.txt:0
biomed/1471-2202-2-19.txt:0
biomed/1471-2202-2-2.txt:0
biomed/1471-2202-2-20.txt:0
biomed/1471-2202-2-3.txt:0
biomed/1471-2202-2-5.txt:0
biomed/1471-2202-2-6.txt:0
biomed/1471-2202-2-7.txt:0
biomed/1471-2202-2-8.txt:0
biomed/1471-2202-2-9.txt:0
biomed/1471-2202-3-1.txt:1
biomed/1471-2202-3-10.txt:0
biomed/1471-2202-3-11.txt:0
biomed/1471-2202-3-14.txt:0
biomed/1471-2202-3-16.txt:0
biomed/1471-2202-3-17.txt:0
biomed/1471-2202-3-19.txt:0
biomed/1471-2202-3-20.txt:0
biomed/1471-2202-3-3.txt:0
biomed/1471-2202-3-4.txt:0
biomed/1471-2202-3-5.txt:1
biomed/1471-2202-3-7.txt:0
biomed/1471-2202-3-8.txt:0
biomed/1471-2202-4-10.txt:0
biomed/1471-2202-4-11.txt:0
biomed/1471-2202-4-12.txt:0
biomed/1471-2202-4-16.txt:0
biomed/1471-2202-4-17.txt:0
biomed/1471-2202-4-2.txt:1
biomed/1471-2202-4-3.txt:0
biomed/1471-2202-4-5.txt:0
biomed/1471-2202-4-6.txt:0
biomed/1471-2210-1-10.txt:0
biomed/1471-2210-1-2.txt:0
biomed/1471-2210-1-3.txt:0
biomed/1471-2210-1-4.txt:0
biomed/1471-2210-1-7.txt:0
biomed/1471-2210-1-8.txt:0
biomed/1471-2210-2-14.txt:0
biomed/1471-2210-2-4.txt:0
biomed/1471-2210-2-5.txt:0
biomed/1471-2210-2-6.txt:0
biomed/1471-2210-2-8.txt:1
biomed/1471-2210-2-9.txt:0
biomed/1471-2210-3-1.txt:0
biomed/1471-2210-3-3.txt:0
biomed/1471-2229-1-2.txt:0
biomed/1471-2229-1-3.txt:0
biomed/1471-2229-2-11.txt:0
biomed/1471-2229-2-3.txt:0
biomed/1471-2229-2-4.txt:0
biomed/1471-2229-2-8.txt:0
biomed/1471-2229-2-9.txt:0
biomed/1471-2229-3-3.txt:0
biomed/1471-2253-1-1.txt:2
biomed/1471-2253-2-4.txt:3
biomed/1471-2253-2-5.txt:0
biomed/1471-2261-1-6.txt:0
biomed/1471-2261-2-11.txt:0
biomed/1471-2261-3-4.txt:0
biomed/1471-2261-3-5.txt:0
biomed/1471-2288-1-9.txt:0
biomed/1471-2288-2-10.txt:2
biomed/1471-2288-2-11.txt:0
biomed/1471-2288-2-4.txt:0
biomed/1471-2288-3-4.txt:0
biomed/1471-2288-3-8.txt:0
biomed/1471-2288-3-9.txt:0
biomed/1471-2296-3-18.txt:14
biomed/1471-2296-3-19.txt:0
biomed/1471-2296-3-3.txt:2
biomed/1471-230X-1-10.txt:1
biomed/1471-230X-1-5.txt:0
biomed/1471-230X-1-6.txt:0
biomed/1471-230X-1-8.txt:0
biomed/1471-230X-2-17.txt:0
biomed/1471-230X-2-21.txt:0
biomed/1471-230X-2-23.txt:0
biomed/1471-230X-3-3.txt:0
biomed/1471-230X-3-5.txt:0
biomed/1471-2318-3-2.txt:0
biomed/1471-2326-2-4.txt:0
biomed/1471-2334-1-10.txt:0
biomed/1471-2334-1-13.txt:2
biomed/1471-2334-1-17.txt:0
biomed/1471-2334-1-21.txt:0
biomed/1471-2334-1-24.txt:0
biomed/1471-2334-1-9.txt:0
biomed/1471-2334-2-1.txt:0
biomed/1471-2334-2-24.txt:0
biomed/1471-2334-2-26.txt:0
biomed/1471-2334-2-27.txt:0
biomed/1471-2334-2-29.txt:7
biomed/1471-2334-2-5.txt:0
biomed/1471-2334-2-6.txt:0
biomed/1471-2334-2-7.txt:0
biomed/1471-2334-3-10.txt:1
biomed/1471-2334-3-11.txt:1
biomed/1471-2334-3-12.txt:0
biomed/1471-2334-3-13.txt:0
biomed/1471-2334-3-15.txt:0
biomed/1471-2334-3-9.txt:0
biomed/1471-2350-2-11.txt:0
biomed/1471-2350-2-12.txt:1
biomed/1471-2350-2-2.txt:0
biomed/1471-2350-2-8.txt:0
biomed/1471-2350-3-1.txt:2
biomed/1471-2350-3-12.txt:0
biomed/1471-2350-3-7.txt:0
biomed/1471-2350-3-9.txt:1
biomed/1471-2350-4-2.txt:0
biomed/1471-2350-4-3.txt:7
biomed/1471-2350-4-4.txt:0
biomed/1471-2350-4-6.txt:0
biomed/1471-2369-3-1.txt:0
biomed/1471-2369-3-10.txt:0
biomed/1471-2369-3-6.txt:6
biomed/1471-2369-3-9.txt:0
biomed/1471-2369-4-1.txt:0
biomed/1471-2369-4-5.txt:0
biomed/1471-2377-1-2.txt:0
biomed/1471-2377-2-4.txt:0
biomed/1471-2377-2-6.txt:0
biomed/1471-2377-3-4.txt:0
biomed/1471-2407-1-13.txt:1
biomed/1471-2407-1-15.txt:0
biomed/1471-2407-1-19.txt:0
biomed/1471-2407-1-6.txt:0
biomed/1471-2407-2-11.txt:0
biomed/1471-2407-2-12.txt:0
biomed/1471-2407-2-15.txt:0
biomed/1471-2407-2-16.txt:0
biomed/1471-2407-2-17.txt:0
biomed/1471-2407-2-18.txt:0
biomed/1471-2407-2-19.txt:0
biomed/1471-2407-2-22.txt:0
biomed/1471-2407-2-23.txt:0
biomed/1471-2407-2-3.txt:0
biomed/1471-2407-2-31.txt:0
biomed/1471-2407-2-33.txt:0
biomed/1471-2407-2-8.txt:0
biomed/1471-2407-2-9.txt:0
biomed/1471-2407-3-14.txt:0
biomed/1471-2407-3-15.txt:0
biomed/1471-2407-3-16.txt:0
biomed/1471-2407-3-18.txt:0
biomed/1471-2407-3-3.txt:0
biomed/1471-2407-3-4.txt:0
biomed/1471-2407-3-5.txt:0
biomed/1471-2415-3-1.txt:0
biomed/1471-2415-3-3.txt:0
biomed/1471-2415-3-4.txt:0
biomed/1471-2415-3-5.txt:0
biomed/1471-2431-2-1.txt:2
biomed/1471-2431-2-11.txt:0
biomed/1471-2431-2-12.txt:0
biomed/1471-2431-2-4.txt:2
biomed/1471-2431-3-3.txt:9
biomed/1471-2431-3-4.txt:0
biomed/1471-2431-3-5.txt:1
biomed/1471-2431-3-6.txt:0
biomed/1471-244X-2-9.txt:6
biomed/1471-244X-3-5.txt:2
biomed/1471-2458-1-9.txt:3
biomed/1471-2458-2-11.txt:0
biomed/1471-2458-2-16.txt:0
biomed/1471-2458-2-18.txt:0
biomed/1471-2458-2-21.txt:0
biomed/1471-2458-2-25.txt:0
biomed/1471-2458-2-3.txt:1
biomed/1471-2458-2-6.txt:1
biomed/1471-2458-3-11.txt:2
biomed/1471-2458-3-2.txt:0
biomed/1471-2458-3-20.txt:0
biomed/1471-2458-3-5.txt:3
biomed/1471-2458-3-9.txt:0
biomed/1471-2466-1-1.txt:3
biomed/1471-2466-2-3.txt:0
biomed/1471-2466-2-4.txt:1
biomed/1471-2466-3-1.txt:0
biomed/1471-2474-2-1.txt:0
biomed/1471-2474-2-2.txt:0
biomed/1471-2474-2-3.txt:0
biomed/1471-2474-3-23.txt:0
biomed/1471-2474-3-3.txt:0
biomed/1471-2474-4-4.txt:0
biomed/1471-2474-4-8.txt:0
biomed/1471-2490-3-2.txt:0
biomed/1471-5945-1-3.txt:0
biomed/1471-5945-2-13.txt:0
biomed/1471-5945-3-3.txt:0
biomed/1472-6750-1-11.txt:0
biomed/1472-6750-1-12.txt:0
biomed/1472-6750-1-13.txt:0
biomed/1472-6750-1-6.txt:0
biomed/1472-6750-1-8.txt:0
biomed/1472-6750-2-10.txt:0
biomed/1472-6750-2-13.txt:0
biomed/1472-6750-2-14.txt:0
biomed/1472-6750-2-2.txt:0
biomed/1472-6750-2-21.txt:0
biomed/1472-6750-3-11.txt:0
biomed/1472-6750-3-4.txt:0
biomed/1472-6750-3-6.txt:0
biomed/1472-6769-1-1.txt:0
biomed/1472-6769-1-2.txt:0
biomed/1472-6769-1-3.txt:0
biomed/1472-6769-1-4.txt:0
biomed/1472-6785-1-3.txt:6
biomed/1472-6785-1-5.txt:0
biomed/1472-6785-2-6.txt:0
biomed/1472-6785-2-7.txt:0
biomed/1472-6793-1-11.txt:0
biomed/1472-6793-1-12.txt:0
biomed/1472-6793-1-15.txt:0
biomed/1472-6793-1-2.txt:0
biomed/1472-6793-1-6.txt:3
biomed/1472-6793-1-8.txt:0
biomed/1472-6793-2-1.txt:0
biomed/1472-6793-2-11.txt:8
biomed/1472-6793-2-16.txt:0
biomed/1472-6793-2-17.txt:0
biomed/1472-6793-2-18.txt:0
biomed/1472-6793-2-19.txt:0
biomed/1472-6793-2-2.txt:0
biomed/1472-6793-2-4.txt:0
biomed/1472-6793-2-5.txt:0
biomed/1472-6793-2-8.txt:0
biomed/1472-6793-3-3.txt:0
biomed/1472-6793-3-4.txt:0
biomed/1472-6793-3-5.txt:0
biomed/1472-6793-3-6.txt:0
biomed/1472-6807-1-1.txt:0
biomed/1472-6807-2-1.txt:0
biomed/1472-6807-2-2.txt:0
biomed/1472-6807-2-3.txt:0
biomed/1472-6807-2-4.txt:0
biomed/1472-6807-2-5.txt:0
biomed/1472-6807-2-9.txt:0
biomed/1472-6807-3-1.txt:0
biomed/1472-6807-3-2.txt:0
biomed/1472-6815-2-3.txt:0
biomed/1472-6823-2-2.txt:0
biomed/1472-6823-3-1.txt:0
biomed/1472-6831-2-2.txt:5
biomed/1472-6831-3-1.txt:0
biomed/1472-684X-1-5.txt:0
biomed/1472-684X-2-1.txt:0
biomed/1472-684X-2-2.txt:0
biomed/1472-6874-2-1.txt:0
biomed/1472-6874-2-13.txt:0
biomed/1472-6874-2-8.txt:0
biomed/1472-6874-3-2.txt:0
biomed/1472-6882-1-10.txt:0
biomed/1472-6882-1-11.txt:0
biomed/1472-6882-1-12.txt:0
biomed/1472-6882-1-7.txt:0
biomed/1472-6882-2-10.txt:0
biomed/1472-6882-2-5.txt:0
biomed/1472-6882-3-1.txt:0
biomed/1472-6882-3-3.txt:0
biomed/1472-6890-1-4.txt:0
biomed/1472-6890-2-5.txt:0
biomed/1472-6890-3-2.txt:0
biomed/1472-6904-1-2.txt:0
biomed/1472-6904-2-4.txt:0
biomed/1472-6904-2-5.txt:0
biomed/1472-6904-2-7.txt:0
biomed/1472-6904-3-1.txt:0
biomed/1472-6920-1-3.txt:0
biomed/1472-6920-2-1.txt:0
biomed/1472-6920-2-3.txt:0
biomed/1472-6947-1-2.txt:0
biomed/1472-6947-1-5.txt:2
biomed/1472-6947-1-6.txt:0
biomed/1472-6947-2-4.txt:0
biomed/1472-6947-2-7.txt:0
biomed/1472-6947-3-5.txt:0
biomed/1472-6947-3-8.txt:0
biomed/1472-6955-2-1.txt:3
biomed/1472-6963-1-11.txt:0
biomed/1472-6963-1-8.txt:2
biomed/1472-6963-2-10.txt:0
biomed/1472-6963-3-1.txt:0
biomed/1472-6963-3-11.txt:0
biomed/1472-6963-3-12.txt:1
biomed/1472-6963-3-13.txt:1
biomed/1472-6963-3-14.txt:0
biomed/1472-6963-3-6.txt:0
biomed/1472-6963-3-7.txt:1
biomed/1475-2832-1-1.txt:12
biomed/1475-2867-2-10.txt:0
biomed/1475-2867-2-15.txt:0
biomed/1475-2867-2-7.txt:0
biomed/1475-2867-3-12.txt:0
biomed/1475-2867-3-2.txt:0
biomed/1475-2867-3-3.txt:0
biomed/1475-2867-3-4.txt:0
biomed/1475-2875-1-14.txt:0
biomed/1475-2875-1-5.txt:0
biomed/1475-2875-2-10.txt:0
biomed/1475-2875-2-14.txt:0
biomed/1475-2875-2-4.txt:0
biomed/1475-2883-2-11.txt:0
biomed/1475-2891-1-2.txt:0
biomed/1475-2891-2-1.txt:0
biomed/1475-4924-1-10.txt:0
biomed/1475-4924-1-5.txt:2
biomed/1475-925X-2-1.txt:0
biomed/1475-925X-2-10.txt:0
biomed/1475-925X-2-11.txt:0
biomed/1475-925X-2-12.txt:0
biomed/1475-925X-2-3.txt:0
biomed/1475-925X-2-6.txt:0
biomed/1475-9268-1-1.txt:0
biomed/1475-9268-1-2.txt:0
biomed/1475-9276-1-3.txt:0
biomed/1476-069X-1-3.txt:2
biomed/1476-069X-2-2.txt:0
biomed/1476-069X-2-4.txt:0
biomed/1476-069X-2-7.txt:0
biomed/1476-069X-2-9.txt:0
biomed/1476-0711-2-3.txt:0
biomed/1476-0711-2-7.txt:1
biomed/1476-072X-2-3.txt:0
biomed/1476-072X-2-4.txt:0
biomed/1476-4598-1-3.txt:0
biomed/1476-4598-1-5.txt:0
biomed/1476-4598-1-6.txt:0
biomed/1476-4598-1-8.txt:0
biomed/1476-4598-2-1.txt:0
biomed/1476-4598-2-2.txt:0
biomed/1476-4598-2-20.txt:0
biomed/1476-4598-2-22.txt:0
biomed/1476-4598-2-24.txt:0
biomed/1476-4598-2-25.txt:0
biomed/1476-4598-2-28.txt:0
biomed/1476-4598-2-3.txt:0
biomed/1476-511X-1-2.txt:0
biomed/1476-511X-2-2.txt:0
biomed/1476-511X-2-3.txt:2
biomed/1476-5918-1-2.txt:0
biomed/1476-9433-1-2.txt:0
biomed/1476-9433-1-3.txt:0
biomed/1477-5956-1-1.txt:0
biomed/1477-7525-1-10.txt:3
biomed/1477-7525-1-12.txt:0
biomed/1477-7525-1-9.txt:1
biomed/1477-7819-1-10.txt:0
biomed/1477-7827-1-13.txt:0
biomed/1477-7827-1-17.txt:0
biomed/1477-7827-1-21.txt:4
biomed/1477-7827-1-23.txt:0
biomed/1477-7827-1-27.txt:0
biomed/1477-7827-1-31.txt:0
biomed/1477-7827-1-36.txt:0
biomed/1477-7827-1-43.txt:0
biomed/1477-7827-1-46.txt:0
biomed/1477-7827-1-48.txt:1
biomed/1477-7827-1-54.txt:0
biomed/1477-7827-1-6.txt:0
biomed/1477-7827-1-9.txt:0
biomed/1478-1336-1-2.txt:0
biomed/1478-1336-1-3.txt:0
biomed/1478-1336-1-4.txt:0
biomed/1478-7954-1-3.txt:0
biomed/ar104.txt:0
biomed/ar118.txt:0
biomed/ar120.txt:0
biomed/ar130.txt:0
biomed/ar140.txt:0
biomed/ar149.txt:0
biomed/ar297.txt:0
biomed/ar309.txt:0
biomed/ar319.txt:0
biomed/ar321.txt:0
biomed/ar328.txt:0
biomed/ar331.txt:0
biomed/ar383.txt:0
biomed/ar387.txt:4
biomed/ar407.txt:0
biomed/ar408.txt:0
biomed/ar409.txt:0
biomed/ar422.txt:0
biomed/ar429.txt:1
biomed/ar430.txt:0
biomed/ar601.txt:0
biomed/ar612.txt:0
biomed/ar615.txt:0
biomed/ar619.txt:0
biomed/ar624.txt:0
biomed/ar68.txt:1
biomed/ar745.txt:0
biomed/ar750.txt:0
biomed/ar774.txt:1
biomed/ar778.txt:0
biomed/ar79.txt:0
biomed/ar792.txt:0
biomed/ar795.txt:0
biomed/ar799.txt:0
biomed/ar93.txt:0
biomed/bcr273.txt:0
biomed/bcr284.txt:0
biomed/bcr285.txt:0
biomed/bcr294.txt:0
biomed/bcr303.txt:0
biomed/bcr317.txt:0
biomed/bcr45.txt:0
biomed/bcr458.txt:1
biomed/bcr567.txt:0
biomed/bcr568.txt:0
biomed/bcr570.txt:0
biomed/bcr571.txt:0
biomed/bcr583.txt:0
biomed/bcr588.txt:0
biomed/bcr602.txt:0
biomed/bcr605.txt:1
biomed/bcr607.txt:0
biomed/bcr618.txt:0
biomed/bcr620.txt:0
biomed/bcr631.txt:0
biomed/bcr635.txt:0
biomed/cc103.txt:0
biomed/cc1044.txt:0
biomed/cc105.txt:0
biomed/cc1476.txt:1
biomed/cc1477.txt:0
biomed/cc1495.txt:0
biomed/cc1497.txt:0
biomed/cc1498.txt:1
biomed/cc1529.txt:0
biomed/cc1538.txt:0
biomed/cc1547.txt:0
biomed/cc1843.txt:0
biomed/cc1852.txt:0
biomed/cc1856.txt:0
biomed/cc1882.txt:0
biomed/cc2160.txt:0
biomed/cc2167.txt:1
biomed/cc2171.txt:0
biomed/cc2172.txt:0
biomed/cc2190.txt:0
biomed/cc2358.txt:0
biomed/cc3.txt:1
biomed/cc300.txt:0
biomed/cc303.txt:0
biomed/cc343.txt:0
biomed/cc350.txt:0
biomed/cc367.txt:0
biomed/cc4.txt:0
biomed/cc713.txt:0
biomed/cc973.txt:0
biomed/cc991.txt:0
biomed/cvm-2-1-038.txt:0
biomed/cvm-2-4-180.txt:0
biomed/cvm-2-4-187.txt:0
biomed/cvm-2-6-278.txt:1
biomed/cvm-2-6-286.txt:0
biomed/gb-2000-1-1-research002.txt:0
biomed/gb-2000-1-2-research0003.txt:0
biomed/gb-2001-2-10-research0041.txt:0
biomed/gb-2001-2-10-research0042.txt:0
biomed/gb-2001-2-11-research0045.txt:0
biomed/gb-2001-2-11-research0046.txt:0
biomed/gb-2001-2-12-research0051.txt:0
biomed/gb-2001-2-12-research0053.txt:0
biomed/gb-2001-2-12-research0054.txt:0
biomed/gb-2001-2-12-research0055.txt:0
biomed/gb-2001-2-2-research0004.txt:0
biomed/gb-2001-2-3-research0007.txt:0
biomed/gb-2001-2-3-research0008.txt:0
biomed/gb-2001-2-4-research0010.txt:0
biomed/gb-2001-2-4-research0011.txt:0
biomed/gb-2001-2-4-research0012.txt:0
biomed/gb-2001-2-4-research0014.txt:0
biomed/gb-2001-2-6-research0018.txt:0
biomed/gb-2001-2-6-research0020.txt:0
biomed/gb-2001-2-6-research0021.txt:0
biomed/gb-2001-2-7-research0024.txt:0
biomed/gb-2001-2-7-research0025.txt:0
biomed/gb-2001-2-8-research0027.txt:0
biomed/gb-2001-2-8-research0030.txt:0
biomed/gb-2001-2-8-research0031.txt:0
biomed/gb-2001-2-8-research0032.txt:0
biomed/gb-2001-2-9-research0035.txt:0
biomed/gb-2001-2-9-research0037.txt:0
biomed/gb-2001-3-1-research0001.txt:0
biomed/gb-2001-3-1-research0004.txt:0
biomed/gb-2001-3-1-research0005.txt:0
biomed/gb-2002-3-10-research0052.txt:0
biomed/gb-2002-3-10-research0053.txt:0
biomed/gb-2002-3-10-research0054.txt:0
biomed/gb-2002-3-10-research0055.txt:0
biomed/gb-2002-3-10-research0056.txt:0
biomed/gb-2002-3-11-research0059.txt:0
biomed/gb-2002-3-11-research0060.txt:0
biomed/gb-2002-3-11-research0061.txt:0
biomed/gb-2002-3-11-research0062.txt:0
biomed/gb-2002-3-11-research0065.txt:0
biomed/gb-2002-3-12-research0071.txt:0
biomed/gb-2002-3-12-research0072.txt:0
biomed/gb-2002-3-12-research0075.txt:1
biomed/gb-2002-3-12-research0077.txt:0
biomed/gb-2002-3-12-research0078.txt:0
biomed/gb-2002-3-12-research0079.txt:0
biomed/gb-2002-3-12-research0080.txt:0
biomed/gb-2002-3-12-research0081.txt:0
biomed/gb-2002-3-12-research0082.txt:0
biomed/gb-2002-3-12-research0083.txt:0
biomed/gb-2002-3-12-research0085.txt:0
biomed/gb-2002-3-12-research0086.txt:0
biomed/gb-2002-3-12-research0087.txt:0
biomed/gb-2002-3-12-research0088.txt:0
biomed/gb-2002-3-2-research0008.txt:0
biomed/gb-2002-3-2-research0009.txt:0
biomed/gb-2002-3-3-research0011.txt:0
biomed/gb-2002-3-3-research0012.txt:0
biomed/gb-2002-3-4-research0018.txt:0
biomed/gb-2002-3-4-research0019.txt:0
biomed/gb-2002-3-5-research0020.txt:0
biomed/gb-2002-3-5-research0021.txt:1
biomed/gb-2002-3-5-research0022.txt:0
biomed/gb-2002-3-5-research0023.txt:0
biomed/gb-2002-3-5-research0024.txt:0
biomed/gb-2002-3-5-research0025.txt:0
biomed/gb-2002-3-6-research0029.txt:0
biomed/gb-2002-3-6-software0001.txt:0
biomed/gb-2002-3-7-research0032.txt:0
biomed/gb-2002-3-7-research0035.txt:0
biomed/gb-2002-3-7-research0036.txt:0
biomed/gb-2002-3-7-research0037.txt:0
biomed/gb-2002-3-8-research0038.txt:0
biomed/gb-2002-3-8-research0039.txt:0
biomed/gb-2002-3-8-research0040.txt:0
biomed/gb-2002-3-9-research0043.txt:0
biomed/gb-2002-3-9-research0044.txt:0
biomed/gb-2002-3-9-research0045.txt:0
biomed/gb-2002-3-9-research0046.txt:0
biomed/gb-2002-3-9-research0048.txt:0
biomed/gb-2002-3-9-research0049.txt:0
biomed/gb-2002-3-9-research0051.txt:0
biomed/gb-2002-4-1-r1.txt:0
biomed/gb-2002-4-1-r2.txt:0
biomed/gb-2003-4-1-r5.txt:0
biomed/gb-2003-4-1-r7.txt:0
biomed/gb-2003-4-2-r11.txt:0
biomed/gb-2003-4-2-r14.txt:0
biomed/gb-2003-4-2-r16.txt:0
biomed/gb-2003-4-2-r8.txt:3
biomed/gb-2003-4-2-r9.txt:0
biomed/gb-2003-4-3-r17.txt:0
biomed/gb-2003-4-3-r18.txt:0
biomed/gb-2003-4-3-r20.txt:0
biomed/gb-2003-4-4-r24.txt:11
biomed/gb-2003-4-4-r26.txt:0
biomed/gb-2003-4-4-r28.txt:0
biomed/gb-2003-4-5-r30.txt:0
biomed/gb-2003-4-5-r32.txt:0
biomed/gb-2003-4-5-r34.txt:0
biomed/gb-2003-4-6-r37.txt:0
biomed/gb-2003-4-6-r39.txt:0
biomed/gb-2003-4-6-r41.txt:0
biomed/gb-2003-4-7-r42.txt:0
biomed/gb-2003-4-7-r43.txt:0
biomed/gb-2003-4-7-r46.txt:0
biomed/gb-2003-4-8-r50.txt:0
biomed/gb-2003-4-8-r51.txt:0
biomed/gb-2003-4-9-r57.txt:0
biomed/gb-2003-4-9-r58.txt:0
biomed/gb-2003-4-9-r60.txt:0
biomed/rr166.txt:0
biomed/rr167.txt:0
biomed/rr171.txt:0
biomed/rr172.txt:0
biomed/rr191.txt:0
biomed/rr196.txt:0
biomed/rr37.txt:10
biomed/rr73.txt:0
biomed/rr74.txt:0
```
This command looks through all the text files in the biomed directory and for each file prints out the number of lines containing the pattern "adults" withought the quotes. This is useful because that means we can get the number of instances of a pattern for multiple files from one command, and also we can verify that some files have the pattern through the number of lines it occurs and other files don't. 

---

Option #2: -l
Source: https://www.geeksforgeeks.org/grep-command-in-unixlinux/ 

Example #1: 

```
#Command
grep -l "improved health" biomed/*.txt

#Output
biomed/1468-6708-3-1.txt
biomed/1475-2875-1-14.txt

```
This command looks through all the text files in the biomed directory and prints out the file names that have instances of the pattern "improved health". This can be useful if we just want to know the files that contain information related to improvng health or any other specific topic and we don't need details about the specific instances themselves. 

Example #2: 

```
#Command
grep -l "problem" biomed/1468-6708-3-3.txt

#Output
biomed/1468-6708-3-3.txt

```
This comand looks through the specified file (biomed/1468-6708-3-3.txt) and searches for the instance of the pattern "problem" withought the quotes. And if there is a instance of that pattern then it prints out the file name. This is useful if we just want to see if a file contains a instance of a specific pattern withought any additional details because if the same file name is printed in output we can take that as true, and there are instances of the pattern and if the filename is not printed out then that file contains no instances of that pattern and we can take it as false. 

---

Option #3: -v
Source: https://www.geeksforgeeks.org/grep-command-in-unixlinux/ 

Example #1: 

```
#Command
grep -v "a" biomed/1468-6708-3-1.txt

#Output


  
    
      
        Introduction
        elderly [ 9 ] .
      
      
        
          Study
        
        
        
        
          ] .
          (for persons who were never in excellent, very good, or
          report results using only the simpler definition.
          findings.
        
        
        
        
        
      
      
        Results
        likely.
        from 25 to 29.9. The second column, which shows results
        under 20.
        groups.
        YOL or YHL.
      
      
        Discussion
        
        
        
          YHL.
        
        
        
      
      
        Conclusion
        'overweight' by the NHLBI guidelines. This suggests using
      
      
        Competing interests
      
      
        CESD Center for Epidemiologic Studies Depression
        poor?
      
    


```

This command looks through the specified file (biomed/1468-6708-3-1.txt) and prints out all lines not containing instances of the letter "a". This is useful because if we want to find all lines withought a specific pattern we can easily find it. And we can verify that all lines have a specified pattern by using this command and seeing if nothing prints out because that means every line has that pattern. 

Example #2: 

```
#Command
grep -v "." biomed/1468-6708-3-1.txt biomed/1468-6708-3-3.txt

#Output
biomed/1468-6708-3-1.txt:
biomed/1468-6708-3-3.txt:

```
This command looks through the 2 specified files (biomed/1468-6708-3-1.txt and biomed/1468-6708-3-3.txt) and for each file prints out all the lines that do not contain a period ("."). This is useful because we can verify quickly no lines were printed out for either file meaning every line in both files contains a period. So we can easily check that multiple files have instances of a specific pattern on every line through this command. 

---

Option #4: -n
Source: https://www.geeksforgeeks.org/grep-command-in-unixlinux/ 

Example #1: 

```
#Command
grep -n "adults" biomed/1468-6708-3-1.txt

#Output
6:        Older adults are frequently counseled to lose weight,
10:        non-smoking older adults have investigated the association
16:        adults drew similar conclusions [ 7 ] .
17:        Many healthy older adults report gradual weight gain
27:        In older adults, risk factors may have a greater effect
36:        years of being healthy, in a cohort of older adults for
42:        modification interventions in older adults.
50:          population-based longitudinal study of 5,888 adults aged
324:          categories could be combined for older adults. Since
338:          interventions for older adults who were merely overweight
347:          adults are the subjects. This is particularly important
350:          33 34 ] . For older adults, the risks associated with
352:          outcome for a trial of weight loss in older adults
356:          found for underweight older adults. Clinical trials whose
406:        older adults, especially for women. Future efforts to
409:        no excess risk for older adults who would be classified as
412:        obese or underweight older adults, and discouraging trials
413:        that address older adults who are merely overweight.

```
This command looks throguh the specified file (1468-6708-3-1.txt ) in the biomed directory for the lines containing instances of the pattern "adults" withought the quotes and prints out every line containing a instance of that pattern along wiht the line number. This is useful because we dont have to search through the file for specific lines the command simply tells us the line number along with the line of the pattern instance which can save us time later on. If we want to go back into the file to edit it now we have the line numbers which will make it easier. 


Example #2: 

```
#Command
grep -n "Introduction" biomed/*.txt

#Output
biomed/1468-6708-3-1.txt:5:        Introduction
biomed/1468-6708-3-4.txt:5:        Introduction
biomed/1471-2091-2-11.txt:5:        Introduction
biomed/1471-2091-3-23.txt:403:        binding specificity. Introduction of a single ACS like
biomed/1471-2105-1-1.txt:5:        Introduction
biomed/1471-2105-2-8.txt:5:        Introduction
biomed/1471-2105-3-24.txt:5:        Introduction
biomed/1471-2121-1-2.txt:5:        Introduction
biomed/1471-2121-3-10.txt:140:          Introduction,) [ 11 ] , we expected that the Tag
biomed/1471-213X-1-10.txt:5:        Introduction
biomed/1471-213X-1-10.txt:332:        Introduction of single copy transgenes into the 
biomed/1471-213X-1-9.txt:5:        Introduction
biomed/1471-213X-2-1.txt:5:        Introduction
biomed/1471-2156-2-7.txt:5:        Introduction
biomed/1471-2156-3-16.txt:554:        Introduction). Furthermore, the 
biomed/1471-2156-4-9.txt:128:          anterior cross-vein. Introduction of a single mutant copy
biomed/1471-2164-3-8.txt:5:        Introduction
biomed/1471-2172-2-10.txt:5:        Introduction
biomed/1471-2180-1-16.txt:5:        Introduction
biomed/1471-2180-1-31.txt:447:          cloned. Introduction of the plasmids into 
biomed/1471-2199-2-10.txt:5:        Introduction
biomed/1471-2199-2-2.txt:5:        Introduction
biomed/1471-2199-2-4.txt:718:          As described in the Introduction, recent studies
biomed/1471-2199-2-5.txt:5:        Introduction
biomed/1471-2199-2-5.txt:333:        the expression of CD5 on these subsets (see Introduction to
biomed/1471-2199-2-6.txt:5:        Introduction
biomed/1471-2202-2-3.txt:5:        Introduction
biomed/1471-230X-1-10.txt:5:        Introduction
biomed/1471-2334-3-9.txt:5:        Introduction
biomed/1471-2350-2-2.txt:5:        Introduction
biomed/1471-2350-4-2.txt:450:        the Introduction: the protective or detrimental effects of
biomed/1471-2377-1-2.txt:5:        Introduction
biomed/1471-2407-1-13.txt:5:        Introduction
biomed/1471-2407-1-6.txt:5:        Introduction
biomed/1471-2415-3-5.txt:847:          apoptosis [ 61 ] . As indicated in the Introduction,
biomed/1471-2458-1-9.txt:5:        Introduction
biomed/1471-2474-2-3.txt:10:        Introduction
biomed/1471-5945-1-3.txt:5:        Introduction
biomed/1472-6750-1-12.txt:444:          the presence of 250 μg/ml 6-thiogaunine. Introduction of
biomed/1472-6750-1-13.txt:5:        Introduction
biomed/1472-6874-2-1.txt:5:        Introduction
biomed/1472-6882-1-11.txt:5:        Introduction
biomed/1472-6882-2-5.txt:5:        Introduction
biomed/1472-6890-2-5.txt:5:        Introduction
biomed/1472-6963-2-10.txt:5:        Introduction
biomed/1475-2832-1-1.txt:5:        Introduction
biomed/1475-2875-2-10.txt:5:        Introduction
biomed/1476-511X-2-2.txt:5:        Introduction
biomed/1477-7819-1-10.txt:5:        Introduction
biomed/1477-7827-1-36.txt:672:        As mentioned in the Introduction, recent studies of the
biomed/1477-7827-1-54.txt:5:        Introduction
biomed/1478-1336-1-3.txt:5:        Introduction
biomed/1478-1336-1-4.txt:387:        Introduction, ERα and ERβ must interact differentially with
biomed/ar104.txt:7:          Introduction
biomed/ar104.txt:152:        Introduction
biomed/ar118.txt:7:          Introduction
biomed/ar118.txt:250:        Introduction
biomed/ar120.txt:7:          Introduction
biomed/ar120.txt:206:        Introduction
biomed/ar130.txt:7:          Introduction
biomed/ar130.txt:119:        Introduction
biomed/ar140.txt:5:        Introduction
biomed/ar149.txt:5:        Introduction
biomed/ar297.txt:5:        Introduction
biomed/ar297.txt:306:          Introduction
biomed/ar309.txt:5:        Introduction
biomed/ar319.txt:5:        Introduction
biomed/ar321.txt:5:        Introduction
biomed/ar328.txt:5:        Introduction
biomed/ar331.txt:5:        Introduction
biomed/ar383.txt:5:        Introduction
biomed/ar387.txt:5:        Introduction
biomed/ar407.txt:5:        Introduction
biomed/ar408.txt:5:        Introduction
biomed/ar409.txt:5:        Introduction
biomed/ar409.txt:244:          Supplementary Introduction
biomed/ar422.txt:5:        Introduction
biomed/ar429.txt:5:        Introduction
biomed/ar430.txt:5:        Introduction
biomed/ar601.txt:5:        Introduction
biomed/ar612.txt:5:        Introduction
biomed/ar615.txt:5:        Introduction
biomed/ar619.txt:5:        Introduction
biomed/ar624.txt:5:        Introduction
biomed/ar68.txt:5:        Introduction
biomed/ar745.txt:5:        Introduction
biomed/ar750.txt:5:        Introduction
biomed/ar774.txt:5:        Introduction
biomed/ar778.txt:5:        Introduction
biomed/ar79.txt:7:          Introduction
biomed/ar79.txt:122:        Introduction
biomed/ar792.txt:5:        Introduction
biomed/ar792.txt:226:          As described in the Introduction, the aim of studying
biomed/ar795.txt:5:        Introduction
biomed/ar799.txt:5:        Introduction
biomed/ar93.txt:7:          Introduction
biomed/ar93.txt:167:        Introduction
biomed/bcr273.txt:7:          Introduction
biomed/bcr273.txt:287:          Introduction
biomed/bcr284.txt:5:        Introduction
biomed/bcr285.txt:7:          Introduction
biomed/bcr285.txt:225:        Introduction
biomed/bcr294.txt:7:          Introduction
biomed/bcr294.txt:108:          Introduction
biomed/bcr303.txt:5:        Introduction
biomed/bcr317.txt:5:        Introduction
biomed/bcr45.txt:7:          Introduction
biomed/bcr45.txt:222:        Introduction
biomed/bcr458.txt:5:        Introduction
biomed/bcr567.txt:5:        Introduction
biomed/bcr568.txt:5:        Introduction
biomed/bcr570.txt:5:        Introduction
biomed/bcr571.txt:5:        Introduction
biomed/bcr583.txt:5:        Introduction
biomed/bcr588.txt:5:        Introduction
biomed/bcr602.txt:5:        Introduction
biomed/bcr605.txt:5:        Introduction
biomed/bcr607.txt:5:        Introduction
biomed/bcr618.txt:5:        Introduction
biomed/bcr620.txt:5:        Introduction
biomed/bcr631.txt:5:        Introduction
biomed/bcr635.txt:5:        Introduction
biomed/cc103.txt:5:        Introduction
biomed/cc1044.txt:5:        Introduction
biomed/cc105.txt:5:        Introduction
biomed/cc1476.txt:5:        Introduction
biomed/cc1477.txt:5:        Introduction
biomed/cc1495.txt:5:        Introduction
biomed/cc1497.txt:5:        Introduction
biomed/cc1498.txt:5:        Introduction
biomed/cc1529.txt:5:        Introduction
biomed/cc1538.txt:5:        Introduction
biomed/cc1547.txt:5:        Introduction
biomed/cc1843.txt:5:        Introduction
biomed/cc1852.txt:5:        Introduction
biomed/cc1856.txt:5:        Introduction
biomed/cc1882.txt:5:        Introduction
biomed/cc2160.txt:5:        Introduction
biomed/cc2167.txt:5:        Introduction
biomed/cc2171.txt:5:        Introduction
biomed/cc2172.txt:5:        Introduction
biomed/cc2190.txt:5:        Introduction
biomed/cc2358.txt:5:        Introduction
biomed/cc3.txt:5:        Introduction
biomed/cc300.txt:5:        Introduction
biomed/cc343.txt:5:        Introduction
biomed/cc350.txt:5:        Introduction
biomed/cc367.txt:5:        Introduction
biomed/cc4.txt:5:        Introduction
biomed/cc713.txt:5:        Introduction
biomed/cc973.txt:5:        Introduction
biomed/cc991.txt:5:        Introduction
biomed/cvm-2-4-180.txt:5:        Introduction
biomed/cvm-2-4-187.txt:5:        Introduction
biomed/gb-2003-4-5-r34.txt:7:          Introduction to cluster analysis
biomed/rr166.txt:5:        Introduction
biomed/rr167.txt:5:        Introduction
biomed/rr171.txt:5:        Introduction
biomed/rr172.txt:5:        Introduction
biomed/rr191.txt:5:        Introduction
biomed/rr196.txt:5:        Introduction
biomed/rr37.txt:5:        Introduction
biomed/rr73.txt:5:        Introduction
biomed/rr74.txt:5:        Introduction

```
This command looks through all the text files in the biomed directory and for each file prints out the line number and the line containing the instances of the pattern "Introduction". This is useful to verify that certain patterns happen in the same line for multiple files since we can look at the line numbers for each files instance of the word "Introduction" and check if it matches for everything. And we can also make sure every file has only one instance of the word "Introduction" since the specific lines are printed we can check only one line is printed for each file. 

---


