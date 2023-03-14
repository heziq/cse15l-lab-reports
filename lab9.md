## Lab Report 5

In lab report 3, I did exploration on command `grep`, so in this lab report, I'll talk about the `find` command. 

`find` command is a useful command that allows people to search for files and directories in various ways. 
Here are some interesting example of different uses of `grep` command. 

1. Find a single file by approximate name 
  
  If we are not sure about what the exact name of the file, but only remember the key words of the file name
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
  
  If we are not sure about whether the letters in filename is captalized or not
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
  
  
  
  
  
