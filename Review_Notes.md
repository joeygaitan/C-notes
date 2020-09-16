# Type Punning
* Having two pointers for the same data but with their own unique data types...

# Float constants
* sometimes the compiler will declare 0.0 as a double, so adding 0.0f will convert them at compile time....


# reference limitations
* you can't set references to nullptr
* you cant set value to another pointer

# function prototype
* c++ runs synchronously meaning from the first line to the bottom. This means that you need to set the function prototype above where you are calling it. Which looks like void functionName (string sam, int bill);


# stdin and stdout
* stdin: it is standard input. given to you by the program cin, getline
* stdout: it is standard output. Given by your computer. cout.

# run time vs compile time
* arrays size must be defined at compile time not run time.
* constexpr

# Scope Resolution Operator

uses of operator
* if a variable has the same variable as a global variable then use the sro.
* to define a function outside of a class. Tacking on a method of a class
* To access a classes static member
* In case of multiple inheritance
* for namespace
* refer to a class inside of another class
* define class member functions outside of class's brackets 


"https://www.geeksforgeeks.org/scope-resolution-operator-in-c/"

* ::

# header guards

* prevent a header from being included more than once (avoid declaring duplicate symbols)
```c++
ifndef HEADERNAME_H
#define HEADERNAME_H

//does the same as above.
#pragma once
```

 

# type byte amounts

int = 4 bytes
char = 1 byte

header files are allow you to import other files throughout your folder.

This could have duplicates which is sad

ifndef _log_H

* include directories is how you pass files around

* <iostream> c++ has no .h after because that is how it differentiates from c. When using include people use c in it.  
you can add a second variable in the for loop such as for (int i = 0, k = 0; i < somevalue; i++, k=0) this first initializes a variable k as a int, and then at start it resets it to the value of your choice or increments

## typedef
* this allows you to make a variable alias.
typedef unsigned long int sam;
sam number = 3;

## c++ programing words
* sentinel controlled program: is where you put the user in a loop and give them a way to exit the program.
* unary scope resolution operator ::variable_name to access global variable
* function overloading: you can build more than one function with the same number that take in different types of types.
* aggregated aggression 

## random number generation

```c++
#include <cstdlib>
#include <ctime>

int main()
{
	srand(time(0)); // calculates the seconds from 1970 every second the seconds are changing.
	srand(10); pass in random number
	
	cout << rand(); // prints out random number
	rand()%6 // 0-5
}


cout << "Please pick your base of a pyramid?" << endl;
cin >> userinput;
char star = '*';
char space = ' ';

for (int i = 1, k = 0; i < userinput; i++, k=0) {
											
	for (int j = 1; j < userinput - i; j++) {
		cout << space;
	};
	
	while (k != 2 * i - 1) {
		cout << star;
		k++;
	};
		cout << endl;
}
};
```

for loops
1st step declare variable to iterate, condition to loop on, and iteration

# Pointers

raw pointers: 
* memory is the most important thing for computers
* All the instructions get loaded into memory or ram
* pointers are an integer a number that stores a memory address
* linear 1 dimension line. Every house that has an address has 1 byte of data.
* read and write from memory. A pointer is the address that tells us where that byte is
* reading and writing from and too memory.

A pointer is just an integer that has a memory address. types are meaningless they are all actually pointers

### a void pointer: completely type less
void* ptr = 0; a memory address that is invalid. We can not read from or write from an invalid memory address

### how to find out what the memory address of a variable is
int var = 8;
void* ptr = &var; ptr now will be equal to the memory address of that var variable

### dereferencing the data from the pointer
*ptr; you must change the pointer type. The type decides on the bytes the variable has.

basically writing to that byte at the memory address and changing it when dereferencing

asking for 8 bytes of memory returning a pointer to that point in memory
char* buffer = new Char[8];
first parameter is pointer to beginning block of memory, take in a value, and a size or how many bytes should it fill.
memset(buffer, 0, 8);

### a pointer is a variable are also stored in memory an integer with a memory address of another variable as its value. you can point to a pointer.

# References

a reference an existing variable. They have to reference an existing variable
a = 5;
int& ref / int& = part of the type it's a reference 
This is an Alias = int& ref = a;
ref = 2;
log(a) == 2

* references point to the memory allow you to easily modify the data while a pointer stores the memory address
* references have to be assigned initially
* you can have a reference for another reference

# Classes OOP

C++ header file "https://www.youtube.com/watch?v=QG5s42I_75c"

* c doesn't support classes, but it supports structs
* classes are object blueprints with private and public properties, and methods to allow you to modify the properties or other things
* C++ parent class is called a base class, and child class is called derived class
* you pass parameters inside of your constructor. This allows you to have a class that can be auto configured
* the children get deleted first by the destructor

## destructor

* handle how class is destroyed
* designated like a constructor with a ~ in front of name
* Never have parameters
* make destructors noexcept
* Define a destructor if a class needs an explicit action at object destruction
* All resources acquired by a class must be released by the class's destructor.
* a base class with a virtual function needs a virtual destructor.


class notation

```c++
class Player
{
				public:
				int x,y;
				int speed;

				void Move(xa,ya){
						x += xa * speed;
						y += ya * speed;
				}
}
```

Player player; instance of player object
player.speed = 5;
player.Move(1,3);

## class inheritance



```c++
#include <iostream>


class checkInput {
	public:
		char input[6] = "hello";
};

class Log: public checkInput
{
	public:
		const int LogLevelError = 0;
		const int LogLevelWarning = 1;
		const int LogLevelInfo = 2;
	private:
		int m_LogLevel = LogLevelInfo;
	public:
		void SetLevel(int level) {
				m_LogLevel = level;
		};
		void Error(const char* message) {
			if (m_LogLevel >= LogLevelError)
				std::cout << "[error]: " << message << std::endl;
		}
		void Warn(const char* message) {
			if (m_LogLevel >= LogLevelWarning)
				std::cout << "[warning]: " << message << std::endl;
		};
		void Info(const char* message) {
			if (m_LogLevel >= LogLevelInfo)
				std::cout << "[Info]: " << message << std::endl;
		}
};

int main() {
	Log log;
	log.SetLevel(log.LogLevelError);
	log.Warn("friend");
	log.Warn("hello");
	log.Error("broken boy");
	std::cout << log.input;
}
```

# difference between structure and Class

* there is no difference
* a class is private by default
* a struct is public by default
* C doesn't have classes. Structs are for backwards compatibility
* never use inheritance with a struct

# log class

```c++
class Log
	{
		public:
			const int LogLevelError = 0;
			const int LogLevelWarning = 1;
			const int LogLevelInfo = 2;
		private:
			int m_LogLevel = LogLevelInfo;
		public:
			void SetLevel(int level) {
				m_LogLevel = level;
			};
			void Error(const char* message) {
				if (m_LogLevel >= LogLevelError)
						cout << "[error]: " << message << endl;
			}
			void Warn(const char* message) {
				if (m_LogLevel >= LogLevelWarning)
					cout << "[warning]: " << message << endl;
			};
			void Info(const char* message)																																																
				if (m_LogLevel >= LogLevelInfo)																														
					cout << "[Info]: " << message << endl;
			}
};																																																																			

int main() {
	Log log;
	// log.SetLevel(log.LogLevelError);
	log.Warn("friend");
	log.Warn("hello");
}
```

# polymorphism

* when a single variable, reference or pointer connects to an instance of inheritance

# Static outside of a class and struct
* outside of a class or struct = only going to be visible to that c++ file it is inside of. You can declare it a header file to share between two of them.

# static inside of class and struct
* any property with a static variable it becomes global throughout all instances of the class.
* this will lead them to point to the same address.
* this is useful for having a global variable that needs to be shared across all class instances.
* static methods can't access non static variables or properties
* a static method doesn't have a class instance always get an instance of current class as the parameters. It doesn't know which property you are referencing to. It goes to the class instead of the 

# arrays

# dynamic memory
* dynamic memory is accessed through pointers
* most 

# new keyword
* finds a block of memory that is a big enough for our needs and then gives us a pointer to that block of memory.
* allocate memory. determines necessary size of memory. Needs to find an address where you have the bytes in a row. Once it does that it returns a pointer with a memory address
* free-list maintains addresses with bytes. (Slow)
* must use delete after the code is finished at the bottom.
* from the heap

```c++
	int* a = new int;
	int* b = new int[50]; 
	int* c = new Entity[20]; // object instance

	// delete after or data leak will happen in your code.
	delete a;
	delete[] b;
	delete[] c;
```

# delete keyword
* de-allocate allocated memory
* specify memory address with the pointer
* memory leak (:/)

# dynamic arrays
* 

```c++
int* array = new int[]
```

```c++
	int* pointer = NULL;
	std::cout << "how many items are you going to enter?" << std::endl;
	int input;
	std::cin >> input;

	pointer = new int[input];

	int user_input;

	for (int i = 0; i < input; i++){
		std::cout << "enter the item " << i+1 << std::endl;
		std::cin >> user_input;
		*(pointer + i) = temp; 
	} 

	delete[] input;
```

```c++

```

