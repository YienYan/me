TODO: Reflect on what you learned this week and what is still unclear.
python3 ../course/set2/tests.py
I feel that my understanding of loops is still not proficient enough, and I am not able to write a complete piece of code independently.
MC Hammer
'#' single-line comment
''' or """ muilti-line comment
'+' addition eg. result = 5 + 3 (result is 8)
'-' subtraction eg. result = 5 - 3 (result is 2)
'*' multiplication eg. result = 5 * 3 (result is 15)
'/' division eg. result = 5 / 3 (result is about 1.67)
'//' floor division eg. result = 5 // 3 (Result is 1)
'%' Modulus eg. result = 5 % 3 (result is 2)
'==' Equal to eg. result = (5 == 3) (result is False)
'!=' Not equal to 
'>' Greater than
'<' Less than
'>=' greater than or equal to
'<=' less than or equal to
'=' assignment
'+=' add and assign eg. a += 3 (a = a + 3)
'-=' subtract and assign
'*=' multiply and assign
'/=' divide and assign
'//=' floor divide and assign
'%=' moudulus and assign
'**=' exponentiate and assign
'[]' lists, arrays, indexing
'()' tuples, function calls
'{}' sets, dictionaries

In "loops_preview' and "loops_1a" & "loops_2_preview" I learned to use "for" loop to iterate over a range, "list.append()" method to add items to a list.

In "loops_1c" I learned to use function arguments to pass variables and generate a list based on those arguments.

In "loops_2" and "loop_5" i learned ues list multiplication to create lists with repeated elements and use nested 'for' loops to generate a 2D list.

In "loops_3" i learned to use the 'range()' function to generate a sequence of numbers and convert numbers to strings and using list multiplication to create lists with repeated elements.

In "loop_4" i learned to use list comprehensions to generate lists with consecutive numbers.

append: in Python, the append method is used with lists to add an element to the end of the list. Here's a basic example of how to use the append method:

# Create an empty list
my_list = []

# Use the append method to add elements to the list
my_list.append(1)
my_list.append(2)
my_list.append(3)

# Print the list
print(my_list)
The output will be:

[1, 2, 3]

list.append(element)
'list': The list you are working with.
'element': The element you want to add to the end of the list.

Examples:

Adding a number to a list:


numbers = [1, 2, 3]
numbers.append(4)
print(numbers)  # Output: [1, 2, 3, 4]
Adding a string to a list:

python
Copy code
fruits = ['apple', 'banana']
fruits.append('cherry')
print(fruits)  # Output: ['apple', 'banana', 'cherry']
Adding a list to a list (as a single element):

list_of_lists = [[1, 2], [3, 4]]
list_of_lists.append([5, 6])
print(list_of_lists)  # Output: [[1, 2], [3, 4], [5, 6]]

The 'append' method modifies the 'list' in place; it does not return a new 'list'.
The 'append' method can only add one element at a time. If you want to add multiple elements, you can use the extend method.

Using the 'extend' Method
Unlike the 'append' method, the 'extend' method can add multiple elements from an iterable (e.g., a list) to the end of the list:

# Create a list
my_list = [1, 2, 3]

# Use the extend method to add multiple elements
my_list.extend([4, 5, 6])

# Print the list
print(my_list)  # Output: [1, 2, 3, 4, 5, 6]

str
'str' Class in Python
The 'str' class is used to create string objects in Python. A string is a sequence of characters, and the 'str' class provides a variety of methods to work with strings.

Constructor
The 'str' class can be instantiated in a couple of ways:

Default Constructor:

str() -> str

This creates an empty string:

s = str()
print(s)  # Output: ''

From an Object:
str(object='') -> str

This converts an object to its string representation using the '__str__' method if defined, otherwise the' __repr__ 'method:

num = 123
s = str(num)
print(s)  # Output: '123'

From Bytes or Buffer:

str(bytes_or_buffer[, encoding[, errors]]) -> str
This creates a string from bytes or a buffer. If 'encoding' or 'errors' are specified, the object must expose a data buffer that will be decoded using the given encoding and error handler.

bytes_or_buffer: This is the bytes or buffer you want to convert to a string.
encoding: This specifies the encoding to use (e.g., 'utf-8'). If not specified, it defaults to sys.getdefaultencoding().
errors: This specifies the error handling scheme. It defaults to 'strict'. Other options include 'ignore', 'replace', 'xmlcharrefreplace', 'backslashreplace', and any other name registered via 'codecs.register_error()'.
Example:
b = b'hello'
s = str(b, 'utf-8')
print(s)  # Output: 'hello'

Summary
'str(object='') -> str': Converts the given object to a string. If the object has a __str__ method, it uses that; otherwise, it uses 'repr(object)'.
'str(bytes_or_buffer[, encoding[, errors]]) -> str': Converts bytes or a buffer to a string, decoding using the specified encoding and error handling scheme if provided.
Default Values
'encoding': Defaults to sys.getdefaultencoding(), which is usually 'utf-8'.
'errors': Defaults to 'strict', which means it will raise a 'UnicodeDecodeError' on errors.
Practical Example
Here is a practical example demonstrating different ways to create strings using the str class:

# Default empty string
s1 = str()
print(s1)  # Output: ''

# String representation of a number
num = 123
s2 = str(num)
print(s2)  # Output: '123'

# String representation of a list
lst = [1, 2, 3]
s3 = str(lst)
print(s3)  # Output: '[1, 2, 3]'

# String from bytes with encoding
b = b'hello'
s4 = str(b, 'utf-8')
print(s4)  # Output: 'hello'

# Handling errors
invalid_bytes = b'\xff'
try:
    s5 = str(invalid_bytes, 'utf-8')
except UnicodeDecodeError as e:
    print(f"UnicodeDecodeError: {e}")

# Using a different error handling scheme
s6 = str(invalid_bytes, 'utf-8', errors='replace')
print(s6)  # Output: '�'


format
The 'format' method in Python is a powerful tool used for formatting strings. It allows you to insert variables into strings using placeholders '{}', making string interpolation flexible and readable.

Basic Syntax
str.format(*args, **kwargs)
'*args': Positional arguments that are inserted into the '{}' placeholders in the order they are provided.
'**kwargs': Keyword arguments that are inserted into the '{}' placeholders by name.
Basic Usage Examples
Simple Placeholder:
name = "Alice"
age = 30
formatted_string = "My name is {} and I am {} years old.".format(name, age)
print(formatted_string)
# Output: My name is Alice and I am 30 years old.

Using Positional Arguments:
formatted_string = "The {0} is {1}.".format("price", 10)
print(formatted_string)
# Output: The price is 10.

Using Keyword Arguments:
formatted_string = "The {item} is {value}.".format(item="price", value=10)
print(formatted_string)
# Output: The price is 10.

Mixing Positional and Keyword Arguments:
formatted_string = "The {0} is {value}.".format("price", value=10)
print(formatted_string)
# Output: The price is 10.

Number Formatting:
Specifying decimal places:
pi = 3.14159265
formatted_string = "Pi is approximately {:.2f}.".format(pi)
print(formatted_string)
# Output: Pi is approximately 3.14.
Adding thousand separators:
number = 1000000
formatted_string = "The number is {:,}".format(number)
print(formatted_string)
# Output: The number is 1,000,000.

Padding and Alignment:
Left, center, and right alignment:
text = "Hello"
formatted_string = "|{:<10}|{:^10}|{:>10}|".format(text, text, text)
print(formatted_string)
# Output: |Hello     |  Hello   |     Hello|
Using a specific character for padding:
formatted_string = "{:*^10}".format(text)
print(formatted_string)
# Output: **Hello***

example:
name = "Alice"
age = 30
balance = 12345.6789

# Basic usage
print("My name is {} and I am {} years old.".format(name, age))

# Positional arguments
print("The {0} is {1}.".format("price", 10))

# Keyword arguments
print("The {item} is {value}.".format(item="price", value=10))

# Number formatting
print("Pi is approximately {:.2f}.".format(3.14159265))

# Thousand separators
print("The number is {:,}".format(1000000))

# Padding and alignment
print("|{:<10}|{:^10}|{:>10}|".format("Left", "Center", "Right"))

# Using specific character for padding
print("{:*^10}".format("Hello"))

# Comprehensive example
print("Name: {name}, Age: {age}, Balance: ${balance:,.2f}".format(name=name, age=age, balance=balance))