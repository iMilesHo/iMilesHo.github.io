---
layout: post
title: Python Review Notes
date: 2024-02-07 12:00:00
description: Notes on Python
tags: Python Foundation
categories: posts
giscus_comments: true
related_posts: true
toc:
  sidebar: left
---

## Python Review
Here are some important notes on Python regarding the reason why we use Python, the setup, the language basics, some practical tips, and some great references.

### why Python?
- Widely used
- General purpose programming language
- Scientific compututation functionality similar to MATLAB
- Used by major deep learning libraries such as PyTorch and TensorFlow

### Setup
- Environment setup
  - Problem
    - Different versions of Python
    - Different versions of libraries (countless)
    - Even same library versions have different versions
  - Solution
    - Use virtual environment
    - Use conda
    - Use pipenv
    - Use Docker

Common workflow
- Keep multiple Python environments that are isolated from each other
- Each environment has its own Python version and libraries
- Each environment can be easily replicated

Anaconda is a popular Python environment/package manager
- Create environments
  - $ conda create -n <environment_name> // -n indicates the name of the environment
  - $ conda create -n <environment_name> python=3.8 // specify the version of Python
  - $ conda create -f <environment.yml> // create environment from a file
- Activate/deactivate environments
  - $ conda activate <environment_name>
  - $ conda deactivate // deactivate the current environment
- Export environments
  - $ conda env list // list all environments
  - $ conda activate <environment_name> // activate the environment first
  - $ conda env export > environment.yml // export the environment to a file

### Python Basics
- Common Operations
```python
# This is a comment
x = 10
y = 3
z = x + y
print(z)
x ** y # exponentiation
x / y # division, the result is 3.3333333333333335
x // y # floor division, the result is 3
x % y # modulo, the result is 1
x / float(y) # the result is 3.3333333333333335
str(x) + " + " + str(y) # convert to string
```
- Built-in Values
```python
a, b = True, False
x = None # Variables can be assigned None representing the absence of a value
array = [1, 2, 3, None] # List can contain None
def func():
  return None # Functions can return None, used to indicate that the function does not return a value
```

- Python is a strongly-typed and dynamically-typed language
  - Strongly-typed: The type of a variable can not be coerced into another type like in JavaScript
    - e.g. "1" + 2 // TypeError: can only concatenate str (not "int") to str
  - Dynamically-typed: The type of a variable is determined at runtime, not at compile time. Variables are names of values or objects references. Variables can be reassigned to values of a different type.
    - e.g. x = 1 // x is an integer
    - x = "hello" // x is a string
- Execution of Python code
  - Python code is first interpreted into bytecode(.pyc) and then compiled by a VM implementation into machine instructions. (Most commonly using C.)
  - Python is slower, but it can run highly optimized C/C++ subroutines which makes scientific computing (e.g. matrix multiplication) very fast.

### Python Common Data Structures
Collections
- List
  - Ordered, mutable, allows duplicate elements
  - e.g. [1, 2, 3, 4, 5]
```python
names = ['Alice', 'Bob', 'Charlie']
#index      0       1        2
#index     -3      -2       -1
names[0] # 'Alice'
print(len(names)) # get the length of the list
print(names) # ['Alice', 'Bob', 'Charlie']
names.append('David') # ['Alice', 'Bob', 'Charlie', 'David']

my_empty_list = []
my_empty_list = list()

stuff = [1, 2, ["hello", "world"], True, -0.12, None]

# List Slicing
names[-1] # 'Charlie'
names[1:2] # ['Bob']
numbers = [0, 1, 2, 3, 4, 5, 6]
numbers[0:3] == numbers[:3] == [0, 1, 2]
numbers[5:] == numbers[5:7] == [5, 6]
numbers[:] == numbers == [0, 1, 2, 3, 4, 5, 6]
numbers[-1] == 6 # Negative index wraps around
numbers[-3:] == [4, 5, 6]
numbers[3:-2] == [3, 4] # Can mix and match
```

- Tuple
  - Ordered, immutable, allows duplicate elements
  - e.g. (1, 2, 3, 4, 5)
```python
names = ('Alice', 'Bob', 'Charlie')
#index      0       1        2
#index     -3      -2       -1
names[0] # 'Alice'
print(len(names)) # get the length of the tuple
print(names) # ('Alice', 'Bob', 'Charlie')
names[0] = 'David' # TypeError: 'tuple' object does not support item assignment
empty_tuple = ()
empty_tuple = tuple()
single = (1,) # single element tuple, otherwise it's just a number
```

- Dictionary
  - Unordered, mutable, indexed, no duplicate elements
  - e.g. {'name': 'Alice', 'age': 25}
```python
phonebook = {}
phonebook = dict()
phonebook = {'Zach': '12-37'} # dictionary with one key-value pair
phonebook['Alice'] = '123-456' # add a new key-value pair

print('Alice' in phonebook) # True, check if a key exists, can not check for values
print('Bob' in phonebook) # False
print(phonebook['Alice']) # '123-456'
print(phonebook['Bob']) # KeyError: 'Bob'

print(phonebook.get('Alice')) # '123-456'
print(phonebook.get('Bob')) # None

print(phonebook) # {'Alice': '123-456', 'Zach': '12-37'}

phonebook['Alice'] = '321-456' # update a value
del phonebook['Alice'] # delete a key-value pair
phonebook.clear() # remove all key-value pairs

print(phonebook) # {}
```

- Set
  - Unordered, mutable, no duplicate elements
  - e.g. {1, 2, 3, 4, 5}
```python
basket = {'apple', 'orange', 'apple', 'pear', 'orange', 'banana'}
print(basket)                      # show that duplicates have been removed
{'orange', 'banana', 'pear', 'apple'}
'orange' in basket                 # fast membership testing
True
'crabgrass' in basket
False

# Demonstrate set operations on unique letters from two words

a = set('abracadabra')
b = set('alacazam')
a                                  # unique letters in a
{'a', 'r', 'b', 'c', 'd'}
a - b                              # letters in a but not in b
{'r', 'd', 'b'}
a | b                              # letters in a or b or both
{'a', 'c', 'r', 'd', 'b', 'm', 'z', 'l'}
a & b                              # letters in both a and b
{'a', 'c'}
a ^ b                              # letters in a or b but not both
{'r', 'd', 'b', 'm', 'z', 'l'}
```

- Loops
```python
names = ['Alice', 'Bob', 'Charlie']
for i, name in enumerate(names):
  print(i, name)

phonebook = {'Alice': '123-456', 'Bob': '456-789', 'Charlie': '789-123'}
for name, number in phonebook.items():
  print(name, number)

for key, value in enumerate(phonebook):
  print(key, value)

for name in phonebook.keys():
  print(name)

for number in phonebook.values():
  print(number)
```

- Classes

```python
class Dog:
  # Constructor `a = Dog('Fido', 3)`
  def __init__(self, name, age):
    self.name = name # refer instance variables with `self`
    self.age = age # instance variables are public by default

  def bark(self):
    print('Woof!')

  def birthday(self):
    self.age += 1

  def get_name(self):
    return self.name

  def get_age(self):
    return self.age

  def set_name(self, name):
    self.name = name

  def set_age(self, age):
    self.age = age

  # same function name, different parameters which is called method overloading
  def play(self, other_dog):
    print(self.name, 'plays with', other_dog.name)
  
  def play(self):
    print(self.name, 'plays with self')



fido = Dog('Fido', 3)
fido.bark() # Woof!
fido.birthday()
print(fido.get_age()) # 4

# Inheritance
class Husky(Dog):
  # redefine the constructor
  def __init__(self, name, age, color):
    super().__init__(name, age) # call the parent class constructor
    self.color = color
  def birthday(self):
    self.age += 5 # override the parent class method
```

### Introduction to NumPy
- NumPy is optimized for matrix and vector operations
- Makes use of C/C++ subroutines and memory-efficient data structures. (Lots of computation can be efficiently represneted as vectors.)
- NumPy arrays are homogeneous, i.e. all elements are of the same type
- Main data structure is the numpy.ndarray. The constructor function is numpy.array()

```python
import numpy as np
x = np.array([1, 2, 3]) # 1D array, [1, 2, 3], shape is (3,)
y = np.array([[3,4 ,5]]) # 2D array, [[3, 4, 5]], shape is (1, 3)
z = np.array([[1, 2, 3], [4, 5, 6]]) # 2D array, [[1, 2, 3], [4, 5, 6]], shape is (2, 3)
print(x.shape) # (3,)
print(y.shape) # (1, 3)
print(z.shape) # (2, 3)

# Create arrays with zeros, ones, and random numbers
a = np.zeros((2, 3)) # 2x3 array of zeros
b = np.ones((1, 2)) # 1x2 array of ones
c = np.random.random((2, 2)) # 2x2 array of random numbers, uniform distribution, [0, 1)
d = np.random.randn(2, 2) # 2x2 array of random numbers, normal distribution, mean 0, standard deviation 1
e = np.random.randint(1, 10, (2, 2)) # 2x2 array of random integers, [1, 10)
f = np.random.choice([1, 2, 3, 4, 5], (2, 2)) # 2x2 array of random integers, [1, 5]

# np.ndarray Operations
# Reductions: np.max(), np.min(), np.sum(), np.mean(), np.std(), np.var(). np.std() is the square root of np.var()

# shape (3, 2)
x = np.array([[1, 2], [3, 4], [5, 6]])
print(np.max(x)) # 6
print(np.max(x, axis=0)) # [5, 6]
print(np.max(x, axis=0, keepdims=True)) # [[5, 6]]
print(np.max(x, axis=1)) # [2, 4, 6]
print(np.max(x, axis=1, keepdims=True)) # [[2], [4], [6]]

# Matrix Operations: np.dot(), np.matmul(), np.linalg.norm, .T, etc.
# Infix operator(i.e. +, -, *, /, **) are element-wise operations
# Element-wise product of matrices A 。 B is A * B
# Element-wise division of matrices A / B is A / B
# Dot product and matrix vector product(between 1-D array vectors) are using np.dot()
np.dot(u, v) 
np.dot(x, W) # matrix vector product

# Matrix product/ multipication prefer np.matmul() over np.dot()
np.matmul(A, B) # matrix product
A @ B # matrix product

# Transpose
x.T # transpose of x
```

- Indexing and Slicing
```python
x = np.random.random((3, 4))
x[:] # all elements keep shape
x[0, :] # first row, shape is (4,)
x[:, 0] # first column, shape is (3,)
x[1, 1:3] # second row, second and third column, shape is (2,)

# Note: selecting with an ndarray, list, or tuple will preserve the shape
x[(1, 2), :] # second and third row, shape is (2, 4)
x[np.array([1, 2]), :] # second and third row, shape is (2, 4)
x[[1, 2], :] # second and third row, shape is (2, 4)

x[:, :, np.newaxis] # add a new axis, shape is (3, 4, 1)
```

- Broadcasting
  - allows for element-wise operations between arrays of different shapes

```python
x = np.random.random((3, 4)) # Random 3x4 matrix
y = np.random.random((3,1)) # Random 3x1 vector
z = np.random.random((1, 4)) # Random 1x4 vector

x + y # Adds y to each column of x
x * z # Multiplies each row of x by z element-wise
```
  - Broadcasting generalize: NumPy compares their shapes element-wise. It starts with the trailing dimensions and works its way forward. Two dimensions are compatible when
    - 1. they are equal, or
    - 2. one of them is 1 (in which case, elements on the axis are repeated along the dimension)
```python
a = np.random.random((3, 4))
b = np.random.random((3, 1))
c = np.random.random((3, ))

b + b.T # works
a + c # ValueError: operands could not be broadcast together with shapes (3,4) (3,)
b + c # works, b is broadcasted to (3, 3), then element-wise addition
```

- Efficient Numpy Code
  - Avoid explicit for-loops over indices/axes at all costs. For-loops will dramatically slow down our code.(~10-100x).

```python
# Slow
x = np.random.random((1000, 1000))
y = np.zeros((1000, 1000))
for i in range(1000):
  for j in range(1000):
    y[i, j] = x[i, j] + 1

# Fast
x = np.random.random((1000, 1000))
y = x + 1
```

  - Use NumPy's built-in functions and operations whenever possible. They are highly optimized and run much faster than their Python counterparts.

```python
# Slow
x = np.random.random((1000, 1000))
y = np.zeros((1000, 1000))
for i in range(1000):
  for j in range(1000):
    y[i, j] = np.sin(x[i, j])

# Fast
x = np.random.random((1000, 1000))
y = np.sin(x)
```

  - Use NumPy's broadcasting feature to avoid unnecessary duplication of data. This will save memory and speed up your code.

```python
# Slow
x = np.random.random((1000, 1000))
y = np.random.random((1000, 1))
z = np.zeros((1000, 1000))
for i in range(1000):
  for j in range(1000):
    z[i, j] = x[i, j] + y[i, 0]

# Fast
x = np.random.random((1000, 1000))
y = np.random.random((1000, 1))
z = x + y
```

  - Use NumPy's built-in linear algebra functions for matrix operations. They are highly optimized and run much faster than their Python counterparts.

```python
# Slow
x = np.random.random((1000, 1000))
y = np.random.random((1000, 1000))
z = np.zeros((1000, 1000))
for i in range(1000):
  for j in range(1000):
    for k in range(1000):
      z[i, j] += x[i, k] * y[k, j]

# Fast
x = np.random.random((1000, 1000))
y = np.random.random((1000, 1000))
z = np.dot(x, y)
```

### Pratical Python Tips

- Use list comprehensions to create lists
```python
# Slow
squares = []
for i in range(10):
  squares.append(i ** 2)

# Fast
squares = [i ** 2 for i in range(10)]
# can also use conditionals
squares = [i ** 2 for i in range(10) if i % 2 == 0]
```

- Convenient Syntax
```python
# Swap two variables
a, b = 1, 2
a, b = b, a

# Multiple assignment
a, b, c = 1, 2, 3
a, b, c = ('Alice', 25, True)

# Unpack a list
x = [1, 2, 3]
a, b, c = x

# Return multiple values from a function
def f():
  return 1, 2, 3
a, b, c = f()

# Joining list of strings with a delimiter
names = ['Alice', 'Bob', 'Charlie']
', '.join(names) # 'Alice, Bob, Charlie'

# String literals with both single and double quotes
s = "Hello, 'world'"
s = 'Hello, "world"'
```

- Debugging Tips: use interactive shell
  - Python has no integer overflow
  - Try out syntax
  - array.shape, array.dtype, type(array)
  - import pdb; pdb.set_trace() # set a breakpoint
  - or breakpoint() # Python 3.7+, set a breakpoint
  - print(f’My name is {name}’) # f-string, Python 3.6+, string interpolation

```python
array.shape # get the shape of the numpy array
array.dtype # get the element data type of the numpy array
type(array) # get the type of a variable
```

- Common Errors
  - SyntaxError: invalid syntax
  - NameError: name 'x' is not defined
  - TypeError: can only concatenate str (not "int") to str
  - ValueError: invalid literal for int() with base 10: 'hello'
  - IndexError: list index out of range
  - KeyError: 'Alice'
  - AttributeError: 'list' object has no attribute 'append'
  - IndentationError: expected an indented block
  - ZeroDivisionError: division by zero
  - FileNotFoundError: [Errno 2] No such file or directory: 'file.txt'
  - ModuleNotFoundError: No module named 'numpy'

### Other Great References

- Official Python 3 documentation: https://docs.python.org/3/
- Official Anaconda user guide: https://docs.conda.io/projects/conda/en/latest/user-guide/index.html
- Official NumPy documentation: https://numpy.org/doc/stable/
