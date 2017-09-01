# DLL-creation-for-widows
How to create DLL for windows

DLL stands for Dynamic Link Library. It is a kind of library which linked at run time. It is usefull when you want to have so many application which needs some function which is common for all the application. Here comes the concept of DLL which provide the facility to link with several application.

Here We will see how to create DLL with two methods :- 1. Mannual(Using command Prompt) Method
                                                       2. Using Visual Studio

DLL creation using Command Prompt

To create DLL application one must have function define in cpp file where it is declared in header file.
Step 1. Write the function declaration in header file as given below.

// File: SampleDLL.h
//
#ifndef INDLL_H
#define INDLL_H

   #ifdef EXPORTING_DLL
      extern __declspec(dllexport) void HelloWorld() ;
   #else
      extern __declspec(dllimport) void HelloWorld() ;
   #endif

#endif

step 2. Define this function in cpp file as given below

// SampleDLL.cpp

#include <iostream>
#define EXPORTING_DLL
#include "sampleDLL.h"
using namespace std;

void HelloWorld()
{
	cout<<"Hello World ! Welcome to the world of DLL!!";
}

step 3. Now create your application which calls this function.

// SampleApp.cpp 

#include "sampleDLL.h"
#include <conio.h>
int main()
{ 	
   HelloWorld();
   getch();
   return 0;
}

Now your program is ready to build.

Steps to build/compile the Application.

step 1. Open command prompt.
step 2. 

