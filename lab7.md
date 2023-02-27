# Lab Report 4

## Step 1 : Log into ieng6 account 

The first step to after the timer start is to log in to the account. 

  Key pressed: `<up><enter>`
  
  The last time the command `ssh cs15lwi23asx@ieng6.ucsd.edu` is just one line above in search history, so accessed it and ran it in the same way. 
  
  Below is the screenshot of successful login. 

 ![image](https://user-images.githubusercontent.com/122570012/221449425-646999e3-ff12-4742-8585-926a70c01cff.png)
 
 
 
## Step 2 : Clone the fork 

Clone the fork using the command `git clone` , since we have already generating SSH Keys for GitHub, I can use the SSH link to do this. 

  Copy the link first, and type `git clone`, and then right click would paste the link into terminal. 
  
  The command line runned should be `git clone git@github.com:heziq/lab7.git ` 
  
  Below is the screenshot of successful clone. 
  
  ![image](https://user-images.githubusercontent.com/122570012/221450427-42a3d844-c3f6-4f16-a8d2-4313f1e9e0f0.png)


## Step 3 : Run the tests and demonstrate the failure 

First using command `ls` and `cd lab7` to check and go to the right directory. 

  ![image](https://user-images.githubusercontent.com/122570012/221450575-ae7933fb-37de-4c27-b981-2e50f2695f10.png)

  Then using command line to compile and run the test. 

  Key pressed : `<up><up><up>...<up><enter>` , `<up><up><up>...<up><enter>` 
  
  Note: "..." above dose not mean type "...", but meanning that continue to use up arrow until find the command line I need. Because during lab I have used these commands with logged in account of ourselve, so I can use up arrows to search for the commands instead of typing this long commands letter by letter. 
  
  In this process, I first called `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` and then called `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests` 
  
  The test should fail as predicted, the results is shown in the below screenshot: 
  
  ![image](https://user-images.githubusercontent.com/122570012/221451147-f1d10361-6b9c-41ec-80f5-ee572459532b.png)

## Step 4 : Edit code to fix the failing test 

Now edit the code file to fix the failing test. 

Using command `nano` to open the file, using up and down arrows to locate the error, and fix the error in to correct form. 

Key pressed : `nano L<tab>.java` 

The terminal would now show us the .java file: 

![image](https://user-images.githubusercontent.com/122570012/221459093-0807c524-3be5-48e9-b762-41bd9ba45656.png

After this command, file "ListExamples.java" would be opened. "tab" would automatically fill possible worlds for us. Then read the code, use arrow keys to locate and edit the file, the changes should be maded is shown below: change the "index1" to "index2" 

before : 
![image](https://user-images.githubusercontent.com/122570012/221452237-1f18b976-8b27-4097-846a-d8e3da885a97.png)

after: 
![image](https://user-images.githubusercontent.com/122570012/221452252-00bb56aa-0946-47d4-82fa-e98ee5efc808.png)

After editting, press `ctrl+X` to exit, type `Y` when it asking for saving changes, then press "enter" key to exit. 

## Step 5 : Run the test and show success 

Now, re-run the code. 

  Key pressed : `<up><up><up><up><enter>` , `<up><up><up><up><enter>` 
  
  The command `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` is 4 up in the search history, so use 4 up arrow keys to use it, same for the command `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests` 
  
  The successful runing is shown in the screenshot below: 
  
  ![image](https://user-images.githubusercontent.com/122570012/221458883-91fb28b6-fe8d-4aee-9466-2ce4b376ed72.png)

## Step 6 : Commit and push the resulting change to Github account 

The last step is to commit and and push the resulting change to Github account. 

First type and use the command `git status` to check the current state of resporitory: 

![image](https://user-images.githubusercontent.com/122570012/221460158-df9c15ac-bb8a-415f-a2ee-ab1d6ff0948a.png)

Then, use `git add .` to stage all changes, and then use `git status` to check: 

![image](https://user-images.githubusercontent.com/122570012/221460280-3805c956-9942-4a36-9703-760e81cd45c3.png)

Now the changes is ready to be commited. 

Using `git commit -m "changed" ` and `git push` to finish the commit and push : 

![image](https://user-images.githubusercontent.com/122570012/221460376-60c081fd-5bdf-49e8-b4e7-e86676fecf56.png)


At this point, all works are done and changes are safely saved. 



