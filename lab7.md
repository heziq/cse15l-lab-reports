# Lab Report 4

## Step 1 : Log into ieng6 account 

The first step to after the timer start is to log in to the account. 

  Key pressed: `<up><enter>`
  
  The last time the command `ssh cs15lwi23asx@ieng6.ucsd.edu` is just one line above in search history, so accessed it and ran it in the same way. 
  
  Below is the screenshot of successful login. 

 ![image](https://user-images.githubusercontent.com/122570012/221449425-646999e3-ff12-4742-8585-926a70c01cff.png)
 
 
 
## Step 2 : Clone the fork 

Clone the fork using the command `git clone` , since we have already generating SSH Keys for GitHub, we can use the SSH link to do this. 

  Copy the link first, and type `git clone`, and then right click would paste the link into terminal. 
  
  The command line runned should be `git clone git@github.com:heziq/lab7.git ` 
  
  Below is the screenshot of successful clone. 
  
  ![image](https://user-images.githubusercontent.com/122570012/221450427-42a3d844-c3f6-4f16-a8d2-4313f1e9e0f0.png)


## Step 3 : Run the tests and demonstrate the failure 

First using command `ls` and `cd lab7` to check and go to the right directory. 

  ![image](https://user-images.githubusercontent.com/122570012/221450575-ae7933fb-37de-4c27-b981-2e50f2695f10.png)

  Then using command line to compile and run the test. 

  Key pressed : `<up><up><up>...<up><enter>` , `<up><up><up>...<up><enter>` 
  
  Note: "..." above dose not mean type "...", but meanning that continue to use up arrow until find the command line we need. Because during lab we have used these commands with logged in account of ourselve, so we can use up arrows to search for the commands instead of typing this long commands letter by letter. 
  
  In this process, we first called `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` and then called `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests` 
  
  The test should fail as predicted, the results is shown in the below screenshot: 
  
  ![image](https://user-images.githubusercontent.com/122570012/221451147-f1d10361-6b9c-41ec-80f5-ee572459532b.png)

## Step 3 : Edit code to fix the failing test 

Now we should edit the code file to fix the failing test. 

Using command `nano` to open the file, using up and down arrows to locate the error, and fix the error in to correct form. 

Key pressed : `nano L<tab>.java` 



before : 
![image](https://user-images.githubusercontent.com/122570012/221452237-1f18b976-8b27-4097-846a-d8e3da885a97.png)

after: 
![image](https://user-images.githubusercontent.com/122570012/221452252-00bb56aa-0946-47d4-82fa-e98ee5efc808.png)


ctrl x 
 Y 
 <enter>
  

  
  






Run the tests, demonstrating that they fail
Edit the code file to fix the failing test
Run the tests, demonstrating that they now succeed
Commit and push the resulting change to your Github account





