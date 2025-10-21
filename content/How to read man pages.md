---
{"publish":true,"created":"2025-10-21T16:46:32.185+05:45","modified":"2025-10-21T19:15:50.971+05:45","cssclasses":""}
---


I was wondering how pipes in [[linux]]/[[unix]] actually work and i thought the best place to start was with `man pipe`. It took me 2 whole minutes to understand i was not reading something related to `pipe`  IPC but i was reading about Postfix delivery daemon.  
Another instance is when i wanted to see the formatters for `printf()` and i couldn't for love of god see how that worked because i was reading a General command `printf` 

So i don't know how to read man pages. So i looked into [What is sections in man pages in linux](https://unix.stackexchange.com/questions/610339/what-is-sections-in-man-pages-in-linux)
and then figured out.

In order to read `man` pages , you start with 

```
man man 
```

Here is the crucial piece of information
```
DESCRIPTION
     The man utility finds and displays online manual documentation pages.  If mansect is provided, man restricts the search to the specific section of the manual.

     The sections of the manual are:
           1.   General Commands Manual
           2.   System Calls Manual
           3.   Library Functions Manual
           4.   Kernel Interfaces Manual
           5.   File Formats Manual
           6.   Games Manual
           7.   Miscellaneous Information Manual
           8.   System Manager's Manual
           9.   Kernel Developer's Manual
```

You use 
```
man 3 printf // for library C functions
````

similarly you use

```
man 2 pipe
```

to learn about pipes.



