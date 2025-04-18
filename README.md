# OpenScan: An Efficient Open-Source Alternative to Java's Scanner

**OpenScan is an Open-Source Implementation of Scanner Class in Java but more Efficient.**

[![License](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Java](https://img.shields.io/badge/Java-v8%2B-orange.svg)](https://www.java.com/en/download/)
[![Build Status](https://img.shields.io/badge/build-passing-brightgreen)](https://github.com/your-username/OpenScan/actions) <!-- Replace 'your-username' with your actual GitHub username -->

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
3.  **Import:** Import the class in your Java code:

    ```java
    import OpenScan;
    ```

## Usage Examples

Here are some examples demonstrating the features of `OpenScan`:

```java
import OpenScan;
import java.util.Arrays;
import java.util.List;

public class Main {
    public static void main(String[] args) {
        try (OpenScan scan = new OpenScan()) {
            // Basic input reading
            System.out.print("Enter your name: ");
            String name = scan.next();
            System.out.println("Hello, " + name + "!");

            System.out.print("Enter an integer: ");
            int num = scan.nextInt();
            System.out.println("You entered: " + num);

            // Reading a line
            System.out.print("Enter a line of text: ");
            String line = scan.nextLine();
            System.out.println("You typed: " + line);

            // Reading an array of integers
            System.out.println("Enter 3 integers on one line (e.g., 1 2 3):");
            int[] numbers = scan.nextIntArray(3);
            System.out.println("Integers: " + Arrays.toString(numbers));

            // Reading a list of strings
            System.out.println("Enter some words on one line (e.g., apple banana orange):");
            List<String> words = scan.nextStringList();
            System.out.println("Words: " + words);
            
            // Skipping lines
            System.out.println("Enter 2 lines to skip:");
            scan.skipLines(2);
            System.out.println("Skipped 2 lines");
            
            // Read all the integers
            System.out.println("Enter some integers: ");
            List<Integer> allInts = scan.readAllInts();
            System.out.println("All Integers : " + allInts);

        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}

