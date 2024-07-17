In order to create a library file of the functions and link it to your executable C program, please follow the following steps. <br>


Step1: Compile and create output of the library source code file<br>
$ gcc -c librarysource.c -o output_librarysource.o <br>
ex. $ gcc -c exp_trk.c -o exptrk.o


Step2: Create library from the output source code file<br>
$ ar rcs libraryname.a output_librarysource.o<br>
ex. $ ar rcs libexptrk.a exptrk.o<br>

This will create a static library<br>

Step3: Compile the application main code using the library file and generate and executable<br>
$ gcc mainfile.c -L. -llibraryname -o outputapplication<br>
ex. $ gcc application.c -L. -lexptrk -o expensetracker
<br>
