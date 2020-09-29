# struct
* default access modifier is public....
* backwards compatible with C language
* Objects are blueprints for objects which help with dry code
* in addition to holding values they also have functionality with member functions or methods
* Allows easy ways of passing member variables, and member functions to other classes through inheritance
* Allows ability to work on each piece of code individually


<strong>explicit parameters:</strong> hidden values n parameters that aren't required
<strong>implicit parameters:</strong> values passed in parameters that required by the linter or it will not allow the program to continue

# different access modifiers
public/private/protected

## public
* can be accessed externally through calls of the object instance and inherited class

## private
* can only be accessed by an internal member function, and not by any inherited classes

## protected
* requires a member function to access them, and can be accessed by their derived classes member functions as well

## destructor
* handles your dynamic array easily so it can automatically destroy your dynamic memory member variables

# Class inheritance
* defaults to private access modifier
* Derived classes only have access to public member variables either by dot notation, member function, or pointer, and protected member variables and functions
* there is also struct inheritance as well

# Polymorphism and the virtual keyword

* abstract classes are just classes with pure virtual member functions in them
* regular virtual functions have the option to be over written
* Whenever using polymorphism you should always use a virtual destructor in the case of you having dynamically allocated variables. Same goes with pure virtual functions as well....

## pure virtual function
```c++
class Human {
    public:
        virtual void attack () override
        {
            std::cout << "gab!" << std::endl;
        }

};

class Ninga: public Human {
    public:
        void attack () override
        {
            std::cout << "Spinning jump kick to the face" << std::endl;
        }
};

class Boxer: public Human {};
```

## pure virtual function
* pure virtual functions must be over written in derived classes
* requires each individual to have their own new block of code.....

```c++
class Human {
    public:
        virtual void attack () = 0;

};

class Ninga: public Human {
    public:
        void attack () {
            std::cout << "Spinning jump kick to the face" << std::endl;
        }
};

class Boxer: public Human {
    public:
        void attack () {
                std::cout << "Spinning jump kick to the face" << std::endl;
        }
};
```
<br/>

## constructors and Delegation

# Class Inheritance

## Association, Aggregation, and Composition

## Inheritance

## Circular Inclusion and Forward Declaration
