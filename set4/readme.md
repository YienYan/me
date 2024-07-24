TODO: Reflect on what you learned this week and what is still unclear.
python3 ../course/set4/tests.py
I learned how to create a txt through use python.
 This is the first time I've realized that code interacts with other files. I feel it's getting harder and harder, and I don't even understand the requirements of the last piece of code in part 1. I thought it was about putting this file into Grasshopper to have the model laser cut, but later I found out that it was actually about counting how many times the word "laser" appears in the last text file of set4.

 'open()': read file content
 'json.loads()' : convert a JSON string into a Python dictionary and parse JSON responses
 'requests.get()': send HTTP requests
 'response.status_code': check if the request was successful
 'response.text': get the response content
 'readlines()': read file content line by line
 'count()': count occurrences of a substring
 'with open()' and 'write()' write results to a file.
 '__name__ == "__main__"' check if the script is run as the main program.
 'print()' to output results.
 'os.path.isfile()' check if files exist

 f-strings
in Python, f-strings (formatted string literals) provide a concise and efficient way to embed expressions inside string literals. Introduced in Python 3.6, f-strings allow you to include variables and expressions directly within a string, prefixed by 'f' or 'F'.

Basic Syntax
python
Copy code
f"string {expression}"
string: The regular string text.
{expression}: The Python expression enclosed in curly braces {}, which will be evaluated at runtime and embedded in the string.

Basic Examples
Embedding Variables:
name = "Alice"
age = 30
greeting = f"My name is {name} and I am {age} years old."
print(greeting)
# Output: My name is Alice and I am 30 years old.

Embedding Expressions:
x = 10
y = 5
result = f"The sum of {x} and {y} is {x + y}."
print(result)
# Output: The sum of 10 and 5 is 15.

Calling Functions:
def greet(name):
    return f"Hello, {name}!"

greeting = f"{greet('Alice')}"
print(greeting)
# Output: Hello, Alice!

Using Dictionaries:
person = {"name": "Bob", "age": 25}
introduction = f"{person['name']} is {person['age']} years old."
print(introduction)
# Output: Bob is 25 years old.

Advanced Usage
Formatting Numbers:
value = 1234.56789
formatted_value = f"{value:.2f}"  # Retain two decimal places
print(formatted_value)
# Output: 1234.57

Padding and Alignment:
text = "Hello"
formatted_text = f"{text:<10}"  # Left align
print(f"|{formatted_text}|")
# Output: |Hello     |

Thousand Separators:
number = 1000000
formatted_number = f"{number:,}"
print(formatted_number)

# Output: 1,000,000
Date and Time Formatting:
from datetime import datetime
now = datetime.now()
formatted_date = f"{now:%Y-%m-%d %H:%M:%S}"
print(formatted_date)

# Output: Current date and time, e.g., 2023-07-24 15:46:23
Comparison with Other Formatting Methods
'%' Operator (old method):
name = "Alice"
age = 30
greeting = "My name is %s and I am %d years old." % (name, age)
print(greeting)
# Output: My name is Alice and I am 30 years old.

'str.format()' Method:
name = "Alice"
age = 30
greeting = "My name is {} and I am {} years old.".format(name, age)
print(greeting)
# Output: My name is Alice and I am 30 years old.

f-strings (more concise and better performance):
name = "Alice"
age = 30
greeting = f"My name is {name} and I am {age} years old."
print(greeting)
# Output: My name is Alice and I am 30 years old.
Conclusion
f-strings offer a more concise and intuitive way to embed variables and expressions in strings. They are suitable for most string interpolation scenarios due to their readability and performance advantages over traditional string formatting methods.





