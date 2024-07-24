TODO: Reflect on what you learned this week and what is still unclear.
python3 ../course/set3/tests.py
I think set3 is much more complex than set2 and includes a lot of new concepts. Therefore, at the beginning, I really didn't know how to write code that could run successfully. I still don't quite understand when to use underscores to connect consecutive words and when to just capitalize the first letter.

In "loop_ranger" & "two_step_ranger" I learned to use a 'while' loop to iterate until a condition is met and Initialize a variable ('current') and updating it within the loop and append values to a list using 'list.append()'.

In "stubborn_asker" I learned to use an infinite 'while' loop to repeatedly ask for user input and use 'try...except' to handle invalid input and ensure the input is an integer and chevk if the input is within the specified range and repeating the request if it is not.

In "not_number_rejector' I learned to use 'try...except' to repeatedly prompt the user until a valid number is entered.

In 'supper_asker' I learned to Combine the logic from 'stubborn_asker' and 'not_number_rejector' to create a more robust input validation function and use a 'try-except' block for error handling and a 'while True' loop for continuous prompting until valid input is received.

Loops: Using 'while' loops to repeat a block of code until a specific condition is met.
List Operations: Using list methods like 'append()' to build lists.
Input and Output: Using 'input()' to get user input and 'print()' to display messages.
Error Handling: Using 'try-except' blocks to handle exceptions and ensure the program continues to run smoothly.
Type Conversion: Using functions like 'int()' to convert input to the desired type.


while
The 'while' loop in Python is used to repeatedly execute a block of code as long as a given condition is true. It is a fundamental control flow statement that allows for repeated execution based on a condition, which is evaluated before the execution of the loop’s body.

Basic Syntax
while condition:
    # code block to be executed
'condition': An expression that is evaluated before each iteration of the loop. If the condition is true, the loop's body is executed. If the condition is false, the loop stops executing.

Examples
Basic Example:
count = 0
while count < 5:
    print(count)
    count += 1
# Output: 0 1 2 3 4


Using 'break' to Exit a Loop:
count = 0
while count < 10:
    print(count)
    if count == 5:
        break
    count += 1
# Output: 0 1 2 3 4 5

Using 'continue' to Skip an Iteration:
count = 0
while count < 5:
    count += 1
    if count == 3:
        continue
    print(count)
# Output: 1 2 4 5

Infinite Loop:
while True:
    print("This is an infinite loop. Press Ctrl+C to stop.")
    # You can use a break statement to exit the loop under a certain condition

    Using 'else' with 'while' Loop:
The else block is executed when the loop condition becomes false (but not if the loop is terminated by a break statement).
count = 0
while count < 5:
    print(count)
    count += 1
else:
    print("Loop finished")
# Output: 0 1 2 3 4
#         Loop finished

Practical Example
Here is a practical example that uses a while loop to find the first occurrence of a number in a list:
numbers = [10, 20, 30, 40, 50]
target = 30
index = 0

while index < len(numbers):
    if numbers[index] == target:
        print(f"Found {target} at index {index}")
        break
    index += 1
else:
    print(f"{target} not found in the list")
# Output: Found 30 at index 2

Important Notes
Ensure that the condition will eventually become false; otherwise, you will create an infinite loop.
Use 'break' to exit the loop prematurely when a certain condition is met.
Use 'continue' to skip the rest of the code inside the loop for the current iteration and move to the next iteration.
The 'else' block, if used, will execute only if the loop terminates naturally (i.e., when the condition becomes false), not when it's terminated by a 'break'.

In Python, the 'try' statement is used to catch and handle exceptions, preventing the program from crashing due to unhandled errors. The 'try' statement is typically used in conjunction with 'except', 'else', and 'finally' clauses to provide a flexible error-handling mechanism.

Basic Syntax
try:
    # Code block that might raise an exception
except ExceptionType1:
    # Code block to handle the specific exception
except ExceptionType2 as e:
    # Code block to handle the specific exception and get the exception object
else:
    # Code block to execute if no exception was raised
finally:
    # Code block that will always execute, regardless of whether an exception was raised

Detailed Examples
Catching a Specific Exception:
try:
    result = 10 / 0
except ZeroDivisionError:
    print("Cannot divide by zero")
# Output: Cannot divide by zero

Catching Multiple Exceptions:
try:
    number = int(input("Enter a number: "))
    result = 10 / number
except ValueError:
    print("Invalid input. Please enter a valid number.")
except ZeroDivisionError:
    print("Cannot divide by zero")
# If input is "a", output: Invalid input. Please enter a valid number.
# If input is 0, output: Cannot divide by zero

Getting the Exception Object:
try:
    result = 10 / 0
except ZeroDivisionError as e:
    print(f"Error occurred: {e}")
# Output: Error occurred: division by zero

Using the else Clause:
try:
    result = 10 / 2
except ZeroDivisionError:
    print("Cannot divide by zero")
else:
    print(f"Result is {result}")
# Output: Result is 5.0

Using the finally Clause:
try:
    result = 10 / 2
except ZeroDivisionError:
    print("Cannot divide by zero")
else:
    print(f"Result is {result}")
finally:
    print("This will always execute")
# Output: Result is 5.0
#         This will always execute

Common Exception Types
'Exception': Base class for all exceptions.
'ArithmeticError': Base class for all arithmetic errors.
'ZeroDivisionError': Raised when division or modulo by zero occurs.
'LookupError': Base class for all lookup errors.
'IndexError': Raised when a sequence index is out of range.
'KeyError': Raised when a dictionary key is not found.
'ValueError': Raised when a function receives an argument of the right type but inappropriate value.

Practical Example
try:
    file = open("example.txt", "r")
    content = file.read()
    print(content)
except FileNotFoundError:
    print("The file does not exist")
except IOError:
    print("An I/O error occurred")
else:
    print("File read successfully")
finally:
    if 'file' in locals():
        file.close()
        print("File closed")
# If "example.txt" does not exist:
# Output: The file does not exist
# If the file is read successfully:
# Output: (file content)
#         File read successfully
#         File closed
In this example, the 'try' block attempts to open and read a file. If the file does not exist or an I/O error occurs, the corresponding 'except' block handles the exception. The 'else' block executes if no exceptions are raised, and the 'finally' block ensures that the file is closed, whether an exception was raised or not.