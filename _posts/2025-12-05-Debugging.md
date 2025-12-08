<h1>Debugging</h1>
<img src="images/1_kld8RKRjrouhdp4gWNFmBQ.jpg" alt="Debugging Image">

<h3>What is Debugging</h3>
Debugging is the process of finding and fixing errors (bugs) in a program. The term originated from Admiral Grace Hopper in 1947, when her colleagues found a moth in the Harvard computer and she said they were ‘debugging’ it.

<h3>Types of errors:</h3>
- **Syntax:** A mistake in the code rules
- **User:** A mistake made by the person using the program
- **Runtime:**Error that happens while the program is running
- **Logic:** When the code runs but gives the wrong result because of a mistake in thinking or calculations.

<h3>Steps to Debugging</h3>
There are 6 common steps taken when debugging code. 
- **Clarify the code’s purpose:** Understand what the code is supposed to do.
- **Identify the problem:** Determine what the code is doing incorrectly.
- **Locate the source:** Find the part of the code causing the error.
- **Identify the type of error:** Determine if it’s syntax, logic, runtime, or user error.
- **Fix the error:** Correct the mistake in the code.
- **Test the solution:** Run the program to make sure it works correctly.

<h2>Example 1</h2>
```python
text = "Hello, world, my name is "
count = 0

for char in text:
    if char == "":
       count += 1

print(count)
```
In order to debug the code for this example we follow the steps to debugging. 
<h4>Step 1: Clarifying the code's purpose</h4>
This code is intended to count how many spaces are in a given string.

<h4>Step 2: Identify the problem</h4>
When the code is run, the spaces in the text are not being counted. 

<h4>Step 3:Locate The Soure</h4>
When looking at the code, the error seems to be in the if statement. It checks whether char == a space, but char is never actually a space, so the count never increases.

<h4>Step 4: Identify the Type of Error</h4>
This is a logic error because the code doesn’t give the correct result due to a problem in the reasoning.

<h4>Step 5: Fix the error</h4>
To fix this error, we need to include a space inside the quotes in the condition, like char == " ".

This would result in the code being:
```python
text = "Hello, world, my name is "
count = 0

for char in text:
    if char == " ":
       count += 1

print(count)
```

<h4>Step 6: Test the solution:</h4>
As a result, the code ran and reported that there are 5 spaces in the text.

<h2>Example 2</h2>
```python
print("give me a number")
n = input()

for num in range(1, n):
    if num % 2 < 0:
        print(num, "is even.")
    else:
        print(num, "is odd.")
``` 
<h4>Step 1: Clarifying the code's purpose</h4>
This code is intended to determine if numbers 1 to n are even or odd 


<h4>Step 2: Identify the problem</h4>
When the code is run, the spaces in the text are not being counted and an error occurs due to the input being a string. 

<h4>Step 3:Locate The Soure</h4>
The problem in this code is that the if statement checks if num % 2 < 0 which is not the right way to check even numbers. Also, the input() function returns a string, and not an integer, and the current range does not include the input number itself because of how range works.

<h4>Step 4: Identify the Type of Error</h4>
In this example, there are two kinds of errors. A runtime error because the input() is only a string input function and a logic error because num % 2 < 0 incorrectly checks for even numbers.

<h4>Step 5: Fix the error</h4>
In order to fix the code the if statement has to be set to == 0 and not less than 0. Additionally for the input it has to be an integer. Lastly in order to include the input for odd or even of the n number you add n + 1 to the range to include it.


This would result in the code being:
```python
print("Give me a number")
n = int(input())

for num in range(1, n + 1): 
    if num % 2 == 0:
        print(num, "is even.")
    else:
        print(num, "is odd.")
```

<h4>Step 6: Test the solution:</h4>
As a result, if you input the number 3, the code will output: 1 is odd, 2 is even, and 3 is odd.

<h2>Example 3</h2>
```python
num = int(input("Enter an integer: "))

if num < -1:
  print("No negative numbers.")
else:
  result = 1
  for i in range(1, num):
    result *= i   

  print("Factorial of " + num + "is" + result)
```
<h4>Step 1: Clarifying the code's purpose</h4>
This code is intended to ask user to enter the correct password but only give them 3 attempts


<h4>Step 2: Identify the problem</h4>
When the code is run, an error called TypeError appears. 

<h4>Step 3:Locate The Soure</h4>
The main issue was that the print statement tried to combine integers and strings using +. The second issue was that the range didn’t include the input number, so the factorial was incomplete. The last issue was that the if statement only checked if the number was less than -1, so -1 would still be allowed even though it’s negative.

<h4>Step 4: Identify the Type of Error</h4>
In this example, there are two kinds of errors. A runtime error because it tries to combine integers and strings with +, and logic errors because the range doesn’t include the input number and the negative check is incorrect.

<h4>Step 5: Fix the error</h4>
To fix the first issue, integers need to be combined with strings using commas instead of +. Then 1 must be added to num so the input number is included in the range. Lastly, the condition num < -1 needed to be changed to num < 0 because anything less than 0 is negative.

This would result in the code being:
```python
num = int(input("Enter an integer: "))

if num < 0:
    print("No negative numbers.")
else:
    result = 1
    for i in range(1, num + 1):
        result *= i

    print("Factorial of", num, "is", result)
```

<h4>Step 6: Test the solution:</h4>
As a result, if you input the number 4, the code will output that the factorial of 4 is 24. If you input the number -1, the code will output that no negative number can be calculated.

<h2>Example 4</h2>
```python
attempts = 0
correct_password = "secret"

while True:
    password = input("Enter your password: ")
    attempts += 1

    if password == "incorrect_password":
        print("Correct password!")
    else:
        print("Incorrect password")

    if attempts > 3:
        print("Too many attempts")
        break
```
<h4>Step 1: Clarifying the code's purpose</h4>
This code is intended to ask user to enter the correct password but only give them 3 attempts


<h4>Step 2: Identify the problem</h4>
When the code is run, the password "secret" does not work and after more than 3 attempts the code says "Too many attempts".

<h4>Step 3:Locate The Soure</h4>
The main issue is that the code doesn’t stop after 3 attempts. Second, even when the correct password is entered, it keeps asking for input. Third, attempts aren’t counted correctly for wrong passwords, and finally, the input should be set equal to the correct_password variable instead of the string "incorrect_password".

<h4>Step 4: Identify the Type of Error</h4>
In this example, there are two kinds of errors. A runtime error because the input() is only a string input function and a logic error because num % 2 < 0 incorrectly checks for even numbers.

<h4>Step 5: Fix the error</h4>
To fix the first issue, the condition should be if attempts >= 3 to stop after 3 tries. To fix the second issue, add a break after printing "Correct password!" so the loop stops when the correct password is entered. To fix the third issue, the attempts check for too many tries should only happen when the password is incorrect meaning it should be indented inside the else statement. Finally, the input should be set equal to the correct_password variable, not the string "incorrect_password".  

This would result in the code being:
```python
attempts = 0
correct_password = "secret"

while True:
    password = input("Enter your password: ")
    attempts += 1

    if password == correct_password:
        print("Correct password!")
        break
    else:
        print("Incorrect password")
        if attempts >= 3:
            print("Too many attempts")
            break
```

<h4>Step 6: Test the solution:</h4>
As a result, if the correct password is entered, the program prints "Correct password!" and stops immediately. If the password is entered incorrectly, it prints "Incorrect password". After three incorrect attempts, it prints "Too many attempts" and stops.

<h3>Conclusion</h3>
In conclusion, debugging is an important part of coding because it allows us to identify and fix errors in our programs. By using the six-step debugging process to solve these examples, I was able to learn how to solve common errors in a more efficient and structured way. This process helped me understand the different types of errors, such as syntax errors, user errors, runtime errors, and logic errors. As a result, I can now apply this knowledge to future coding projects, solving errors in my code in a more structured manner.

 