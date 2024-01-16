Hello World!!!

# Lab Report 1 - Remote Access and FileSystem
 ---

1. cd
   
* Example of using the command with no arguments
  <img width="1440" alt="Screen Shot 2024-01-11 at 3 16 47 PM" src="https://github.com/kirustar14/cse15l-lab-reports/assets/148379107/d3f597a2-10b7-4b08-949f-69a0adb467e9"> <br/>
Working directory when command was run: /home <br/>
The system shows no changes besides printing out another terminal line and we can see from the phrase [user@sahara ~] we are still in the same directory as before we ran that command. This is because cd is a command used to change directories and usually you give it a path to a directory to switch into but if we just write cd with no arguments or items following it, it should simply switch into the /home directory and since it was already in that directory to begin with there are no changes. Having no arguments just means we did not write anything in the command line after the cd. We only wrote cd and did enter so there are no arguments provided. <br/>
Is output an error?: No  <br/> <br/>
* Example of using the command with a path to a directory as an argument
   <img width="1440" alt="Screen Shot 2024-01-11 at 3 21 50 PM" src="https://github.com/kirustar14/cse15l-lab-reports/assets/148379107/0b500e72-d8e9-4490-8738-ec91d0a5bc7c"> <br/>
Working directory when command was run: /home <br/>
The system has changed directories into the /home/lecture1 directory from the /home directory. We can see this because in the output the terminal line now says [user@sahara ~/lecture1] which is diffrent than before because before there was no 'lecture1' and it was just [user@sahara ~]. Indiating that we have switched directories into /home/lecture1. In the filesystem we have a lecture1 file and so changing directories means that from the /home or initally overall setup we are now inside the lecture1 file which has the path /home/lecture1. <br/>
Is output an error?: No <br/> <br/>
* Example of using the command with a path to a file as an argument
<img width="1440" alt="Screen Shot 2024-01-16 at 8 36 40 AM" src="https://github.com/kirustar14/cse15l-lab-reports/assets/148379107/6f217c60-b4be-4c4d-bf57-a046055f0405"> <br>
Working directory when command was run: /home/lecture1/messages <br/>
The argument we gave in the command line when we did cd en-us.txt was a path to a file. Because the en-us.txt is a text file inside the /home/lecture1/messages directory and we are trying to change directories from our current directory into that file by using the command cd with that file as a argument. However a directory is actually like a folder and so we get the error 'bash: cd: en-us.txt: Not a directory' which is indicating that the argument we provided (en-us.txt) is not a directory. because it is a text file and not a folder we can go into.  <br/>
Is output an error?: Yes. The output indicates that there is a error with the argument we provided, and it is that the argument is not a directory. In order for the argument to be a directory it would need to be a folder that we can switch into. However the argument we provided is a path to the file en-us.txt from our current working directory ( inside the messages folder) and so the command cd en-us.txt does not work and results in a error. Because we need to provide a path to a directory to use the command cd or provide no arguments at all to return to home directory. But the argument we provided doesnt math either of thoose conditions. <br/> <br/>

   ---
3. ls

* Example of using the command with no arguments
  <img width="1440" alt="Screen Shot 2024-01-16 at 9 59 15 AM" src="https://github.com/kirustar14/cse15l-lab-reports/assets/148379107/8806abb4-7d88-4fb3-9a2d-d3579096c7e6">
Working directory when command was run: /home <br/>
The command ls gies you a list of all the folders/files and items directly inside your current working directory. Because we are in the directory /home when the command was run and the only thing inside that directory is the lecture1 folder, when we run the command ls it prints out lecture1 which is the only item inside our working directory.   <br/>
Is output an error?: No. <br/> <br/>

* Example of using the command with a path to a directory as an argument
  <img width="1440" alt="Screen Shot 2024-01-16 at 10 14 10 AM" src="https://github.com/kirustar14/cse15l-lab-reports/assets/148379107/6f3faffd-b16a-4864-844f-cb0ce2d62e21">
Working directory when command was run: /home <br/>
The command ls gives you a list of all the folders/files and items directly inside your current working directory. However we wrote ls lecture1, and lecture1 is a directory on its own. So when we write the command ls with another directory as its argument the terminal will print out all the folders/file in that specific directory not in the current working directory. So the terminal printed out 'Hello.class  Hello.java  messages  README' which are are all the items in the /home/lecture1 directory. Whereas if we had just written ls it would instead print out the items in our current working directory. <br/>
Is output an error?: No. <br/> <br/>

* Example of using the command with a path to a file as an argument
<img width="1440" alt="Screen Shot 2024-01-16 at 10 30 56 AM" src="https://github.com/kirustar14/cse15l-lab-reports/assets/148379107/c6d22415-5887-4a99-9efe-367bb5213b0a">
Working directory when command was run: /home/lecture1 <br/>
The command ls gives you a list of all the folders/files and items directly inside your current working directory. However we wrote ls Hello.java and Hello.java is a file inside our current working directory (inside the lecture1 folder). And we see the terminal simply prints out the name of the file we provided as a argument. So if we provide a argument that is a file inside oru current working directory with the ls command it simply prints out the name of the file agian in the terminal. <br/>
Is output an error?: No. <br/> <br/>

   ---
4. cat

* Example of using the command with no arguments
  
* Example of using the command with a path to a directory as an argument
  
* Example of using the command with a path to a file as an argument
