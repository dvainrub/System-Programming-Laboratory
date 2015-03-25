### **Task 2: The line_splitter program**
***
In this task we will write a modified version of the Unix split program

Punctuation marks are only the following:
* period .
* comma ,
* semicolon ;
* colon :

***

**NAME**

line_splitter - split input into lines by a given delimiter type.

**SYNOPSIS**

line_splitter [OPTION]… [FILE1] [FILE2] … [FILE10]

**DESCRIPTION**

* line_splitter receives a string from the standard input and prints it into the standard output. 
* If option '-p' is given, line_splitter will splits the input into lines after every occurrence of a punctuation mark. 
* If option '-d' is given, line_splitter will splits the input into lines after every occurrence of a digit: from 0 to 9.
* If no options are present, it is assumed to split after each punctuation mark.
* If '-o' is not provided, then the program prints to the standard output. 
* If [FILE1]…[FILE10] is provided, then line_splitter reads its input from the given file[s], instead of the standard input. 

**OPTIONS**

* `-p` Split after each punctuation mark.
* `-d` Split after each digit.
* `-o FILE`  Output file. Write the output to a file, instead of the standard output. You may write to one file only.

**EXAMPLES**

    #> echo A 1000 nations, of the Persian empire, will descend upon you! > i3
    #> echo Our arrows, > i5
    #> echo will blot out the sun. Then> i7
    #> line_splitter -o outFileResult i3 i5 i7 -d -p 
    
    #> more outFileResult
    A 1
    0
    0
    0
     nations,
     of the Persian empire,
     will descend upon you! 
    Our arrows,
     
    will blot out the sun.
     Then


***

**Mandatory requirements**

* You must use a switch to check if a char is a punctuation delimiter
* You must read the input character by character, there is no need to store the data read at all.
* stdin and stdout are FILE* constants than can be used with fgetc and fputc.
* Make sure you know how to recognize end of file ( EOF ).
* Control-D causes the Unix terminal driver to signal the EOF condition to the process running in this terminal foreground, using this key combination will cause fgetc to return EOF and in response your program should terminate itself.
* To read your program parameters: first set default values to the variables holding the program configuration and then scan through argv to update those values.
* You must use an array to store the input file descriptors.
* The files are up to 10. That means from 0 to 10 possible input files can be given as parameter.
* The order of parameters is arbitrary, and all options can be present, and all options can be not present.
