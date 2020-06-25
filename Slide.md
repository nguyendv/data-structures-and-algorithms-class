# Chapter 1. Introduction
## 1.1. Introduction
Computer science is *not* about computers. It's the science of computing: how to compute (or calculate, process) data correctly, fast, and efficiently.

```

                  +---------------+
                  |               |
                  |               |
      INPUT +---> |   Computing   +---> OUTPUT
                  |               |
                  |               |
                  +---------------+


```

How to represent, or model, data? Data Structures.
Steps to transform input data to output data: Algorithms.

Algorithms need to:
- correct: provides expected output
- fast: quickly to provide output, especially when the input size is large
- efficient: not wasting hardware resources

Coming up with the right data structures for your data is 50% of the work. Many times the correct algorithms just emerges naturally after you have the data structures.

"Worry about the data structures first, and your code will naturally be cleaner." - Linus Torvalds, probalbly.
"Bad programmers worry about the code. Good programmers worry about data structures and their relationships." - same man.

Examples of data structures: list, class, dictionary, etc.
Examples of algorithms:
- Steps to cook rice: 1. Wash the rice. 2. Fill the water. 3. Press cook button.
- Search an number in a list

## 1.2. Programming Fundamentals
```Python
# Variables
name = "Dave"  # name: variable name, "Dave": variable value
country = "Vietnam"
boiling_point = 100

# Function: take input, return output
def add(a, b):
    return a + b
def say(name):
    print(name) # Both input and return are optional!
```

Data type: a data type defines which values a variable can take, and which operations can be operated on those values
There are 2 types of data types:
- Primitive data types: types are built-in, provided by language creators
- Abstract data types: types are constructed from built-ins, usually from language users

### Built data types
```Python
number = 1
str = "I am a string"
character = 'c'
is_it_true = True # boolean
is_it_false = False # boolean
a_ist = [1, 2, 3]
a_dict = {"name": "Dave", age: 30}
```
See more at https://docs.python.org/3/library/stdtypes.html

### Class
How to represent a laptop in Python?
Try to describe it in natural language fist:
- What's brand? Apple
- What's color? Silver
- What's price? $1,000
- What's serial number? 12324433224

brand, color, price, and serial_number are *attributes* of the Laptop class.

From a class we can *instantiate* multiple objects:
- apple macbook air is an object of the Laptop class
- lenovo thinkpad is an object of the Laptop class

To tell an object to do something, we call its *method*. Examples of methods for the Laptop class:
- start()
- stop()
- explode()

```Python
class Laptop:
    def __init__(self, brand, color, price, serial_number):
        """ This is a special method named constructor"""
        self.brand = brand
        self.color = color
        self.price = price
        self.serial_number = number

    def tell_me_your_color(self):
        """ `self` is a special variable arguments of every methods. It holds the current object
        Every method should start with `self`, unless you want a static method"""
        print(self.color)
```

### Exercise
1. Define a class called Animal, and instantiate a dog, cat, and fish objects.
2. Define method `legs()` for the `Animal` class, which print out number of legs for the animal.

## 1.3. Binary Search
Given a list of unique, sorted numbers, find the index of number 10 in the list
For example:
Input: [1, 2, 3, 4, 5, 7, 10, 26], output should be 7
Input: [1, 2,  99, 333], output should be None
Input: [10, 11, 22, 33], output should be 0

Naive solution:
Go over each number from left to right and compare it to 10.

Problem: what if the list is huge (1,000,000), and 10 is at the end of the list, or worse, not in the list?
Number of comparisons: 1,000,000

Solution: binary search:
```
1. Find the middle number and cut the list into halves: left and right
2. If 10 < middle number: it should be in the left half. Otherwise it should be in the right half
3. Repeat step 1 with the left or right list.
```
Number of comparisons: log(1,000,000) = 10.


# Home Works
1. Implement naive search
```Python
def naive_search(numbers, 100):
    your code here
```

2. Implement binary search
```Python
def binary_search(numbers, 100):
    # hints: recursion
    # to generate a large list of numbers for testing: numbers = list(range(100000))
```

3. TBD
