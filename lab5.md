Hello World!!!

# Lab Report 5 - Putting it All Together 
Name: Kiruthika Marikumaran 
PID: A17877875
 
---

# Part 1: Debugging Scenario
---

Edstem Cnversation: 

1. Student: Spongebob Squarepants

I am failing my filter test in ListExamples and I don't know why. The list was expected to be [Fire, air, 123, hi], but the actual list was [blueeee]. I think theres a problem with which items I am adding to my list but I don't know how to fix it. Can you please help me solve this issue? Thank you! 


<img width="564" alt="Screen Shot 2024-03-12 at 7 51 37 PM" src="https://github.com/kirustar14/cse15l-lab-reports/assets/148379107/d97da016-a633-4524-8c9d-703c5a2da4e2">

---

2. TA

Hi! It looks like the issue stems from how you are adding the items to the final list in filter since none of the items in the expected showed up in the actual. Could you try identifying inside the filter method where you are checking if a item should be added to the list or not? 

---
3. Student: Spongebob Squarepants

Oh that makes a lot of sense, originally I had my filter method adding items if they were not approved by the string checker. I changed the line !sc.checkString(s) to just sc.checkString(s). However I am getting a different problem now and the filter test is still failing. There is only one item that appears in the list (hi) when the expected list is [Fire, air, 123, hi]. I think it is because of how many items I am adding to the list but I dont knwo where the problem is. Can you help me solve this please? 

Original Filter Method: 
<img width="509" alt="Screen Shot 2024-03-12 at 7 59 26 PM" src="https://github.com/kirustar14/cse15l-lab-reports/assets/148379107/06e1ec7f-f2ca-4010-aa23-d58a4fac890a">

New Filter Method: 
<img width="508" alt="Screen Shot 2024-03-12 at 7 59 42 PM" src="https://github.com/kirustar14/cse15l-lab-reports/assets/148379107/1ffae1bf-c625-4f54-afad-45d0d50af49c">

New Test Results: 
<img width="479" alt="Screen Shot 2024-03-12 at 7 59 56 PM" src="https://github.com/kirustar14/cse15l-lab-reports/assets/148379107/8f1b155e-c7ab-4a6f-911c-ddb5b7da3478">

---
4. TA

It seems like you are not adding all the items the list should have but the string checker itself is still working. So the problem may be with how you make the final list itself? Could you check where and when you create the list?

---
5. Student: Spongebob Squarepants

Ah I see I was able to fix it now! I realized I was initializing the list in each iteration of the for loop so the previous items went away when a new item was added. Because I had the line 'result = new ArrayList<>();' inside my for loop. And thats why in the end only the "hi" showed up in the list because it was the last item added after passing the string checker. I simply took that line out. And I ran the command 'bash test.sh' in the terminal to run my tests which caught the bug in the first place, and now they all pass! Thank you so much for your help!

Original Filter Method in ListExamples.java: 
<img width="516" alt="Screen Shot 2024-03-12 at 8 08 47 PM" src="https://github.com/kirustar14/cse15l-lab-reports/assets/148379107/0e0e39cc-1a0a-4ce7-9e9e-44f19435a9e0">

Fixed Filter Method in ListExamples.java: 
<img width="521" alt="Screen Shot 2024-03-12 at 8 07 34 PM" src="https://github.com/kirustar14/cse15l-lab-reports/assets/148379107/61830a13-4306-494b-ad34-ccf7be201671">


testFilter Method in ListExamplesTests.java: 
<img width="437" alt="Screen Shot 2024-03-12 at 8 15 18 PM" src="https://github.com/kirustar14/cse15l-lab-reports/assets/148379107/630c511c-bff2-4c54-85d4-8bd360a578ef">


Tests Passing: By running command 'bash test.sh' which goes to test.sh file that compiles all java files in this directory and runs the ListExamplesTests.java file
<img width="406" alt="Screen Shot 2024-03-12 at 8 07 12 PM" src="https://github.com/kirustar14/cse15l-lab-reports/assets/148379107/0a094492-3463-4188-bf3f-121ab492c543">

---
6. TA

Good job on finding the bug! If you need any more help please feel free to ask!

# Part 2: Reflection
---
Something interesting I learned from the second half of this quarter was the java debuggers! I have never used jdb before and I found it very cool how you can pause running your program at specific lines and catch the bug right around where you think it was located. It was like solving a puzzle and finding bugs/issues in my code became a lot easier and faster when I used jdb. Before I would simply look through all my code manually and I wouldn't set up any tests specifically. But now I can write test cases meant to find bugs and I can use a debugger to go back and quickly see where the problem is. Another thing I found very cool was how many things you can do from just the command line. I didnt know you could create files from the terminal or edit them using Vim and realizing that I could write entire programs from just the terminal was amazing. I think if I learn all the shortcuts on vim for moving around it would save a lot of time and be much faster rather than opening up the actual file itself in VS code. All in all, I learned a lot of new techniques and technologies to better my efficiency in writing programs through this class and I am very excited to improve my knowledge in scripting languages/software tools!
