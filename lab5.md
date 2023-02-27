# Lab 5 Report


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
      
      Source: [grep-command](https://www.digitalocean.com/community/tutorials/grep-command-in-linux-unix)
      
2. `-n` option 

    `-n` option with `grep` help us to find where the specific words occur, i.e. show the line number of that word.  
      
      For example now we want to know which line does "wonders of California" occur in the file, we can use:
      
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
      144:The oldest part of San Diego is situated 3 miles (4.8 km) north of downtown in the area known as Old Town (bounded by Juan, Congress, Twiggs, and Wallace streets). Here...or eat at one of the many restaurants.
      ``
      
      Source: [nine-ways-to-use-grep](https://www.comptia.org/blog/nine-ways-to-use-grep-to-filter-results-linux)

3. `-h` option

    `-h` option would suppress the display of filenames in the output. 
  
    Take previous example, searching for "wonders of California" in written_2 directory: 
  
    ``
    $ grep -r -h "wonders of California" written_2
    ``
  
    The ouput would be :
  
    ``
    Of all the wonders of California, the high desert is perhaps the greatest surprise. The desert is no monotonous expanse of sand dunes, but a beautiful... creating unforgettable views. 
    `` 
  
    Compare with the result we get before, this `-h` would not show us which file the words are at, but only the content. 
  
    Same for "colonization of California ": 
  
    ``
    $ grep -r -h "colonization of California" written_2
    `` 
  
    The output : 
    ``
  The oldest part of San Diego is situated 3 miles (4.8 km) north of downtown in the area known as Old Town (bounded by Juan, Congress, Twiggs, and Wallace streets). Here... or eat at one of the many restaurants.
    ``
  
    Source: [grep-examples](https://linuxhandbook.com/grep-command-examples/)
    
4. `-v` option 

    `-v` option is used to select all lines that does not match the pattern. 
    
    For example, before, we want to find all txt file in Written_2, But now if we want to know all other paths in this file, we could use `-v` option. 
    
    ``
    $ find written_2 > find.result.txt
    $ grep -v "txt" find.result.txt 
    ``
    
    This would give us the output that list all paths with only sub directories : 
    
    ``
    written_2
    written_2/non-fiction
    written_2/non-fiction/OUP
    written_2/non-fiction/OUP/Abernathy
    written_2/non-fiction/OUP/Berk
    written_2/non-fiction/OUP/Castro
    written_2/non-fiction/OUP/Fletcher
    written_2/non-fiction/OUP/Kauffman
    written_2/non-fiction/OUP/Rybczynski
    written_2/travel_guides
    written_2/travel_guides/berlitz1
    written_2/travel_guides/berlitz2
    ``
    
    Another example of using `-v` option would be. What if we do not what directorys in non-fiction, then we can use the below command line: 
    
    ``
    $ grep -v "txt" find_reslut.txt > grepvv.txt
    $ grep -v "non-fiction" grepvv.txt      
    `` 
    
    And we will get: 
    
    ``
    written_2
    written_2/travel_guides
    written_2/travel_guides/berlitz1
    written_2/travel_guides/berlitz2
    `` 
    
    Source: [grep-command](https://www.geeksforgeeks.org/grep-command-in-unixlinux/)

