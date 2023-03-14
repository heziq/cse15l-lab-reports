## Lab Report 5

In lab report 3, I did exploration on command `grep`, so in this lab report, I'll talk about the `find` command. 

`find` command is a useful command that allows people to search for files and directories in various ways. 
Here are some interesting example of different uses of `grep` command. 

1. Find a single file by approximate name 
  
  If we are not sure about what the exact name of the file, but only remember the key words of the file name.
  We can use `*  *`  to do a partial search like this:

  ``
  $ find non-fiction/OUP -name "*ch1*txt"
  ``
  
  The result would be as following, where all files' name contaning "ch1" would be shown, instead of just ch1.txt
  
  ``
  non-fiction/OUP/Abernathy/ch1.txt
  non-fiction/OUP/Abernathy/ch14.txt
  non-fiction/OUP/Abernathy/ch15.txt
  non-fiction/OUP/Berk/ch1.txt
  non-fiction/OUP/Fletcher/ch1.txt
  non-fiction/OUP/Fletcher/ch10.txt
  non-fiction/OUP/Kauffman/ch1.txt
  non-fiction/OUP/Kauffman/ch10.txt
  non-fiction/OUP/Rybczynski/ch1.txt
  ``
  
  If we are not sure about whether the letters in filename is captalized or not,
  we can use `-iname` to do a case-insensitive search: 
  
  ``
  $ find non-fiction/OUP -iname "*ch4*txt"
  ``
  
  The result would show the filename contain both "ch4" and "CH4" :
  
  ``
  non-fiction/OUP/Berk/CH4.txt
  non-fiction/OUP/Kauffman/ch4.txt
  ``
  
  These two appoarches is useful when we are not hundred percent sure about the exact filename. 
  
  Source: [10 ways to use find command](https://www.redhat.com/sysadmin/linux-find-command)
  

2. Limiting list result 

  Sometimes, there are a lot of files that match our requirments, but we only need several examples.
  At this time, we can use `-head` option follow by the number of files we want. 
  
  An example of running this command would be : 
  
  If we just run command 
  
  ``
  $ find non-fiction/OUP -name "txt"
  `` 
  
  The output would be 
  
  ``
  non-fiction/OUP/Abernathy/ch1.txt
  non-fiction/OUP/Abernathy/ch14.txt
  non-fiction/OUP/Abernathy/ch15.txt
  ...
  non-fiction/OUP/Rybczynski/ch3.txt
  // list all the txt files, this is too long so I use "..." to represent middle part. 
  `` 
  
  But if we only want two txt files, we could use the following command to do so : 
  
  ``
  $ find non-fiction/OUP -name "*.txt" | head -2
  ``
  
  The output would be:
  
  ``
  non-fiction/OUP/Abernathy/ch1.txt
  non-fiction/OUP/Abernathy/ch14.txt
  ``
  
  Only first two txt files was listed. 
  
  This `-head` option is useful when we only want a specific number of certain kinds of files instead of all files of this kind. 
  
  Source: [10 ways to use find command](https://www.redhat.com/sysadmin/linux-find-command)
  
  
3. Find files based on their type 

   If we only want to search for files, we can use `-f` option:
   
   For example: 
   
   ``
   $ find -type f -name "*ch1*"
   ``
   
   This would list all files with ch1 in its name. 
   
   ``
   ./non-fiction/OUP/Abernathy/ch1.txt
  ./non-fiction/OUP/Abernathy/ch14.txt
  ./non-fiction/OUP/Abernathy/ch15.txt
  ...
  ./non-fiction/OUP/Rybczynski/ch1.txt
  //too long so use ... to represent middle part 
  ``
  
  But if we run :
  
  ``
  $ find -type d -name "*ch1*"
  ``
  
  Nothing would be shown since there no directories named with "ch1"
  
  `-type` is useful is we want to search for a specific type i.e. files or directorys. 
  
   
  
  
  
  
