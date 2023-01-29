# Lab 1 Report

  This will be a tutorial first CSE 15L lab, meaningly about remote access to the ieng6 course specific account and run simple commands. 

## Step 1 - Installing VScode 

1. Go to the Visual Studio Cose websit [Visual Studio Website](https://code.visualstudio.com/), and download the suitable version of VScode for you computer.
  (you can see at the right side of the screen, there is a bottom shows which version you should download for your computer, you can just clicking downloading and then open it, when installing, you can keep all setting as default) 
  ![image](https://user-images.githubusercontent.com/122570012/215300595-7b3c3140-feb3-4a4b-9147-0a4e4895761b.png)
  

2. Once finish downloading and installing, open VS code, this should be the page you will see. 
  
      <img src="https://user-images.githubusercontent.com/122570012/215301108-eea292e0-6b36-4614-9098-b2dd7c844933.png" width=70% height=60%>


   
Now we are done with first step, let's move to next step. 


## Step 2 - Remotely Connecting 
1. Set up your CSE 15L course specific account. 

    a. Look up you account user name throw the link here: [Account look up](https://sdacs.ucsd.edu/~icc/index.php)
    
    b. Once logged in, follow the link below to reset your password for this course specific account : [tutorial](https://docs.google.com/document/d/1hs7CyQeh-MdUfM9uv99i8tqfneos6Y8bDU0uhn1wqho/edit)
    
    *(Please make sure to read through the guideline, it is very common to meet problems here)*. 
    
2. If you are using Windows, please install the git, which comes with some useful tools we will need.  
    
   [git for Windows](https://gitforwindows.org/)
   
   After installing, use this steps to set your default terminal on VS code. 
   
   [steps](https://gitforwindows.org/)
    
3. Now open a new terminal in the VS code, you do not need to create or open a file. On the top of the menu, select "terminal" then "new terminal". 

4. In you terminal enter the following command, notice that "zz" should be replaced with your own account. Remember you do not need type "$", that's just how we write commond. 

```
$ ssh cs15lwi23zz@ieng6.ucsd.edu
```

  If this is the first time that you are connecting to a server, you will probably get this message: 

```
⤇ ssh cs15lwi23zz@ieng6.ucsd.edu
The authenticity of host 'ieng6.ucsd.edu (128.54.70.227)' can't be established.
RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.
Are you sure you want to continue connecting (yes/no/[fingerprint])? 
```

  Type "yes" and "enter"

  Then you will be able to enter your passowrd at this time. Notice that the password would not shown on screen for security, just type "enter" when you finish your password.  
  
5. Once you successfully connected, you will see something like this: 

![logged-in](https://user-images.githubusercontent.com/122570012/212614101-baf01ce0-e291-4167-aef3-6b0ca4467e73.png)

  Now your terminal is connected to a computer in CSE basement, and any commands you will run on that computer. 
  
  
## Step 3 - Trying Some Commands

Let's try some command here, on both remote connecting and your own computer. Try command in different position and think about what you see. Here are some command you can try: 

- `pwd` : print working directory 
- `ls <path>` : list the files and folders in the given path 
- `cd <path>` : change directory, used to switch the current working directory to the given path 
- `cat <path1> <path2> `... Prints the contents of files given by the paths 

Also try these command too: 

- `ls -lat`
- `ls <directory>`
- `cat /home/linux/ieng6/cs15lwi23/public/hello.txt`
- `cp /home/linux/ieng6/cs15lwi23/public/hello.txt ~/`

Here are some examples of what you will see when you run the commands: 
![command-1](https://user-images.githubusercontent.com/122570012/212752910-de6c9e2b-6945-4f34-a195-0bcb2a817983.png)
![command-2](https://user-images.githubusercontent.com/122570012/212752920-19193b2f-20ea-458a-8732-22f7611343d1.png)


  
After finishing, you can log out the remote server, you can :
- Ctrl D
- Run the command `exit`
  
**Congratulations!** Now you are done with the remote server part of this lab. 
