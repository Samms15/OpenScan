# OpenScan: An Efficient Open-Source Alternative to Java's Scanner

**OpenScan is an Open-Source Implementation of Scanner Class in Java but more Efficient.**

[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)
[![Java](https://img.shields.io/badge/Java-v8%2B-orange.svg)](https://www.java.com/en/download/)
[![Build Status](https://img.shields.io/badge/build-passing-brightgreen)](https://github.com/Chill-Astro/OpenScan/actions)

## Introduction

`OpenScan` is a robust, efficient, and versatile Java library designed to replace the standard `Scanner` class for handling user input. While the built-in `Scanner` class is useful for basic tasks, `OpenScan` offers significant advantages in terms of performance, error handling, and flexibility, especially when dealing with large inputs or complex data formats.

## Key Features and Advantages

*   **Enhanced Performance:**
    *   Leverages `BufferedReader` for efficient line-by-line reading.
    *   Uses buffering to reduce the number of physical read operations, resulting in faster I/O.
*   **Line-Oriented Input:**
    *   `nextLine()` method efficiently reads entire lines, unlike `Scanner`'s token-based approach.
*   **Robust Error Handling:**
    *   Explicitly throws `NoSuchElementException` when input is exhausted.
    *   Throws `NumberFormatException` for invalid numeric input.
    *   Throws `RuntimeException` (wrapping `IOException`) for I/O errors.
    *   Handles empty tokens when `nextChar()` is called.
*   **Automatic Resource Management:**
    *   Implements `AutoCloseable`, allowing for use with try-with-resources, ensuring proper resource cleanup.
*   **Comprehensive Data Type Support:**
    *   Directly reads various data types: `int`, `long`, `double`, `float`, `boolean`, `char`, `short`, `byte`.
*   **Array and List Reading:**
    *   `nextIntArray()`, `nextLongArray()`, `nextDoubleArray()` read multiple values into arrays.
    *   `nextStringList()` reads all tokens on a line into a `List<String>`.
* **Complete Data Loading:**
    * `readAllInts()`, `readAllDoubles()`, `readAllLongs()`, `readAllStrings()` reads all the available data from the input stream.
*   **Input Control:**
    *   `skipLines()` to efficiently skip over unwanted lines of input.
*   **Clear tokenizer**
    * `nextLine()` method clears the tokenizer by assigning null.
*   **Robust Checking**
    * `hasNext()` method checks properly if the new token is available.
* **Detailed Exception Handling:**
    * It handles all the exceptions clearly.

## Getting Started

1.  **Download:** Clone or download the `OpenScan.java` file from this repository.
2.  **Include:** Add the `OpenScan.java` file to your Java project.
3.  **Create Object:** Create an Object from this Code:

    ```java
    OpenScan sc = new OpenScan();
    ```
## Usings
 
Assuming that sc is your OpenScan object,

 - sc.next() reads the next token from the input.
 - sc.nextInt() reads the next token as an integer.
 - sc.nextDouble() reads the next token as a double.
 - sc.nextLine() reads the next line of text.
 - sc.nextChar() reads the first character of the next token.
 - sc.nextBoolean() reads the next token as a boolean.
 - sc.nextShort() reads the next token as a short.
 - sc.nextByte() reads the next token as a byte.
 - sc.nextLong() reads the next token as a long.
 - sc.nextFloat() reads the next token as a float.
 - sc.nextStringList() reads all remaining tokens from the current line as Strings.
 - sc.nextIntArray(int count) reads multiple integers from the current line.
 - sc.nextLongArray(int count) reads multiple longs from the current line.
 - sc.nextDoubleArray(int count) reads multiple doubles from the current line.
 - sc.readAllInts() reads all integers from the input until the end of input.
 - sc.readAllDoubles() reads all doubles from the input until the end of input.
 - sc.readAllLongs() reads all longs from the input until the end of input.
 - sc.readAllStrings() reads all strings from the input until the end of input.
 - sc.skipLines(int linesToSkip) skips a specified number of lines from the input.
 - sc.hasNext() checks if there is another token available.
 - sc.close() closes the underlying BufferedReader.
