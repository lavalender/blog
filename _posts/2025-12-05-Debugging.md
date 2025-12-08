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
- **Clarify the code’s purpose:** What is the code trying to accomplish?
- **Identify the problem:** Figure out what isn’t working.
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
This code is intended to count how many spaces are in a given string
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



 