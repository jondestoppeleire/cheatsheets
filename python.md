# Python Language Cheatsheet

## Basics

### Variables
```python
a = 10                  # Integer
b = 3.14                # Float
c = "Hello"             # String
```

### Constants
```python
PI = 3.14159            # Conventionally, constants are in uppercase
```

### Basic Types
```python
int, float, complex     # Numeric types
str                     # String type
bool                    # Boolean type
None                    # Represents the absence of a value
```

### Printing and Formatting
```python
print("Hello, world!")
print(f"The value of pi is approximately {PI:.2f}")
```

### Functions
```python
def add(x, y):
    return x + y

# Function with default parameters
def greet(name, greeting="Hello"):
    print(f"{greeting}, {name}!")
```

## Control Structures

### If Statement
```python
if x > 0:
    print("Positive")
elif x < 0:
    print("Negative")
else:
    print("Zero")
```

### Loops
```python
# For loop
for i in range(5):
    print(i)

# While loop
j = 0
while j < 5:
    print(j)
    j += 1
```

### Comprehensions
```python
# List comprehension
squares = [x**2 for x in range(10)]

# Dictionary comprehension
square_dict = {x: x**2 for x in range(5)}
```

## Data Structures

### Lists
```python
my_list = [1, 2, 3]
my_list.append(4)       # Adds an item
my_list[0] = 0          # Sets the first item
```

### Tuples
```python
my_tuple = (1, 2, 3)
```

### Dictionaries
```python
my_dict = {'a': 1, 'b': 2}
my_dict['c'] = 3        # Adds a new key-value pair
```

### Sets
```python
my_set = {1, 2, 3}
my_set.add(4)           # Adds an item
```

## Modules and Packages
```python
import math
from datetime import datetime

print(math.sqrt(16))    # Using the math module
print(datetime.now())   # Prints the current date and time
```

## Exception Handling
```python
try:
    x = 1 / 0
except ZeroDivisionError:
    print("Can't divide by zero")
finally:
    print("Attempted division")
```

## File Handling
```python
# Reading from a file
with open("file.txt", "r") as file:
    content = file.read()

# Writing to a file
with open("file.txt", "w") as file:
    file.write("Hello, world!")
```

## Comments
```python
# This is a single-line comment

'''
This is a
multi-line comment
'''
```

