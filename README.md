# InputHandler.py

**Author:** Maximus Barraza (Github: X86-Point5)
**Version:** 1.0.0
**Date:** 2025-05-15

## Description

`InputHandler.py` is a Python script that provides a range of functions meant for dealing with console inputs safely and effectively. It focuses on validating user input for common data types like integers, floating-point numbers, single characters, and dates.

## Features

This script offers the following functionalities:

* **Integer Validation:**
    * Prompts the user for integer input.
    * Validates that the input is an integer.
    * Includes optional bounds checking (inclusive or exclusive).
* **Floating-Point Validation:**
    * Prompts the user for floating-point (decimal) input.
    * Validates that the input is a float.
    * Includes optional bounds checking (inclusive or exclusive).
* **Character Validation:**
    * Prompts the user for a single character input.
    * Takes the first character of the user's input.
    * Optionally validates the input against a provided string of allowed characters.
    * Optionally converts the input character to uppercase.
* **Date Validation:**
    * Prompts the user for a date in MM/DD/YYYY format.
    * Validates the string for correct date format and valid date values.
    * Can return the validated date as a string or as a tuple of integers (month, day, year).

## Requirements

* Python 3.x
* The following Python standard libraries are used:
    * `datetime`: For validating date input.

## How to Use

1.  **Ensure Python is Installed:** Make sure you have Python 3.x installed on your system.
2.  **Save the Script:** Save the `InputHandler.py` script to your desired location.
3.  **Import in Your Project:** You can import the `InputHandler` module into your own Python scripts to use its functions:

    import InputHandler

    # Example: Get a valid integer from the user
    age = InputHandler.input_integer(prompt="Please enter your age (1-120): ", lower_bound=1, upper_bound=120)
    if age is not None: # Assuming functions might return None or raise error on unrecoverable input issues, though current ones loop
        print(f"Entered age: {age}")

    # Example: Get a character for a menu choice
    # (as per your initial request for input_char's purpose)
    choice_options = "ABCX"
    user_choice = InputHandler.input_char(
        prompt=f"Enter your choice ({'/'.join(list(choice_options))}): ",
        valid_chars=choice_options,
        to_caps=True
    )
    print(f"You selected: {user_choice}")

## Functions Overview

Here's a brief overview of the main functions available in `InputHandler.py`:

* `input_integer(prompt, lower_bound, upper_bound, inclusion)`: Prompts for and validates an integer within specified bounds.
* `input_float(prompt, lower_bound, upper_bound, inclusion)`: Prompts for and validates a float within specified bounds.
* `input_char(prompt, valid_chars, to_caps)`: Prompts for and validates a single character, optionally against a set of valid characters and with case conversion.
* `input_string_date(prompt)`: Prompts for and validates a date string, returning it in MM/DD/YYYY format.
* `input_tuple_date(prompt)`: Prompts for a date, validates it, and returns its components (month, day, year) as a tuple of integers.

For detailed information on arguments, return values, and specific error handling for each function, please refer to the docstrings within the `InputHandler.py` script.

## License

This software is free to use, modify, and distribute for any purpose. Go wild.
