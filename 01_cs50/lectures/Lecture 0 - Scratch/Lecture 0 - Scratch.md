# Computer Science - CS50x 2026: Lecture 0 - Scratch

────────────────────────────────────

**Video:** [CS50x 2026 - Lecture 0 - Scratch](https://youtu.be/UuIEbpQms8o)
**Instructor:** David J. Malan
**Course:** CS50: Introduction to the Intellectual Enterprises of Computer Science and the Arts of Programming

────────────────────────────────────

## Overview

This lecture serves as the foundational introduction to computer science, shifting the focus from simple programming to the broader art of problem-solving. Professor Malan introduces the concept of computational thinking, explores how computers represent information using binary, and demonstrates the transition from high-level logic to visual programming using Scratch.

## Key Topics

### The Role of Artificial Intelligence in Programming [00:02:27]

- **AI as a Tool:** AI (like ChatGPT, Claude, and Gemini) is changing programming by helping find bugs, suggest features, and solve problems.
- **Human as the Pilot:** Despite AI's capabilities, the human remains the "conductor" or "pilot." The goal of CS50 is to teach students how to think and master these tools, not just memorize syntax.
- **The Calculator Analogy:** Just as calculators didn't make learning addition obsolete, AI doesn't remove the need to understand foundational computer science principles.

### Simple Python Chatbot Example [00:06:01]

The instructor demonstrates how modern APIs allow for powerful functionality in very few lines of code.

```python
from openai import OpenAI

# Initialize the client
client = OpenAI()

# Get a response from the model
response = client.chat.completions.create(
    model="gpt-4o",
    messages=[{"role": "user", "content": "In one sentence, what is CS50?"}]
)

# Print the result
print(response.choices[0].message.content)
```

### Binary and Information Representation [00:15:17]

- **Unary vs. Binary:** The lecture contrasts unary systems (counting on fingers/tallies) with binary (base-2), which computers use. **For more details:** [Unary, Binary, and Ternary Operators in JavaScript](https://www.freecodecamp.org/news/unary-binary-ternary-operators-javascript/).
- **Bits and Transistors:** A **bit** (binary digit) is the smallest unit of information, representing a 0 or 1. Physically, these are implemented via **transistors** acting as electronic switches.
- **Counting in Binary:** By using multiple bits, computers can represent larger numbers.
  - 1 bit can represent 2 values (0, 1).
  - 3 bits can represent 8 values (0-7).
  - $n$ bits can represent $2^n$ values.

![alt text](./images/image.png)

> fig 2^n

```text
8 | 4 | 2 | 1
------------------
0 | 0 | 0 | 1  -> 1
0 | 0 | 1 | 0  -> 2
0 | 0 | 1 | 1  -> 3
0 | 1 | 0 | 0  -> 4
0 | 1 | 0 | 1  -> 5
0 | 1 | 1 | 0  -> 6
0 | 1 | 1 | 1  -> 7
1 | 0 | 0 | 0  -> 8
```

> In reality unit of measure is not bit but **byte (8 bits)** which can represent 256 values (0-255).

- That's why computer used to show 256 colors in old days.

> Common convention now a day is to use **32 bits** for memory addressing (4 billion values or 2 billion values).

### Data Representation: Text, Images, and Sound [00:20:02]

- **ASCII & Unicode:** Standardized mappings that assign numbers to characters. For example, 'A' is 65 in ASCII. Unicode expands this to include emojis and global characters.

```text
128 | 64 | 32 | 16 | 8 | 4 | 2 | 1
---------------------------------------
0   | 1  | 0  | 0  | 0 | 0 | 0 | 1  -> 65 (A)
0   | 1  | 0  | 0  | 0 | 0 | 1 | 0  -> 66 (B)
0   | 1  | 0  | 0  | 0 | 0 | 1 | 1  -> 67 (C)
0   | 1  | 0  | 0  | 0 | 1 | 0 | 0  -> 68 (D)
0   | 1  | 0  | 0  | 0 | 1 | 0 | 1  -> 69 (E)
0   | 1  | 0  | 0  | 0 | 1 | 1 | 0  -> 70 (F)
0   | 1  | 0  | 0  | 0 | 1 | 1 | 1  -> 71 (G)
0   | 1  | 0  | 0  | 1 | 0 | 0 | 0  -> 72 (H)

```

![ASCII](<./images/CS50x 2026 - Lecture 0 - Scratch 32-48 screenshot.png>)

- **Text Casing** The uppercase and lowercase letters are represented by different numbers in ASCII. They are 32 apart.

```text
128 | 64 | 32 | 16 | 8 | 4 | 2 | 1
---------------------------------------
0   | 1  | 0  | 0  | 0 | 0 | 0 | 1  -> 65 (A)
0   | 1  | 1  | 0  | 0 | 0 | 1 | 0  -> 97 (a)
```

> Text casing can be changed by flipping a single bit (32 column).

- **Activity Spell BOW:**

```text
128 | 64 | 32 | 16 | 8 | 4 | 2 | 1
---------------------------------------
0   | 1  | 0  | 0  | 0 | 0 | 0 | 1  -> B (66)
0   | 1  | 0  | 0  | 0 | 0 | 1 | 0  -> O (79)
0   | 1  | 0  | 0  | 1 | 1 | 1 | 1  -> W (87)
```

![special characters](<./images/CS50x 2026 - Lecture 0 - Scratch 41-14 screenshot.png>)

> without ASCII and Unicode, we would not be able to represent text, emojis, or symbols in computers. They are fundamental to how we interact with digital devices.

- **ASCII & Unicode:** ASCII uses 7 bits (128 characters), while Unicode uses 16 bits, 24 bits, up to 32 bits, allowing for over a million characters, including emojis and symbols from various languages.
- ASCII is a subset of Unicode, meaning the first 128 characters of Unicode are the same as ASCII.
- ASCII is not only one system world used it one of the earliest but we have moved to Unicode now a day.

```text
 2^31 | 2^30 | 2^29 | 2^28 | 2^27 | 2^26 | 2^25 | 2^24 | 2^23 | 2^22 | 2^21 | 2^20 | 2^19 | 2^18 | 2^17 | 2^16 | 2^15 | 2^14 | 2^13 | 2^12 | 2^11 | 2^10 | 2^9 | 2^8 | 2^7 | 2^6 | 2^5 | 2^4 | 2^3 | 2^2 | 2^1 | 2^0
```

11110000100111111100110001000010 :arrow_right: 4036991106 :arrow_right: (UTF-8 encoding of '😂')

> Seeing emoji in different platforms can be different because of different rendering of Unicode characters.

- **RGB Color Model:** Images are represented as **pixels**. Each pixel's color is a combination of Red, Green, and Blue (RGB) values, typically ranging from 0 to 255.
- **Digital Sound:** Sound is represented by sampling vibrations and converting those intensities into sequences of numbers.
  > Frequency, Pitch, and Volume are the three properties of sound.

### Algorithms and Pseudocode [00:12:28]

![computerFlow(input-process-output)](./images/image-1.png)

> The secret sauce in between is algorithm.
>
> Code is just implementation (language a computer understands) of algorithm.

- **Definition:** An **algorithm** is a step-by-step procedure for solving a problem.
- **Correctness and Efficiency:** An algorithm must not only produce the right answer but do so in an optimized way (e.g., searching a phonebook by splitting it in half rather than page-by-page).

![alt text](<./images/CS50x 2026 - Lecture 0 - Scratch 1-3-51 screenshot.png>)

- **Pseudocode:** A human-readable version of code that focuses on logic rather than strict syntax.

![alt text](<./images/CS50x 2026 - Lecture 0 - Scratch 1-10-22 screenshot.png>)

```c
#include <stdio.h>
int main(void){
    printf( "hello, world\n");
}
```

> Computer not only standardize information (numbers, text, images, sound) but also the standardized the instruction set (algorithms).

python :arrow_right: C :arrow_right: Assembly :arrow_right: Machine code :arrow_right: Transistors

## Technical Content: Scratch [01:14:09]

────────────────────────────────────

Scratch is a visual programming language developed by MIT that allows students to learn fundamental programming concepts—like functions, loops, and conditions—by dragging and dropping blocks instead of typing code. This eliminates syntax errors and allows the focus to remain on logic and problem-solving.

### Core Programming Concepts in Scratch

The instructor maps common programming "building blocks" to specific visual components in Scratch:

| Concept                 | Programming Definition                                    | Scratch Implementation                                   |
| :---------------------- | :-------------------------------------------------------- | :------------------------------------------------------- |
| **Functions**           | Actions or verbs that perform a specific task.            | Blocks like `say "hello"` or `move 10 steps`.            |
| **Arguments**           | Inputs provided to functions to change their behavior.    | The text `"hello"` or the number `10` inside the blocks. |
| **Loops**               | A structure that repeats a set of instructions.           | The `forever` or `repeat` C-shaped blocks.               |
| **Variables**           | Places to store information that can change.              | A custom block created in the "Variables" category.      |
| **Conditions**          | Logic that branches the code (If this, then that).        | The `if` block combined with a diamond-shaped sensor.    |
| **Boolean Expressions** | A question that results in a **True** or **False** value. | Diamond-shaped blocks like `touching mouse-pointer?`.    |
| **Events**              | Triggers that start a sequence of code.                   | The `when green flag clicked` block.                     |

### Practical Demonstration: Building a Game [01:54:56]

The instructor demonstrates these concepts by iterating through versions of a "Homing" game:

#### 1. Simple Movement and Bouncing [01:54:56]

- **The Goal:** Make a sprite (Yale logo) move back and forth.
- **The Logic:** - `Move 1 step`
  - `If on edge, bounce`
- **Key Tip:** To make the game harder, you increase the **argument** for the move function (e.g., changing 1 step to 10 steps).

#### 2. "Boss Level" Homing Logic [01:56:07]

- **The Logic:**
  ```scratch
  forever:
    point towards [Harvard Crest]
    move 1 step
  ```
