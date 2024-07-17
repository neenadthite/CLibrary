In order to create a library file of the functions and link it to your executable C program, please follow the followin steps. 


Step1: Compile and create output of the library source code file
$ gcc -c librarysource.c -o output_librarysource.o
ex. $ gcc -c exp_trk.c -o exptrk.o


Step2: Create library from the output source code file
$ ar rcs libraryname.a output_librarysource.o
ex. $ ar rcs libexptrk.a exptrk.o

This will create a static library

Step3: Compile the application main code using the library file and generate and executable
$ gcc mainfile.c -L. -llibraryname -o outputapplication
ex. $ gcc application.c -L. -lexptrk -o expensetracker

