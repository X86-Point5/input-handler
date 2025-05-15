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
