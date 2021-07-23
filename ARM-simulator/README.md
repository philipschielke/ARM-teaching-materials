# ARM simulator resources

## VisUAL2

This is an assembly level simulator for a subset of the ARM instruction set.  It's developed in F# and can be found here: https://github.com/tomcl/visual2.github.io

## VisUAL

This is an older version of this simulator written in Java.  It can be found here: https://salmanarif.bitbucket.io/visual/index.html

## VisUAL - modified

The jar file in this directory is a modified version of the simulator, primarily adding the multiply instructions.  Simply download the file and point Java at it.
You may need to go to your security settings to allow it to run.

The documentation for VisUAL can be found here:  https://salmanarif.bitbucket.io/visual/index.html
Please note, that this documentation is for the unmodified version of VisUAL.  I have made some extensions to the software as detailed in this document.  Please read thoroughly!

### List of Supported Instructions
In addition to what is listed on the website the following instructions are supported in the course version of VisUAL:

* Multiply, MUL, MUL{S}{cond} dest, op1, op2
* Multiply and Accumulate, MLA, 
* SMULL
* UMULL

### Directives

The DCD directive allows you to store words (32-bit) data into memory.  For example:

`stuff   DCD   13, 12`

Will store the numbers 13 and 12 into the memory address referred to be stuff as 32-bit (Word) values.  VisUAL also supports the DCB directive which stores bytes of data.  For example,

`stuff   DCB   13, 12`

Will store only two bytes of data, 16 bits total, one byte each for 13, and 12.  This version of VisUAL also allows you to enter strings as data for DCB.  For exampls:

`myString  DCB   "Hello"`

Will store the ASCII values of the characters 'H', 'e', 'l', 'l', 'o' as bytes into memory at the location referred to as myString.  Note that a trailing 0 is not added onto the end of the string.  DCB also supports characters as values.  For example:

`myString2 DCB 'H','i','!'`
is acceptable syntax.

### Memory map

You can also display individual bytes of memory as their ASCII characaters.
