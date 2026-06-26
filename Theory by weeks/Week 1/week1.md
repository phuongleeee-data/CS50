# Week 1: Introduction to C & Compilers

## 1. Core concepts

* **Source Code:** Lines of instructions written by humans using a programming languague (like C). It uses English vocabularies, making it readable, understandable, and maintainable.
* **Machine Code:** Patterns of `0` and `1` that the computer hardware actually understands and executes.
**Compiler:** A specialized piece of software that acts as a high-speed translator. It converts human-written source code into machine code.

___

## 2. Terminal Workflow

In a command-line environment, writing and running a program requires three essential steps:

1.  **Create and open a file to write code:**
    ```bash
    code hello.c
    ```
    *This command creates a new file named `hello.c` (must be lowercase with a `.c` extension) and opens the text editor.*

2.  **Compile the program:**
    ```bash
    make hello
    ```
    *This command calls the compiler. It reads the `hello.c` file, checks for syntax errors, and creates an executable file named `hello` (containing machine code, with no file extension).*

3.  **Execute the program:**
    ```bash
    ./hello
    ```
    *The `./` syntax tells the computer to "run the executable file named `hello` located right here in the current directory."*

---

## 3. "Hello, World" Structure

```c
// This is a comment. The compiler will ignore this line.

#include <stdio.h>

int main(void)
{
    printf("hello, world\n");
}

### Syntax Breakdown

*   `#include <stdio.h>`: Imports the Standard Input/Output library, which provides the tools needed for the `printf` function to work.
*   `int main(void)`: The starting point of every C program.
*   `printf`: A function used to output text to the screen.
*   `" "`: Double quotes enclose the exact text you want to output.
*   `\n`: A special character representing a "new line".
*   `;`: A mandatory semicolon at the end of every instruction. If missing, the compiler will throw an error and refuse to create the executable file.

---

### 4. CS50's Standard for "Good Code"

A good program must meet three core criteria:

1.  **Correctness:** The program accurately solves the problem and produces the expected results.
    *   *CS50 Tool:* Use the `check50` command to automatically check your code against various test cases.
2.  **Design:** The solution is logical, efficient, and avoids unnecessary repetition.
3.  **Style:** The code is visually clean, with proper spacing, accurate indentation, and clear comments (`//`) to make it easily readable and maintainable.
    *   *CS50 Tool:* Use the `style50` command to check for formatting mistakes and get styling suggestions.
