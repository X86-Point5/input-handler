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

import InputHandler

Then, you can call the desired functions as needed.
## Functions

Here's a breakdown of the available functions:

### `input_integer(prompt: str = "\n\tEnter an integer: ", lower_bound: int = 0, upper_bound: int = 32767, inclusion: bool = True) -> int`

Prompts the user to enter an integer and validates it against specified bounds.

* **`prompt`**: The message displayed to the user.
* **`lower_bound`**: The lower limit for the integer value.
* **`upper_bound`**: The upper limit for the integer value.
* **`inclusion`**: If `True` (default), the bounds are inclusive (e.g., `lower_bound <= value <= upper_bound`). If `False`, bounds are exclusive (e.g., `lower_bound < value < upper_bound`).
* **Returns**: The validated integer entered by the user.

**Example:**

age = InputHandler.input_integer(prompt="Please enter your age: ", lower_bound=1, upper_bound=120)
print(f"Your age is: {age}")

quantity = InputHandler.input_integer(prompt="Enter quantity (1-99): ", lower_bound=1, upper_bound=99)
print(f"Quantity set to: {quantity}")
