# Casting
* Converting data types of variables into another data type

# different types of casts in C++
* static_cast
* reinterpret_cast
* dynamic_cast
* const_cast

## type punning
* Converting complex data types into something else.
* converting struct and classes member variables into an array.
* treating a memory as a different type than it actually is. Get that type as pointer and then cast it to different pointer type. Then you can dereference it.

### Text Book definition
* A form of pointer aliasing where two pointers refer to the same location in memory but represent that location as different types. The compiler will treat both "puns" as unrelated pointers. Type punning has the potential to cause dependency problems for any data accessed through both pointers

* pros converting data into less complex forms. Such as turning a struct into an array letting it be easily sent over.

## implicit conversion
- C++ knows how convert between two data types with no data loss
```c++
    int a = 5;
    double value = a;

    double value = 5.25;
    int a = value;
```

## explicit conversion
- Telling c++ to convert types


### C styled casts
```c++
    double value = 5.25;
    double a = (int)(value + 5.25);
```

### C++ styled casts (static cast)
```c++
    double value = 5.25;
    double a = static_cast<int>(value);
```



