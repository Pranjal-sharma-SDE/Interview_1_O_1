# Python Interview Questions
---
## Q-1 What is the difference between == and is operator in Python?
Ans- Both the == and is operators in Python are used for comparison, but they function differently.

The == operator checks for value equality.
The is operator, on the other hand, validates object identity,
In Python, every object is unique, identifiable by its memory address. The is operator uses this memory address to check if two objects are the same, indicating they both point to the exact same instance in memory.

is: Compares the memory address or identity of two objects.
==: Compares the content or value of two objects.
While is is primarily used for None checks, it’s generally advisable to use == for most other comparisons.

Tips for Using Operators
==: Use for equality comparisons, like when comparing numeric or string values.
is: Use for comparing membership or when dealing with singletons like None.
## Q-2 How do you create a dictionary in Python?
Ans- Python dictionaries are versatile data structures, offering key-based access for rapid lookups. Let’s explore various data within dictionaries and techniques to create and manipulate them.

Key Concepts
A dictionary in Python contains a collection of key:value pairs.
Keys must be unique and are typically immutable, such as strings, numbers, or tuples.
Values can be of any type, and they can be duplicated.
Creating a Dictionary
You can use several methods to create a dictionary:

Literal Definition: Define key-value pairs within curly braces { }.

From Key-Value Pairs: Use the dict() constructor or the {key: value} shorthand.

Using the dict() Constructor: This can accept another dictionary, a sequence of key-value pairs, or named arguments.

Comprehensions: This is a concise way to create dictionaries using a single line of code.

zip() Function: This creates a dictionary by zipping two lists, where the first list corresponds to the keys, and the second to the values.

## Q-3 What is the difference between list and tuple?
Ans- Lists and Tuples in Python share many similarities, such as being sequences and supporting indexing.

However, these data structures differ in key ways:

Key Distinctions
**Mutability**: Lists are mutable, allowing you to add, remove, or modify elements after creation. Tuples, once created, are immutable.

**Performance**: Lists are generally slower than tuples, most apparent in tasks like iteration and function calls.

**Syntax**: Lists are defined with square brackets [], whereas tuples use parentheses ().

When to Use Each
Lists are ideal for collections that may change in size and content. They are the preferred choice for storing data elements.

Tuples, due to their immutability and enhanced performance, are a good choice for representing fixed sets of related data.

## Q-4 How to handle the exception in python?
Exception handling is a fundamental aspect of Python, and it safeguards your code against unexpected errors or conditions. Key components of exception handling in Python include:

Components
**Try**: The section of code where exceptions might occur is placed within a try block.

**Except**: Any possible exceptions that are raised by the try block are caught and handled in the except block.

**Finally**: This block ensures a piece of code always executes, regardless of whether an exception occurred. It’s commonly used for cleanup operations, such as closing files or database connections.

**Else**: This block runs only when no exception catch over except bloks.

**Raise** : This keyword helps in raiseing the exeption manually. 
Structure for above-> 
```
try:
    print("Inside try")
    raise ValueError("Custom error")
except ValueError:
    print("Inside except")
else:
    print("Inside else")
finally:
    print("Inside finally")
```

## Q-5 Which blocks will execute?
```
try:
    x = 10 / 2
    print("Try block executed")
except ZeroDivisionError:
    print("Exception caught")
else:
    print("Else block executed")
finally:
    print("Finally block executed")
```
Ans - 
Try block executed
Else block executed
Finally block executed

## Q-6 Which blocks will execute?
```
try:
    x = 10 / 0
    print("Try block executed")
except ZeroDivisionError:
    print("Zero division error caught")
else:
    print("Else block executed")
finally:
    print("Finally block executed")
```
Ans- 
Zero division error caught
Finally block executed

## Q-7 
```
try:
    print("Inside try")
    raise ValueError("Custom error")
except ValueError:
    print("Inside except")
else:
    print("Inside else")
finally:
    print("Inside finally")
```
Ans- Inside try → Custom error → Inside except → Final.

## Q-8 Explain the difference between a mutable and immutable object.
Ans- Let’s look at the difference between mutable and immutable objects.

Key Distinctions
**Mutable Objects**: Can be modified after creation.
**Immutable Objects**: Cannot be modified after creation.
Common Examples
**Mutable**: Lists, Sets, Dictionaries
**Immutable**: Tuples, Strings, Numbers
