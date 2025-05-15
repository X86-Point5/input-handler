# InputHandler.py

**Author:** Maximus Barraza (Github: X86-Point5)
**Version:** 1.0.0
**Date:** 2025-05-15

## Overview

`InputHandler.py` is a Python module that provides a collection of functions designed to safely and robustly handle various types of console input from users. It simplifies the process of prompting users for input and validating that input against specified criteria, such as data type, bounds, and allowed characters.

The primary purpose of this module is to be included in other Python projects via an `import` statement, allowing developers to easily call its functions whenever they need to securely gather information from the user via the console.

## Features

* Validates Integer input, including bounds checking (inclusive or exclusive).
* Validates Floating Point input, including bounds checking (inclusive or exclusive).
* Validates Single Character input, with an option to restrict to a specific set of characters and convert to uppercase.
* Validates Date input, ensuring it conforms to the MM/DD/YYYY format.
* Provides options to return dates as either a string or a tuple of integers (month, day, year).

## How to Use

To use the functions in this module, simply import it into your Python script:

```python
import InputHandler
Then, you can call the desired functions as needed.

Functions
Here's a breakdown of the available functions:

input_integer(prompt: str = "\n\tEnter an integer: ", lower_bound: int = 0, upper_bound: int = 32767, inclusion: bool = True) -> int
Prompts the user to enter an integer and validates it against specified bounds.

prompt: The message displayed to the user.
lower_bound: The lower limit for the integer value.
upper_bound: The upper limit for the integer value.
inclusion: If True (default), the bounds are inclusive (e.g., lower_bound <= value <= upper_bound). If False, bounds are exclusive (e.g., lower_bound < value < upper_bound).
Returns: The validated integer entered by the user.
Example:

Python

age = InputHandler.input_integer(prompt="Please enter your age: ", lower_bound=1, upper_bound=120)
print(f"Your age is: {age}")

quantity = InputHandler.input_integer(prompt="Enter quantity (1-99): ", lower_bound=1, upper_bound=99)
print(f"Quantity set to: {quantity}")
input_float(prompt: str = "\n\tEnter a decimal value: ", lower_bound: float = 0.0, upper_bound: float = 32767.0, inclusion: bool = True) -> float
Prompts the user to enter a float (decimal number) and validates it against specified bounds.

prompt: The message displayed to the user.
lower_bound: The lower limit for the float value.
upper_bound: The upper limit for the float value.
inclusion: If True (default), the bounds are inclusive. If False, bounds are exclusive.
Returns: The validated float entered by the user.
Example:

Python

price = InputHandler.input_float(prompt="Enter the price: $", lower_bound=0.01, upper_bound=1000.00)
print(f"The price is: {price:.2f}")
input_char(prompt: str = "\n\tEnter a character: ", valid_chars: str = "", to_caps: bool = True) -> str
Prompts the user to enter a single character. It can optionally validate the character against a list of allowed characters and convert it to uppercase. This function is particularly useful for selection prompts (e.g., "Choice A, Choice B, Choice C. Enter your choice:").

prompt: The message displayed to the user.
valid_chars: A string containing all valid characters. If empty (default), any character is accepted.
to_caps: If True (default), the input character and valid_chars are converted to uppercase for comparison, and the returned character will be uppercase.
Returns: The validated single character.
Example:

Python

# Example for a menu choice
options = "ABCX"
choice = InputHandler.input_char(
    prompt=f"Choice A. Choice B. Choice C. Choice X. \nEnter your choice [{options}]: ",
    valid_chars=options,
    to_caps=True
)
print(f"You selected: {choice}")

confirmation = InputHandler.input_char(prompt="Continue? (Y/N): ", valid_chars="YN")
print(f"Confirmation: {confirmation}")
input_string_date(prompt: str = "\n\tEnter a data in the format (MM/DD/YYYY): ") -> str
Prompts the user to enter a date string in MM/DD/YYYY format and validates it.

prompt: The message displayed to the user.
Returns: The validated date string in MM/DD/YYYY format.
Example:

Python

birth_date_str = InputHandler.input_string_date(prompt="Enter your birth date (MM/DD/YYYY): ")
print(f"Birth date entered: {birth_date_str}")
input_tuple_date(prompt: str = "\n\tEnter a data in the format (MM/DD/YYYY): ") -> tuple[int, int, int]
Prompts the user for a date string in MM/DD/YYYY format, validates it, and returns its components (month, day, year) as a tuple of integers.

prompt: The message displayed to the user.
Returns: A tuple containing the month, day, and year as integers (e.g., (5, 15, 2025) for May 15, 2025).
Example:

Python

event_date_tuple = InputHandler.input_tuple_date(prompt="Enter the event date (MM/DD/YYYY): ")
month, day, year = event_date_tuple
print(f"Event is on: Month {month}, Day {day}, Year {year}")
Error Handling
All functions include error handling for invalid input types (e.g., text where a number is expected) and out-of-bounds values. Users will be re-prompted with an error message until valid input is provided.

License
This software is free to use, modify, and distribute for any purpose. Go wild.
