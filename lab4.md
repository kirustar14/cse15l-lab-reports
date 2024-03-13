Hello World!!!

# Lab Report 4 - Vim
Name: Kiruthika Marikumaran 
PID: A17877875
 
---

# Step 4: Log into ieng6
---
<img width="995" alt="Screen Shot 2024-02-27 at 6 45 55 PM" src="https://github.com/kirustar14/cse15l-lab-reports/assets/148379107/609f8be8-e35f-401e-819d-d8106e441e99">

```
Keys Pressed: 
1. ssh
2. <space>
3. kmarikumaran@ieng6-201.ucsd.edu
4. <enter>

```
First I typed 'ssh kmarikumaran@ieng6-201.ucsd.edu' using the respective letters/numbers and the <space> key on the keyboard, and then I pressed <enter> key to log into the ieng6 remote computer. 

---

# Step 5: Clone your fork of the repository from your Github account (using the SSH URL)
---

<img width="688" alt="Screen Shot 2024-02-27 at 6 47 25 PM" src="https://github.com/kirustar14/cse15l-lab-reports/assets/148379107/4933598c-4b88-4e0a-8508-4561b24dc593">

```
Keys Pressed: 
1. git
2. <space>
3. clone
4. <sapce>
5. git@github.com:kirustar14/lab7.git
6. <enter>

```
First I typed the command 'git clone git@github.com:kirustar14/lab7.git', which had the ssh url from my forked repository of lab 7 using the letter/numbers and the <space> key on keyboard. And then I pressed the <enter> key in order to clone that lab7 repository into my ieng6 remote computer which I was already logged into from the last step. 

---

# Step 6: Run the tests, demonstrating that they fail
---

<img width="544" alt="Screen Shot 2024-03-12 at 8 55 48 PM" src="https://github.com/kirustar14/cse15l-lab-reports/assets/148379107/7c45a973-2702-4a8b-a7a5-8113f5b5314d">


```
Keys Pressed: 
1. cd
2. <sapce>
3. lab7
4. <enter>
5. bash
6. <space>
7. test.sh
8. <enter>

```

First I changed directories into lab7 by running the command 'cd lab7' and pressing the key <enter>. Then I typed out the command 'bash test.sh' using the respective letters/numbers and the <space> key to compile all the java files in the lab 7 directory and run the tests. Because inside the test.sh file you have the command 'javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java' whcih compiles all java files and the command 'java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests' which lets you run the tests in the ListExamplesTests.java file. 

---

# Step 7: Edit the code file to fix the failing test
---
<img width="564" alt="Screen Shot 2024-03-12 at 8 57 21 PM" src="https://github.com/kirustar14/cse15l-lab-reports/assets/148379107/a48f60e1-bd07-4e02-b5c2-ea2e39ec415a">


```
Keys Pressed: 
1. vim
2. <space>
3. ListExamples.java
4. 4
5. 3
6. J
7. E
8. R
9. 2
10. <esc>
11. :
12. w
13. q
14. <enter> 

```

First I typed 'vim ListExamples.java' using the respective letters/numbers and the <space> key to open the file ListExamples.java which has the error in the terminal with vim. Then I pressed 4, then 3, then J, because J moves your cursor down and pressing 4 then 3 then J moved my cursor down 43 times and the error to fix is on that line. Then I pressed E which moves my cursor to the end of the word 'index1' which is where my error is because I need to change the 1 to a 2. Then I press R, which goes to replace which lets me replace the character my cursor is currently on (1) with a character I will type next. So I press 2, to replace the 1 with a 2. Then I press <esc> key to go back to normal mode. Then I press :, then w, then, q, and press the <enter> key which saves my work and exits vim. 

---

# Step 8: Run the tests, demonstrating that they now succeed
---
<img width="398" alt="Screen Shot 2024-03-12 at 8 57 57 PM" src="https://github.com/kirustar14/cse15l-lab-reports/assets/148379107/84bb61fa-3cdb-409f-a6d9-073fb0e25cc3">


```
Keys Pressed: 
1. bash
2. <space>
3. test.sh
8. <enter> 

```
Finally I typed 'bash test.sh' command again using the respective letters/numbers and <space> key on keyboard and pressed the <enter> key to compile all the java files in the lab7 directory and rerun the tests.

---
# Step 9: Commit and push the resulting change to your Github account (you can pick any commit message!)
---

<img width="678" alt="Screen Shot 2024-03-12 at 9 01 55 PM" src="https://github.com/kirustar14/cse15l-lab-reports/assets/148379107/e56959d5-220a-4fd5-9129-9d9a9cf01de9">

```
Keys Pressed: 
1. git
2. <space>
3. commit
4. <sapce>
5. -a
6. <space>
7. -m
8. <space>
9. "Fixed
10. <space>
11. Lab7"
12. <enter> 
13. git
14. <sapce>
15. push
16. <enter>

```
First I typed the command git commit -a -m "Fixed Lab7" using the <sapce> key and the respective letters/numbers on keyboard, which adds all changes to be commited and commits them with the message "Fixed Lab7", and then I pressed the key <enter> to run this command. Then I typed the command 'git push', and pressed the <enter> key again to run this command which pushed my changes to the orignal branch, my fork of the lab7 repository. 

---

