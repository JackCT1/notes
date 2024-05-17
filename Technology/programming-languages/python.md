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
