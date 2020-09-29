

## programming paradigms

### waterfall development
* plan the product before hand. Then build it out in one go

### agile development 
* build your idea in sprints or short development cycles with constant user feed back to help shape the product to fit the user

## Test Driven Development == TDD

### Write tests before writing code.....
1. Write one or more related tests.
2. Write code that passes the test(s).
3. Run all tests to verify that the code works correctly

#### Pros
* Possibly faster development by clarifying what you are trying to accomplish
* Fewer bugs in your code
* Cleaner code
* Greater confidence in your own code

## Game bug testing
1. Software is never done
2. No software is bug free
3. if it works then you aren't done (probably doesn't work)

## game development
* Design
* Develope
* Polish

## First Steps
* define one aspect of your software's requirements well enough to write a unit test. 

#### unit test
* a specific kind of test that can verify whether a single unit of the program has been completed correctly. A "single unit" of a program is typically a function......

#### unit test implementations
* boolean expression check. it the expression is true then the test was passed otherwise you know where the bug is and fix it. Then run the test again....

## using pre processes and a if conditional to display debug mode

```c++
#define UNIT_TESTS 1 // turn to 0 to avoid unit tests


#if (UNIT_TESTS)
RunTests();
#else
RunProgram();
#endif
```

## objects require instances to check functionality
* a single member function of a class might require you to allocate, call the function, and then check the objects state to see that it's correct.
* it requires first to make an object instance, then to run the member function and check if they pass your unit tests after.

### assert library
* at runtime...
* takes an expression if true it moves along, if false it will through an error stopping your code. Making you make that expression true systematically
```c++
#include <assert.h>

int value = 5;

assert(value > 4);
```

### when to use assert
* if the user has access to the assert don't use an assert and use a unit test
* when the values are controlled and the user has no access to the values in the expression for the assert breaking your code.

### closing statement

* write a test that catches it so it won't happen again....





