In order to create a library file "libxyz.a" of the functions and link it to your executable C program, please follow the following steps. <br>

Create Header and Source files for the functions, where all the functions declaration should be in the header file and the definations should be in source file<br>
ex. library_creation$ cat exp_trk.h
#ifndef EXP_TRK
#define EXP_TRK

int startprogram();
int enterexpense();
int writerecordinfile(int, int, char*);
int display();
int findtime();
int fileinitialization();
int invalidinput();
#endif


Step1: Compile and create output of the library source code file<br>
$ gcc -c librarysource.c -o output_librarysource.o <br>
ex. $ gcc -c exp_trk.c -o exptrk.o


Step2: Create library from the output source code file<br>
$ ar rcs libraryname.a output_librarysource.o<br>
ex. $ ar rcs libexptrk.a exptrk.o<br>
This will create a static library by the name "libexptrk.a" <br>


Step3: Compile the application main code using the library file and generate and executable<br>
Make sure that you add the header file of the libray file in your application code.<br>
$ gcc mainfile.c -L. -llibraryname -o outputapplication<br>
ex. $ gcc application.c -L. -lexptrk -o expensetracker
<br>
