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
1. ssh kmarikumaran@ieng6-201.ucsd.edu
2. <enter>

First I typed 'ssh kmarikumaran@ieng6-201.ucsd.edu' using the respective letters/numbers on the keyboard, and then I pressed <enter> key to log into the ieng6 remote computer. 
```

---

# Step 5: Clone your fork of the repository from your Github account (using the SSH URL)
---

<img width="688" alt="Screen Shot 2024-02-27 at 6 47 25 PM" src="https://github.com/kirustar14/cse15l-lab-reports/assets/148379107/4933598c-4b88-4e0a-8508-4561b24dc593">

```
Keys Pressed: 
1. git clone git@github.com:kirustar14/lab7.git
2. <enter>

First I typed the command 'git clone git@github.com:kirustar14/lab7.git', which had the ssh url from my forked repository of lab 7 using the letter/numbers on keyboard. And then I pressed the <enter> key in order to clone that lab7 repository into my ieng6 remote computer which I was already logged into from the last step. 
```

---

# Step 6: Run the tests, demonstrating that they fail
---

<img width="1077" alt="Screen Shot 2024-02-27 at 7 31 47 PM" src="https://github.com/kirustar14/cse15l-lab-reports/assets/148379107/175a2444-a694-4566-8339-9e040958e84b">

```
Keys Pressed: 
1. cd lab7
2. <enter>
3. javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
4. <enter>
5. java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests
6. <enter>

First I changed directories into lab7 by running the command 'cd lab7' and pressing the key <enter>. Then I typed out the command to compile all the java files in the lab 7 directory by typing 'javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java' using the respective letters/numbers on the keyboard. Then I pressed the <enter> key to do the compilation of all java files in my current directory (all java files in the lab7 folder). Then to run the tests I typed in the command 'java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests' and pressed the <enter> key to run the tests. 
```

---

# Step 7: Edit the code file to fix the failing test
---
<img width="1075" alt="Screen Shot 2024-02-27 at 7 08 54 PM" src="https://github.com/kirustar14/cse15l-lab-reports/assets/148379107/9caafb76-3cf8-4943-834e-024ecabe76fe">

```
Keys Pressed: 
1. vim ListExamples.java
2. 43J
3. E
4. R
5. 2
6. <esc>
7. :wq
8. <enter> 


First I typed 'vim ListExamples.java' to open the file ListExamples.java which has the error in the terminal with vim. Then I pressed 43J, because J moves your cursor down and pressing 43J moved my cursor down 43 times and the error to fix is on that line. Then I pressed E which moves my cursor to the end of the word 'index1' which is where my error is because I need to change the 1 to a 2. Then I press R, which goes to replace which lets me replace the character my cursor is currently on (1) with a character I will type next. So I press 2, to replace the 1 with a 2. Then I press <esc> key to go back to normal mode. Then I press :wq, and press the <enter> key which saves my work and exits vim. 
```

---

# Step 8: Run the tests, demonstrating that they now succeed
---
<img width="897" alt="Screen Shot 2024-02-27 at 7 34 11 PM" src="https://github.com/kirustar14/cse15l-lab-reports/assets/148379107/f5ae8cc8-fdc0-4a82-868c-2053105c127e">

```
Keys Pressed: 
1. <up>
2. <up>
3. <up>
8. <enter> 
9. <up>
10. <up>
11. <up> 
12. <enter>


First I pressed the <up> key three times because the command 'javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java' was 3 up in my command history and then I pressed <enter> to recompile all the java files in lab7. The I pressed <up> key 3 times again, because now the command 'java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests' was 3 up in my history, and I pressed <enter> to run the command which ran the tester file and now all the tests worked. 
```

---
# Step 9: Commit and push the resulting change to your Github account (you can pick any commit message!)
---


<img width="608" alt="Screen Shot 2024-02-27 at 7 41 58 PM" src="https://github.com/kirustar14/cse15l-lab-reports/assets/148379107/488770c1-5245-40fa-832d-864521bc74ce">

```
Keys Pressed: 
1. git commit -a -m "Fixed Lab7"
2. <enter> 
3. git push
4. <enter>


First I typed the command git commit -a -m "Fixed Lab7", which adds all changes to be commited and commits them with the message "Fixed Lab7", and then I pressed the key <enter> to run this command. Then I typed the command git push, and pressed the <enter> key again to run this command which pushed my changes to the orignal branch, my fork of the lab7 repository. 
```
---

