# Lab 5 Report

## `grep` command
  `grep` command line is used to search files for lines that contain specific expression or match some patterns. 
  Here are some interesting example of different uses of `grep` command. 
  
  1. `-w` option
  
      `-w` option with `grep` let us to search for context that match only exactly whole words. 
      Examples:
      
      ``
      $ grep -r -w -l "wonders of California" written_2
      ``
      
      This will give us the file that contains exactly this 3 words: 
      
      ``
      written_2/travel_guides/berlitz2/California-WhereToGo.txt
      ``
      
      However, if we miss spell two letter at the end : 
      
      ``
      $ grep -r -w -l "wonders of Califor" written_2
      ``
      
      There would be no output. 
      
      Note: `-r` and `-l` here means search through the directory recursively and list the matched file path. 
      
      Source: https://www.digitalocean.com/community/tutorials/grep-command-in-linux-unix

2. `-n` option 

    `-n` option with `grep` help us to find where the specific words occur, i.e. show the line number of that word.  
      
      For example now we want to know which line does "wonders of Carlifornia" occur in the file, we can use:
      
      ``
      $ grep -n "wonders of California" written_2/travel_guides/berlitz2/California-WhereToGo.txt
      ``
      
      The output would be : 
      
      ``
      166:Of all the wonders of California, the high desert is perhaps the greatest surprise. The desert is no monotonous expanse of sand dunes, but a beautiful......creating unforgettable views.
      `` 
      
      This tells us that the "wonders of California" occurs at line 166. 
      
      This article not only talks about the wonders of California, but also talks about some history of California, we can search for the words "colonization of California " in this article too : 
      
      ``
      $ grep -n "colonization of California" written_2/travel_guides/berlitz2/California-WhereToGo.txt
      ``
      
      The output would be : 
      
      ``
      144:The oldest part of San Diego is situated 3 miles (4.8 km) north of downtown in the area known as Old Town (bounded by Juan, Congress, Twiggs, and Wallace streets). Here, in 1769, the European colonization of California commenced...or eat at one of the many restaurants.
      ``
      
      Source: https://www.comptia.org/blog/nine-ways-to-use-grep-to-filter-results-linux

3. `-h` option

  `-h` option would suppress the display of filenames in the output. 
  
  Take previous example, searching for "wonders of California" in written_2 directory: 
  
  ``
  $ grep -r -h "wonders of California" written_2
  ``
  
  The ouput would be :
  
  ``
  Of all the wonders of California, the high desert is perhaps the greatest surprise. The desert is no monotonous expanse of sand dunes, but a beautiful... creating unforgettable views. 
  
  
  Source: https://linuxhandbook.com/grep-command-examples/
      
  
  2. `` option 
  3. `` option
  4. `` option 
  
