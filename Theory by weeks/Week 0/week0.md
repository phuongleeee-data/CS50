# Week 0: Foundation
## 1. The Core Model of Computer Science
Computer science and programming are fundamentally about **Problem Solving**. The process follows a straightforward model:

**Input** ➔ **Black Box** ➔ **Output**

* **Input:** The raw data or the problem you need to solve.
* **Output:** The desired result or solution.
* **Black Box:** The logic, algorithms, and code we design to transform the Input into the Output.

## 2. The Language of Computers: Binary
To design the "Black Box", we must understand how computers communicate. At the physical level, a computer is essentially billions of tiny electrical switches (transistors).

Each switch has only two possible states:
* **Off** = `0`
* **On** = `1`

This counting system, which uses only 0s and 1s, is called the **Binary System (Base-2)**. A single 0 or 1 is known as a **Bit** (Binary Digit).

---

## 3. How Computers Count (The "Lightbulb" Rule)
Instead of counting from 0 to 9 like the human Decimal (Base-10) system, Binary operates on powers of 2. Reading from right to left, each "lightbulb" (Bit) represents double the value of the one before it.

For example, with 4 Bits: **8 | 4 | 2 | 1**

To represent the number **10**, we turn on the '8' bulb and the '2' bulb:
* **8** (On) ➔ `1`
* **4** (Off) ➔ `0`
* **2** (On) ➔ `1`
* **1** (Off) ➔ `0`

**Result:** The decimal number 10 = `1010` in binary.

## 4. What is a Byte?
Computers typically group 8 Bits together to form **1 Byte**. 
* Example: `00000101` represents the number 5.
* The maximum value a single Byte (8 Bits) can represent is `11111111` (which equals 255). 

*Note: Understanding binary is the first step to understanding how computers store everything. Text, images, and audio are all ultimately stored as massive sequences of 0s and 1s.*

# Data Representation: ASCII
## 1. The challenge of text
We know that computer only understands binary numbers (0s and 1s). So, how do they process, store, and display text messages, numbers, names, or codes?

The solution is agreed upon a standard: a dictionary that maps specific numbers to specific characters.

## 2. What is ASCII?
**ASCII** (American Standard Code for Information Interchange) is the most widely used standard for character encoding. It ensures that when one computer sends a specific number, another computer translates it into the exact same letter.

* In ASCII, every uppercase letter, lowercase letter, number (0-9), and punctuation mark is assigned a unique decimal number.
* Example:
    * The letter **A** is represented by the number **65** (which is `01000001` in binary).
    * The letter **B** is **66**.
    * The letter **a** (lowercase) is **97**.

## 3. How a Message is Sent
When you send a text message saying `"CAT"`, the computer's "Black Box" processes it as follows:
1. Breaks the word into individual characters: `C`, `A`, `T`.
2. Converts characters to ASCII decimal numbers: `67`, `65`, `84`.
3. Converts decimals to binary to transmit over hardware: `01000011`, `01000001`, `01010100`.

## 4. Beyond ASCII: Unicode
Standard ASCII uses 7 or 8 bits, meaning it can only represent 128 to 256 unique characters. This is enough for English, but not for the thousands of characters in languages like Chinese, Japanese, or Arabic, nor for emojis (😂, 🚀).

To solve this, the world moved to **Unicode** (which can use 16 to 32 bits per character), allowing computers to represent millions of unique characters and emojis across all languages.

# Data Representation: Colors, Images & Video
## 1. The Power of Context
Data is just data. A sequence of 0s and 1s has no inherent meaning. **The meaning of data depends entirely on the "Black Box" (the software) reading it.**

For example, the numbers `72`, `73`, and `33`:
* To a Text Editor, using ASCII: It translates to `"HI!"`.
* To an Image Viewer, using RGB: It translates to a specific color pixel (a light shade of yellow).

## 2. The RGB Color Model
Screens display colors by mixing three primary light colors: **Red, Green, and Blue (RGB)**.
* Each color channel uses 1 Byte (8 bits), meaning its value ranges from `0` (completely off) to `255` (maximum brightness).
* Combining these three channels (3 Bytes per pixel) allows computers to display over 16 million different colors (256 x 256 x 256).
* Example: `RGB(72, 73, 33)` means a mix of Red at level 72, Green at 73, and Blue at 33.

## 3. Images, Video, and Music
Everything digital scales up from these basic building blocks:
* **Images:** A grid of millions of tiny dots called **pixels**. Each pixel is represented by 3 Bytes (RGB). A 10x10 image has 100 pixels, requiring 300 Bytes of memory just for the colors.
* **Videos:** Simply a sequence of images (frames) played back very quickly (e.g., 30 or 60 frames per second), combined with an audio track.
* **Music/Audio:** Sound waves are measured (sampled) thousands of times per second. Each measurement is stored as a binary number.

*Note: Because raw images and videos take up a massive amount of memory, computer scientists use "Algorithms" to compress (shrink) this data so it can be sent quickly over the internet (e.g., JPEG for images, MP4 for video).*

# Algorithms & Big O Notation
## 1. What is an Algorithm?
In computer science, an **Algorithm** is simply a step-by-step set of instructions used to solve a specific problem. 
It is the logic inside the "Black Box" that transforms Input into Output.

## 2. The Phone Book Problem
Goal: Find the name "Mike" in a 1000-page phone book.

* **Linear Search (Algorithm 1):** Read page by page from start to finish.
* **Algorithm 2:** Search two pages at a time.
* **Binary Search (Algorithm 3):** Open the middle of the book. If "Mike" is in the earlier half, discard the right half. Repeat this process, cutting the problem in half each time until "Mike" is found.

**Crucial Prerequisite:** Binary search *only* works if the data is already **sorted** (e.g., in alphabetical order).

## 3. Big-O Notation (Efficiency)
**Big-O** is a way to describe the efficiency of an algorithm. It measures the maximum number of steps required in the worst-case scenario as the size of the problem (n) grows.

* **O(n):** Linear time. (e.g., Linear Search - taking up to 1000 steps for 1000 pages).
* **O(n/2):** Half-linear time.
* **O(log n):** Logarithmic time. (e.g., Binary Search - taking only about 10 steps for 1000 pages, because the data is halved each step).

*Note: Writing good algorithms is about making rational, optimized decisions to save processing time and computer memory.*

# Pseudocode & Programming Fundamentals
## 1. What is Pseudocode?
**Pseudocode** consists of human-readable instructions that describe the steps of an algorithm. It is the bridge between human logic and machine code. 
* Writing pseudocode allows you to map out the logic and solve the problem *before* worrying about the exact syntax of a programming language.
* It serves as excellent documentation for others to understand your thought process.

## 2. The Four Building Blocks of Programming
Every algorithm is built from these core concepts:

1. **Functions:** Actions or verbs. Telling the computer *what* to do. (e.g., `Pick up`, `Open`, `Call`).
2. **Conditionals:** Decision-making branches that dictate the flow of the program. (e.g., `If`, `Else if`, `Else`).
3. **Boolean Expressions:** Questions or statements that evaluate to exactly `True` or `False`. (e.g., `Is the person on this page?`).
4. **Loops:** Instructions to repeat a set of actions until a specific condition is met. (e.g., `Go back to line 3`).

## 3. The Binary Search Pseudocode
Here is how the phone book problem translates into pseudocode:

```text
1  Pick up phone book
2  Open to middle of phone book
3  Look at page
4  If person is on page
5      Call person
6  Else if person is earlier in book
7      Open to middle of left half of book
8      Go back to line 3
9  Else if person is later in book
10     Open to middle of right half of book
11     Go back to line 3
12 Else
13     Quit
