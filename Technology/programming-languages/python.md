# Python

- [Overview](#overview)
- [Operators](#operators)
- [Data Types](#data-types)
- [Conditionals](#conditionals)
- [Loops](#loops)
- [Functions](#functions)
- [Exceptions](#exceptions)
- [Object Oriented](#object-oriented)

## Overview

Python (named after Monty Python) is a high-level, interpreted programming language. It is designed to emphasise readability with indentation highlighting the scope of code lines.

## Operators

### Arithmetic

`+, -, *, /, %`

### Comparison

`>, <, ==, !=, >=, <=`

### Logical

`and` - returns true of both operands are true

`or` - true if one of the operands is true

`not` - true if operand is false

### Bitwise

### Assignment

`=, +=, -=, *=, /=, %=, **=`

### Identity

`is` - true if operands identical

`is not` - true if not identical

### Membership

`in` - true if value found in sequence

`not in` - true if not in sequence

### Ternary

Ternary operators (also called conditional expressions) evaluate based on a condition being true or false.

`[true] if [expression] else [false]`

## Data Types

### Strings

### Numbers

### Booleans

### Lists

### Tuples

### Sets

### Dictionaries

## Conditionals

## Loops

## Functions

A function is a block of code that can be reused and runs only when called upon.

```python
# defining a function
def function_name(parameters):
    # code
    return expression

# calling a function
function_name()
```

### Anonymous functions

Anonymous functions are functions without a name. They use the `lambda` keyword instead of the `def` keyword.

```py
def square(x): return x**2

square_x = lambda x: x**2
```

## Exceptions

### Try and Except

Try and except statements are used to catch and handle exceptions. Code that can raise exceptions is written in the try block and code that handles the exception is written in the except block.

```py
try:
    #code
except:
    # error handling
    print('error raised')
```

We can write many except blocks for different kinds of errors.

```py
try:
    #code
except IndexError:
    # error handling
    print('IndexError raised')
except ValueError:
    # error handling
    print('ValueError raised')
```

The `else` keyword can define a code block that executes if no errors are raised in the `try` block. And the `finally` keyword defines a block which always executes regardless if an error was raised or not.

```py
try:
    #code
except:
    # error handling
    print('error raised')
else:
    #code which executes if no exception
    print('no errors raised')
finally:
    #code which always executes
```

The `raise` keyword allows us to intentionally raise an error when a particular condition happens in our code.

```py
if condition:
    raise Exception("exception raised")

# specific error raised
if condition:
    raise TypeError("TypeError raised")
```

## Object-Oriented

Object-oriented programming (OOP) is a method of programming that utilises objects and classes. The idea is to package data and functions that work together as a single unit so that no other part of the application can affect them. This concept is known as encapsulation.

### Classes

Classes act as a blueprint for making objects. Variables defined in a class are called attributes, whereas functions in a class are called methods. Attributes and variables can be accessed using the dot operator i.e. `my_class.my_attribute`.

```py
class MyClass:
  x = 5

my_object = MyClass()
print(my_object.x)
```

### Objects

Objects have associated states and behaviours. States are determined by the attributes and behaviours are determined by the methods.

```py
class MyClass:
  def __init__(self, attr1, attr2):
    self.attr1 = attr1
    self.attr2 = attr2

  def __str__(self):
    return f"{self.attr1}({self.attr2})"

my_object = MyClass("John", 36)

print(my_object)
```

The `__init__()` function is common to every class and is automatically run when the class is used to create an object. It is used to assign values to properties when setting up an object

The `__str__()` function is used to determine what is returned when the object is represented as a string.

The `self` parameter refers to the current instance of the class and accesses varables in the class.

### Inheritance

Inheritance is when a class inherits the methods and properties from another class

```py
class ParentClass():
    def __init__(self, attr1, attr2):
        self.attr1 = attr1
        self.attr2 = attr2

class ChildClass(ParentClass):
    def __init__(self, attr1, attr2, attr3, attr3):
        self.attr3 = attr3
        self.attr4 = attr4

        ParentClass.__init__(self, attr1, attr2)
```

### Polymorphism

```py
class MyClass:
    def method(self):
        #code

class SubClass(MyClass):
    def method(self):
        #new code
```
