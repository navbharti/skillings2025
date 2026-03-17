## DSA Comprehensive Overview
**Last Updated:** March 3, 2026

Data Structures and Algorithms (DSA) form the backbone of efficient software development, focusing on how data is organized and processed.

---

### 1. Fundamentals of DSA
* **Data Structures:** Specialized formats for organizing, processing, retrieving, and storing data (e.g., Arrays, Trees).
* **Algorithms:** A step-by-step procedure or set of rules to be followed in calculations or problem-solving operations (e.g., Sorting, Searching).



### 2. Why DSA Matters
* **Core of Technology:** Powers GPS, Search Engines, AI Chatbots, Databases, and Gaming.
* **Career Growth:** Top-tier companies (Google, Meta, Amazon, etc.) prioritize DSA in technical interviews.
* **Skill Development:** Enhances logical thinking, problem-solving, and code efficiency.

---

### 3. Prerequisites
Before diving into DSA, you should have a solid grasp of at least one programming language:
* **Popular choices:** C++, Java, Python, or JavaScript.

---

### 4. Step-by-Step Learning Path
The following sequence is recommended for mastering DSA:

| Phase | Topics |
| :--- | :--- |
| **Foundations** | Logic Building, Complexity Analysis (Time & Space) |
| **Linear Data Structures** | Arrays, Strings, Linked Lists, Stack, Queue, Deque |
| **Techniques & Patterns** | Two Pointers, Sliding Window, Prefix Sum, Recursion, Hashing |
| **Intermediate Concepts** | Searching, Sorting, Matrix/Grid, Bitwise Algorithms |
| **Non-Linear Data Structures** | Trees, Heaps, Graphs |
| **Advanced Paradigms** | Greedy Algorithms, Dynamic Programming (DP), Backtracking, Divide & Conquer |
| **Specialized Topics** | Trie, Segment Tree, Red-Black Tree, Binary Indexed Tree, Branch & Bound |

---

### 5. Mastery & Evaluation
To solidify your understanding, it is essential to complete **Topic-Wise Quizzes** for each section listed above, ranging from basic Logic Building to complex Dynamic Programming and Backtracking.

> **Note:** Consistent practice is the only way to master DSA. Focus on understanding the "Why" behind a data structure before the "How."

---


## Logic Building: The Core of Programming
**Last Updated:** March 3, 2026

Logic building is the process of creating structured, step-by-step methods to solve problems. It is the fundamental skill that allows programmers to translate human reasoning into computational solutions.

---

### 💡 Strategies for Sharpening Logic
To move from a problem statement to an optimized solution, follow these steps:
1.  **Analyze the Problem:** Read the requirements carefully until you can explain them in your own words.
2.  **Manual Test Cases:** Manually derive outputs for several different inputs to see how the data behaves.
3.  **Pattern Recognition:** Identify recurring sequences, mathematical properties, or constraints in your test cases.
4.  **The "Brute Force" First Rule:** Always start with the simplest, most obvious solution. Once it works, look for ways to reduce time or space complexity.

---

### 🛠 Problem Roadmap by Difficulty

Below is a curated list of problems categorized by the logic required to solve them.

#### **Level 1: Basic (Arithmetic & Conditionals)**
These focus on fundamental operators and simple `if-else` structures.
* **Check Even/Odd:** Understanding the modulo operator (`%`).
* **Swap Two Numbers:** Logic for temporary variables vs. arithmetic swaps.
* **Sum of Naturals/Squares:** Introduction to basic loops and mathematical series.
* **Closest Number & Dice Problem:** Basic rounding and probability logic.

#### **Level 2: Easy (Number Theory & Iteration)**
These introduce digit manipulation and basic mathematical properties.
* **Digit Operations:** Reversing digits, Sum of Digits, Armstrong, and Palindrome numbers.
* **Divisibility & Factors:** GCD/HCF, LCM, Prime Testing, and Perfect Numbers.
* **Conversions:** Decimal to Binary and identifying sequence patterns (e.g., $1, 3, 6, 10...$).
* **Geometry/Time:** Overlapping Rectangles and Day of the Week logic.

#### **Level 3: Medium (Combinatorics & Optimization)**
These require a deeper understanding of formulas and efficient iteration.
* **Advanced Math:** Square Root (without library functions), 3 Divisors, and Power Set.
* **Sequences:** Pascal’s Triangle and Fibonacci variations.
* **Probability & Counting:** nPr, nCr, Binomial Coefficients, and Catalan Numbers.
* **Modular Arithmetic:** Modular Exponentiation and Prime Factorization.



#### **Level 4: Hard (Algorithms & Complex Logic)**
These problems often require specific algorithmic strategies like recursion or mathematical sieves.
* **Sieve of Eratosthenes:** The most efficient way to find all primes up to $N$.
* **Recursion & Games:** Tower of Hanoi, Josephus Problem, and the 8-puzzle Problem.
* **Higher Math:** Euler's Totient Function and Clock Angle calculations.
* **Puzzles:** The Rat and Poisoned bottles logic.



---

## Logic Building: Checking Even or Odd

Determining whether a number is even or odd is a fundamental logic-building task. A number is **even** if it is exactly divisible by 2; otherwise, it is **odd**.

---

### 1. Naive Approach: Modulo Operator
This method uses the remainder operator (`%`) to check divisibility.

* **Logic:** $n \% 2$ returns the remainder of $n$ divided by 2.
    * If `remainder == 0`, the number is **Even**.
    * If `remainder == 1`, the number is **Odd**.
* **Complexity:**
    * **Time:** $O(1)$
    * **Space:** $O(1)$

#### Implementation (Java)
```java
public static boolean isEven(int n) {
    // A simple check using the modulo operator
    return (n % 2 == 0);
}
```

---

### 2. Efficient Approach: Bitwise AND
This approach leverages how numbers are stored in binary format.

* **Logic:** In binary, the Least Significant Bit (LSB)—the rightmost bit—determines if a number is even or odd.
    * **Odd numbers** always have a `1` as their last bit (e.g., $15 = 1111_2$).
    * **Even numbers** always have a `0` as their last bit (e.g., $44 = 101100_2$).
* **The Operation:** Performing `n & 1` masks all bits except the last one.
    * If `(n & 1) == 0`, the number is **Even**.
    * If `(n & 1) == 1`, the number is **Odd**.



* **Why use this?** Bitwise operations are executed directly by the CPU, making them theoretically faster than arithmetic division or modulo.
* **Complexity:**
    * **Time:** $O(1)$
    * **Space:** $O(1)$

#### Implementation (Java)
```java
public static boolean isEven(int n) {
    // Using Bitwise AND for maximum efficiency
    return (n & 1) == 0;
}
```

---

### Comparison Table

| Feature | Modulo Approach (`%`) | Bitwise Approach (`&`) |
| :--- | :--- | :--- |
| **Readability** | High (Intuitive for beginners) | Moderate (Requires binary knowledge) |
| **Performance** | Standard arithmetic speed | Extremely fast (Binary level) |
| **Logic** | Checks remainder after division | Checks the status of the last bit |

---

## Logic Building: Program for Multiplication Table

Printing a multiplication table is a classic exercise to understand iterative and recursive flow control. Given a number $n$, the goal is to output its multiples from 1 to 10.

---

### 1. Iterative Approach (Using Loops)
The iterative method uses a simple `for` loop to repeat the multiplication process.

* **Logic:** Start a loop from $i = 1$ and end at $i = 10$. In each step, calculate $n \times i$ and display the result.
* **Complexity:**
    * **Time:** $O(1)$ (The loop always runs exactly 10 times, making it constant time).
    * **Space:** $O(1)$ (No extra memory used).

#### Implementation (Java)
```java
class  Main{
    public static void printTable(int n) {
        // Iterate from 1 to 10
        for (int i = 1; i <= 10; ++i) {
            System.out.println(n + " * " + i + " = " + n * i);
        }
    }

    public static void main(String arg[]) {
        int n = 5; 
        printTable(n);
    }
}
```

---

### 2. Recursive Approach
Recursion solves the problem by calling the same function with an incremented multiplier until a "base case" is met.

* **Logic:** 1.  **Base Case:** If the multiplier $i$ reaches 11, stop (return).
    2.  **Recursive Step:** Print $n \times i$, then call the function again with $i + 1$.
* **Complexity:**
    * **Time:** $O(1)$ (10 recursive calls).
    * **Space:** $O(1)$ (Specifically, $O(10)$ stack space, which simplifies to constant).



#### Implementation (Java)
```java
class Main {
    static void printTable(int n, Integer... val) {
        int i = (val.length == 0) ? 1 : val[0];

        if (i == 11) return; // Base Case

        System.out.println(n + " * " + i + " = " + n * i);
        printTable(n, i + 1); // Recursive Call
    }

    public static void main(String[] args) {
        int n = 5;
        printTable(n);
    }
}
```

---

### Comparison of Execution Flow

| Feature | Iterative | Recursive |
| :--- | :--- | :--- |
| **Mechanism** | `for` or `while` loop | Function calling itself |
| **State Management** | Loop variable $i$ updated in place | State passed via function parameters |
| **Stop Condition** | Loop condition ($i \leq 10$) | Base case ($i == 11$) |

---

## Logic Building: Sum of First $n$ Natural Numbers

Finding the sum of the first $n$ natural numbers ($1 + 2 + 3 + ... + n$) is a foundational problem used to compare algorithm efficiency and mathematical optimization.

---

### 1. Naive Approach: Iterative Loop
This method uses a loop to add each number one by one to a running total.

* **Logic:** Start a counter at 1 and add it to a `sum` variable. Repeat until the counter reaches $n$.
* **Complexity:**
    * **Time:** $O(n)$ — The time taken grows linearly with $n$.
    * **Space:** $O(1)$ — Only one variable is used to store the sum.

#### Implementation (Java)
```java
static int findSum(int n) {
    int sum = 0;
    for (int i = 1; i <= n; i++) {
        sum += i;
    }
    return sum;
}
```

---

### 2. Alternative Approach: Recursion
Recursion breaks the problem into smaller sub-problems: the sum of $n$ numbers is $n$ plus the sum of $(n-1)$ numbers.

* **Logic:** * **Base Case:** If $n = 1$, return 1.
    * **Recursive Step:** Return `n + findSum(n - 1)`.
* **Complexity:**
    * **Time:** $O(n)$ — There are $n$ function calls.
    * **Space:** $O(n)$ — Each call occupies a spot on the **function call stack**.



---

### 3. Expected Approach: Mathematical Formula
This is the most efficient method, utilizing the Arithmetic Progression (AP) sum formula.

* **Formula:** $Sum = \frac{n(n + 1)}{2}$
* **Proof by Induction (Simplified):**
    If the formula works for $n-1$, the sum is $\frac{(n-1)n}{2}$. Adding the $n^{th}$ term:
    $$n + \frac{n(n-1)}{2} = \frac{2n + n^2 - n}{2} = \frac{n^2 + n}{2} = \frac{n(n+1)}{2}$$
* **Complexity:**
    * **Time:** $O(1)$ — Calculation is performed in a single step regardless of the size of $n$.
    * **Space:** $O(1)$ — No extra memory or stack space required.



#### Implementation (Java)
```java
static int findSum(int n) {
    return n * (n + 1) / 2;
}
```

---

### Efficiency Comparison Table

| Feature | Iterative (Loop) | Recursive | Formula (Best) |
| :--- | :--- | :--- | :--- |
| **Strategy** | Incremental Addition | Divide & Conquer | Mathematical Constant |
| **Time Complexity** | $O(n)$ | $O(n)$ | **$O(1)$** |
| **Space Complexity** | $O(1)$ | $O(n)$ (Stack) | **$O(1)$** |
| **Performance** | Good for small $n$ | Risks StackOverflow | **Instantaneous** |

---

## Logic Building: Sum of Squares of First $n$ Natural Numbers

This problem involves calculating the sum of the series $1^2 + 2^2 + 3^2 + \dots + n^2$. Like the sum of natural numbers, this can be solved using either iteration or an optimized mathematical formula.

---

### 1. Naive Approach: Iterative Loop
This method directly translates the mathematical series into a programming loop.

* **Logic:** Initialize `sum = 0`. Iterate from $i = 1$ to $n$, calculating the square of $i$ in each step and adding it to the total.
* **Complexity:**
    * **Time:** $O(n)$ — Linear time complexity as the loop runs $n$ times.
    * **Space:** $O(1)$ — Constant space used.

#### Implementation (Java)
```java
public static int summation(int n) {
    int sum = 0;
    for (int i = 1; i <= n; i++) {
        sum += (i * i);
    }
    return sum;
}
```

---

### 2. Expected Approach: Mathematical Formula
Using algebraic summation rules, the sum can be calculated in a single step.

* **Formula:** $\frac{n(n + 1)(2n + 1)}{6}$
* **Proof:** This formula is typically proven using **Mathematical Induction**, where we show it holds for $n=1$ and then prove that if it holds for $k-1$, it must hold for $k$.
* **Complexity:**
    * **Time:** $O(1)$ — Results are calculated instantly.
    * **Space:** $O(1)$ — No additional memory required.



---

### 3. Advanced Strategy: Avoiding Overflow
When dealing with large values of $n$ (common in competitive programming or large-scale data processing), the intermediate product $n \times (n+1) \times (2n+1)$ might exceed the maximum limit of a 32-bit integer (`int`).

* **Refined Logic:** Since $n(n+1)$ is always even, it is always divisible by 2. We can restructure the formula to perform divisions earlier to keep intermediate values smaller.
* **Restructured Formula:** $\left( \frac{n \times (n + 1)}{2} \right) \times \frac{(2n + 1)}{3}$

#### Implementation (Java)
```java
static int summation(int n) {
    // Strategic division to prevent integer overflow
    return (n * (n + 1) / 2) * (2 * n + 1) / 3;
}
```

---

### Efficiency Analysis

| Method | Time Complexity | Space Complexity | Best For |
| :--- | :--- | :--- | :--- |
| **Iterative** | $O(n)$ | $O(1)$ | Small values of $n$, learning loops. |
| **Formula** | $O(1)$ | $O(1)$ | Performance-critical applications. |
| **Refined Formula** | $O(1)$ | $O(1)$ | Large $n$ where overflow is a risk. |

---

## Logic Building: Swapping Two Numbers

Swapping two variables is a fundamental operation in programming, frequently used in sorting algorithms and data manipulation. The goal is to exchange the values of variables `a` and `b`.

---

### 1. Naive Approach: Using a Temporary Variable
This is the most intuitive method. Imagine having two cups of liquid; to swap them, you need a third empty cup.

* **Logic:**
    1.  Copy the value of `a` into a `temp` variable.
    2.  Move the value of `b` into `a`.
    3.  Move the value stored in `temp` into `b`.
* **Complexity:**
    * **Time:** $O(1)$
    * **Auxiliary Space:** $O(1)$



#### Implementation (Java)
```java
int a = 2, b = 3;
int temp = a; // temp = 2
a = b;        // a = 3
b = temp;     // b = 2
```

---

### 2. Expected Approach: Without a Third Variable
In many interviews, you may be asked to swap numbers without using extra space. This can be achieved using arithmetic or bitwise operations.

#### A. Arithmetic Method (Addition and Subtraction)
* **Logic:** 1.  `a = a + b` (Store sum in $a$)
    2.  `b = a - b` (Sum minus new $b$ gives original $a$)
    3.  `a = a - b` (Sum minus original $a$ gives original $b$)
* **Risk:** Can lead to **Integer Overflow** if the sum exceeds the capacity of the data type.

#### B. Bitwise Method (XOR Operation)
* **Logic:** Uses the property that $x \oplus x = 0$ and $x \oplus 0 = x$.
    1.  `a = a ^ b`
    2.  `b = a ^ b`
    3.  `a = a ^ b`
* **Benefit:** No risk of overflow and generally faster at the hardware level.



---

### 3. Language-Specific Built-in Approaches
Modern languages often provide cleaner, "syntactic sugar" ways to perform swaps without manual logic.

* **C++:** Uses the utility function `swap(a, b);`.
* **Python:** Uses tuple unpacking: `a, b = b, a`.
* **JavaScript (ES6+):** Uses destructuring: `[a, b] = [b, a];`.

---

### Summary Table

| Method | Extra Space | Pros | Cons |
| :--- | :--- | :--- | :--- |
| **Temporary Variable** | $O(1)$ | Most readable and safe. | Uses one extra memory slot. |
| **Arithmetic (+/-)** | $O(1)$ | No extra variable. | Risk of integer overflow. |
| **Bitwise (XOR)** | $O(1)$ | Fast, no overflow risk. | Less readable for beginners. |
| **Language Built-ins** | $O(1)$ | Cleanest code. | Hidden implementation details. |

---

## Logic Building: Swap Without a Third Variable

Swapping without a temporary variable is a common optimization challenge. It relies on mathematical or logical properties to "encode" both values into a single variable temporarily.

---

### 1. Using Arithmetic Operators (`+` and `-`)
This method uses addition to combine both values and subtraction to extract them back in reverse order.

* **Step-by-Step Logic:**
    1.  **Add:** `a = a + b` (Now `a` holds the total sum).
    2.  **Extract Original `a`:** `b = a - b` (Sum - original `b` = original `a`).
    3.  **Extract Original `b`:** `a = a - b` (Sum - original `a` = original `b`).
* **Complexity:** * **Time:** $O(1)$
    * **Space:** $O(1)$
* **Caution:** This can cause **Integer Overflow** if the sum of `a` and `b` exceeds the maximum value of the `int` data type (e.g., $2^{31}-1$).



---

### 2. Using Bitwise XOR (`^`)
The XOR operator is safer and more efficient as it operates at the bit level and does not suffer from overflow issues.

* **Core Properties:**
    * $X \oplus X = 0$
    * $X \oplus 0 = X$
    * Commutative and Associative: Order doesn't matter.
* **Step-by-Step Logic:**
    1.  `a = a ^ b` (A composite "key" of both values).
    2.  `b = a ^ b` (Effectively: `(original_a ^ original_b) ^ original_b` $\rightarrow$ `original_a`).
    3.  `a = a ^ b` (Effectively: `(original_a ^ original_b) ^ original_a` $\rightarrow$ `original_b`).



---

### Implementation Comparison

#### **Arithmetic (Java)**
```java
int a = 2, b = 3;
a = a + b; // a = 5
b = a - b; // b = 5 - 3 = 2
a = a - b; // a = 5 - 2 = 3
```

#### **Bitwise XOR (Java)**
```java
int a = 2, b = 3;
a = a ^ b; 
b = a ^ b; // b is now original a
a = a ^ b; // a is now original b
```

---

### Summary Table

| Method | Safety | Efficiency | Use Case |
| :--- | :--- | :--- | :--- |
| **Arithmetic** | ⚠️ Potential Overflow | High | Basic mathematical logic. |
| **Bitwise XOR** | ✅ Safe from Overflow | Extremely High | Competitive programming & Low-level systems. |
| **Third Variable**| ✅ Always Safe | High | General purpose (Best readability). |

---

## Logic Building: Find Closest to $n$ and Divisible by $m$

The goal is to find an integer $x$ such that $x$ is divisible by $m$ and the distance $|n - x|$ is minimized. A specific tie-breaking rule applies: if two numbers are equally close, choose the one with the larger absolute value.

---

### 1. Naive Approach: Iterative Checking
This approach explores the neighborhood around $n$ to find the best candidate.

* **Logic:** Since a multiple of $m$ must exist within the range $[n - |m|, n + |m|]$, we iterate through these integers and check if $i \% m == 0$.
* **Tie-breaking:** We track the `minDifference`. If a new $i$ has the same difference but a larger `Math.abs(i)`, we update our result.
* **Complexity:**
    * **Time:** $O(m)$ — The loop runs proportional to the size of $m$.
    * **Space:** $O(1)$ — No extra memory used.

---

### 2. Expected Approach: Quotient Calculation
A more efficient method uses the properties of integer division to find the two closest multiples of $m$.

* **Logic:**
    1.  Find the initial quotient $q = n / m$.
    2.  **Candidate 1 ($n1$):** $m \times q$. This is the multiple resulting from standard truncation in integer division.
    3.  **Candidate 2 ($n2$):** The *other* surrounding multiple. 
        * If $n$ and $m$ have the same sign (both $+$ or both $-$), $n2 = m \times (q + 1)$.
        * If they have opposite signs, $n2 = m \times (q - 1)$.
    4.  **Comparison:** Compare $|n - n1|$ and $|n - n2|$. Return the smaller one. If equal, return the one where `Math.abs` is greater.

* **Complexity:**
    * **Time:** $O(1)$ — Constant time mathematical operations.
    * **Space:** $O(1)$ — Constant space.



#### Implementation (Java)
```java
static int closestNumber(int n, int m) {
    int q = n / m;
    int n1 = m * q;
    
    // Determine the second candidate based on the direction of n
    int n2 = (n * m > 0) ? (m * (q + 1)) : (m * (q - 1));

    if (Math.abs(n - n1) < Math.abs(n - n2)) {
        return n1;
    }
    
    // Tie-breaking (n2 is naturally the larger absolute value in a tie here)
    return n2;
}
```

---

### Summary of Examples

| $n$ | $m$ | $n1$ | $n2$ | Closest | Reason |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **13** | **4** | 12 | 16 | **12** | $|13-12|=1$, which is less than $|13-16|=3$. |
| **-15** | **6** | -12 | -18 | **-18** | Both are 3 units away. $|-18| > |-12|$. |

---

## Logic Building: The Dice Problem

The problem requires finding the number on the opposite face of a standard six-sided die, given the number on the current face.

---

### 1. Understanding the Die Structure
In a standard cubical die, the faces are numbered 1 through 6. The arrangement of these numbers follows a specific rule: the sum of the numbers on any two opposite faces is always **7**.

* **1** is opposite **6** ($1 + 6 = 7$)
* **2** is opposite **5** ($2 + 5 = 7$)
* **3** is opposite **4** ($3 + 4 = 7$)



---

### 2. Naive Approach: Conditional Logic
This method uses an `if-else` or `switch` statement to map each input to its known opposite.

* **Logic:** Manually check the input $n$ and assign the corresponding opposite value.
* **Complexity:**
    * **Time:** $O(1)$
    * **Space:** $O(1)$

#### Implementation (Java)
```java
public static int oppositeFaceOfDice(int n) {
    if (n == 1) return 6;
    if (n == 2) return 5;
    if (n == 3) return 4;
    if (n == 4) return 3;
    if (n == 5) return 2;
    return 1;
}
```

---

### 3. Expected Approach: Mathematical Observation
By leveraging the "Sum of 7" rule, we can solve the problem with a simple subtraction, eliminating the need for multiple branches in our code.

* **Logic:** Since $Opposite + Current = 7$, then $Opposite = 7 - Current$.
* **Complexity:**
    * **Time:** $O(1)$ — Performs a single subtraction.
    * **Space:** $O(1)$ — No additional memory used.

#### Implementation (Java)
```java
public static int oppositeFaceOfDice(int n) {
    // Standard dice property: sum of opposite faces is 7
    return 7 - n;
}
```

---

### Comparison Table

| Feature | `if-else` Approach | Mathematical Approach |
| :--- | :--- | :--- |
| **Code Length** | Lengthy/Verbose | Concise (One line) |
| **Scalability** | Harder to adapt for different dice | Easily adapted (e.g., $13 - n$ for a 12-sided die) |
| **Logic Type** | Hard-coded mapping | Algorithmic/Mathematical |

---

## Logic Building: Sum of Digits of a Number

Calculating the sum of digits is a classic exercise in digit manipulation. It requires isolating each digit of a number regardless of its position (units, tens, hundreds, etc.).

---

### 1. Approach 1: Digit Extraction (Iterative)
This is the most efficient and common method. It uses the properties of the decimal system (base 10) to peel off digits one by one.

* **Logic:**
    1.  **Extract:** Use `n % 10` to get the last digit (remainder when divided by 10).
    2.  **Accumulate:** Add that digit to a `sum` variable.
    3.  **Reduce:** Use `n / 10` to remove the last digit (integer division).
    4.  Repeat until the number becomes 0.
* **Complexity:**
    * **Time:** $O(\log_{10}n)$ — The number of iterations is equal to the number of digits in $n$.
    * **Space:** $O(1)$ — Only a few integer variables are used.



#### Implementation (Java)
```java
static int sumOfDigits(int n) {
    int sum = 0;
    while (n != 0) {
        sum += n % 10; // Add last digit
        n /= 10;       // Remove last digit
    }
    return sum;
}
```

---

### 2. Approach 2: Using Recursion
Recursion follows the same logic as the iterative approach but uses the function call stack to handle the state.

* **Logic:**
    * **Base Case:** If `n == 0`, return 0.
    * **Recursive Step:** Return `(n % 10) + sumOfDigits(n / 10)`.
* **Complexity:**
    * **Time:** $O(\log_{10}n)$
    * **Space:** $O(\log_{10}n)$ — Due to the recursion stack depth.



---

### 3. Approach 3: String Conversion
This approach treats the number as a sequence of characters. It is particularly helpful if the input is provided as a very long string (beyond the range of `long`).

* **Logic:**
    1.  Convert the integer to a `String`.
    2.  Iterate through the string character by character.
    3.  Convert each character back to its numeric value (by subtracting the ASCII value of `'0'`) and add to the sum.
* **Complexity:**
    * **Time:** $O(d)$ where $d$ is the number of digits.
    * **Space:** $O(d)$ to store the string representation.

---

### Comparison Table

| Feature | Digit Extraction (Best) | Recursion | String Conversion |
| :--- | :--- | :--- | :--- |
| **Performance** | Fastest | Slower (Stack overhead) | Slowest (Object creation) |
| **Memory** | Minimal ($O(1)$) | Moderate ($O(\text{digits})$) | High ($O(\text{digits})$) |
| **Flexibility** | Standard Integers | Standard Integers | Handles extremely large numbers |
| **Readability** | High | Moderate | High |

---

## Logic Building: Program to Reverse Digits of a Number

Reversing the digits of an integer is a common task that tests your ability to manipulate numbers through loops, recursion, or data type conversion.

---

### 1. Iterative Approach: Digit-by-Digit Extraction
This is the most standard method. It builds the reversed number one digit at a time using basic arithmetic.

* **Logic:**
    1.  Initialize `revNum = 0`.
    2.  **Extract:** Get the last digit of $n$ using `n % 10`.
    3.  **Append:** Shift the existing `revNum` one position to the left (`revNum * 10`) and add the extracted digit.
    4.  **Reduce:** Remove the last digit from $n$ using `n / 10`.
    5.  Repeat until $n$ is 0.
* **Complexity:**
    * **Time:** $O(\log n)$ — Proportional to the number of digits.
    * **Space:** $O(1)$ — Only a single variable is used.



#### Implementation (Java)
```java
static int reverseDigits(int n) {
    int revNum = 0;
    while (n > 0) {
        revNum = revNum * 10 + n % 10;
        n = n / 10;
    }
    return revNum;
}
```

---

### 2. Recursive Approach
Recursion handles the reversal by processing digits as it unwinds the function call stack.

* **Logic:** The function calls itself with $n/10$ until it reaches the base case ($n=0$). As the recursion "returns," it multiplies each digit by its corresponding power of 10 (`basePos`) and adds it to the total.
* **Complexity:**
    * **Time:** $O(\log n)$
    * **Space:** $O(\log n)$ — Requires stack space for each digit.

---

### 3. String Conversion Approach
This method leverages high-level language features to reverse the number as a sequence of characters.

* **Logic:** Convert the number to a `String` or `StringBuffer`, use a built-in `reverse()` function, and then parse it back into an `int`.
* **Pros/Cons:** It is highly readable but involves more overhead due to object creation.
* **Python Slicing:** In Python, this is exceptionally concise: `str(n)[::-1]`.

---

### Comparison of Methods

| Feature | Iterative (Optimal) | Recursive | String/Slicing |
| :--- | :--- | :--- | :--- |
| **Performance** | **High** | Moderate | Lower |
| **Space** | **$O(1)$** | $O(\log n)$ | $O(\log n)$ |
| **Leading Zeros** | Truncates (e.g., $100 \rightarrow 1$) | Truncates | Can preserve as String |
| **Best For** | Embedded/Performance | Academic Logic | Scripting/Rapid Dev |

---

### Important Edge Case: Leading Zeros
When reversing a number like **200**, the mathematical approaches will yield **2**, because $002$ is numerically equal to $2$. If your application requires preserving the leading zeros (e.g., producing the string "002"), you must use the **String** approach without converting it back to an integer.

---

## Logic Building: Primality Test and School Method

A primality test determines whether a given integer $n$ is prime. A prime number is a natural number greater than 1 that is divisible only by 1 and itself.

---

### 1. Basic School Method
The simplest way to check for primality is to try dividing the number by every possible integer.

* **Logic:** Iterate through all integers from 2 up to $n-1$. If $n$ is divisible by any of these, it is not prime.
* **Complexity:**
    * **Time:** $O(n)$ — We perform $n-2$ checks in the worst case.
    * **Space:** $O(1)$

#### Implementation (Java)
```java
static boolean isPrime(int n) {
    if (n <= 1) return false;
    for (int i = 2; i < n; i++)
        if (n % i == 0) return false;
    return true;
}
```

---

### 2. Optimized School Method ($\sqrt{n}$)
We can significantly reduce the number of checks by observing that if $n = a \times b$, then at least one of the factors ($a$ or $b$) must be less than or equal to $\sqrt{n}$.

* **Logic:** Instead of checking up to $n-1$, stop the loop at $\sqrt{n}$. If no factor is found by this point, none will be found later.
* **Complexity:**
    * **Time:** $O(\sqrt{n})$ — Significant improvement for large numbers.
    * **Space:** $O(1)$



#### Implementation (Java)
```java
static boolean isPrime(int n) {
    if (n <= 1) return false;
    // Check from 2 to sqrt(n)
    for (int i = 2; i * i <= n; i++)
        if (n % i == 0) return false;
    return true;
}
```

---

### 3. Highly Optimized Method ($6k \pm 1$)
This method is based on the mathematical fact that all prime numbers greater than 3 can be written in the form $6k \pm 1$.

* **Logic:**
    1.  Handle small primes (2 and 3) as corner cases.
    2.  Eliminate all numbers divisible by 2 or 3.
    3.  Iterate through the remaining numbers using the step `i += 6`. In each iteration, check divisibility by $i$ (which is $6k-1$) and $i+2$ (which is $6k+1$).
* **Efficiency:** This is roughly 3 times faster than the standard $O(\sqrt{n})$ check because it skips all even numbers and multiples of 3.



#### Implementation (Java)
```java
static boolean isPrime(int n) {
    if (n <= 3) return n > 1;
    if (n % 2 == 0 || n % 3 == 0) return false;

    // Check multiples of 6k +/- 1 up to sqrt(n)
    for (int i = 5; i * i <= n; i += 6) {
        if (n % i == 0 || n % (i + 2) == 0)
            return false;
    }
    return true;
}
```

---

### Complexity Comparison Table

| Method | Time Complexity | Efficiency Note |
| :--- | :--- | :--- |
| **Basic School Method** | $O(n)$ | Very slow for large $n$. |
| **$\sqrt{n}$ Optimization** | $O(\sqrt{n})$ | Drastic reduction in iterations. |
| **$6k \pm 1$ Method** | $O(\sqrt{n})$ | Best performance; skips unnecessary checks. |

---

## Logic Building: Check if a Number is a Power of Another Number

The goal is to determine if a positive integer $y$ can be expressed as $x^n$, where $n$ is a non-negative integer.

---

### 1. Naive Approach: Repeated Multiplication
This method mimics how we manually check powers by multiplying the base $x$ repeatedly.

* **Logic:** Start with `pow = 1`. While `pow` is less than `y`, multiply `pow` by `x`. If at any point `pow` equals `y`, return `true`.
* **Special Case:** If $x=1$, then $y$ must be 1 to be a power.
* **Complexity:**
    * **Time:** $O(\log_x y)$ — The number of multiplications corresponds to the exponent $n$.
    * **Space:** $O(1)$

#### Implementation (Java)
```java
public static boolean isPower(int x, long y) {
    if (x == 1) return (y == 1);
    long pow = 1;
    while (pow < y) {
        pow *= x;
    }
    return (pow == y);
}
```

---

### 2. Better Approach: Binary Search Method
This approach uses exponential growth to narrow down the range where the potential power could exist.

* **Logic:** 1.  Repeatedly square the base ($x, x^2, x^4, \dots$) until you match or exceed $y$. 
    2.  If you overshoot $y$, perform a binary search within the last known range to see if any integer exponent results in exactly $y$.
* **Complexity:**
    * **Time:** $O(\log(\log_x y))$ — Much faster for extremely large values of $y$.
    * **Space:** $O(1)$

---

### 3. Expected Approach: Logarithmic Method
The most mathematically direct way to solve this is using logarithms and the change of base formula:
$$\log_x(y) = \frac{\log(y)}{\log(x)}$$

* **Logic:** If $y$ is a power of $x$, then $\log_x(y)$ must be an integer. We calculate the value and check if it equals its "floor" (the integer part).
* **Complexity:**
    * **Time:** $O(1)$ — Assuming constant time for logarithmic calculations.
    * **Space:** $O(1)$



#### Implementation (Java)
```java
public static boolean isPower(int x, int y) {
    if (y == 1) return true; // x^0 is always 1
    double res = Math.log(y) / Math.log(x);
    // Check if the result is an integer
    return Math.abs(res - Math.round(res)) < 1e-9;
}
```
*Note: Due to floating-point precision issues in computers, it is often safer to check if the difference between the result and the nearest integer is extremely small (e.g., `< 1e-9`) rather than using a direct `==` comparison.*

---

### Summary Table

| Method | Strategy | Time Complexity | Best For |
| :--- | :--- | :--- | :--- |
| **Multiplication** | Iterative | $O(\log_x y)$ | Small exponents and beginners. |
| **Binary Search** | Divide & Conquer | $O(\log \log y)$ | Very large numbers in technical tests. |
| **Logarithmic** | Mathematical | $O(1)$ | High-performance production code. |

---

## Logic Building: Find if Two Rectangles Overlap

Determining if two rectangles overlap is a common problem in computer graphics, collision detection, and layout design. A rectangle is defined by two points: **Top-Left (l)** and **Bottom-Right (r)**.

---

### 1. The Core Logic: Elimination
Instead of trying to find all the ways rectangles *can* overlap (which are many), it is much simpler to determine the conditions under which they **cannot** overlap. 

Two rectangles **do not overlap** if any of the following is true:
1.  **Horizontal Separation:** One rectangle is completely to the left of the other.
2.  **Vertical Separation:** One rectangle is completely above the other.

If neither of these conditions is met, the rectangles must be overlapping.



---

### 2. Identifying Non-Overlap Conditions

Let the first rectangle be $R1$ (with points $l1, r1$) and the second be $R2$ (with points $l2, r2$).

#### **A. Left/Right Separation**
Rectangle $R1$ is to the left of $R2$ if its right edge ($r1.x$) is to the left of $R2$'s left edge ($l2.x$).
* **Condition:** `l1.x > r2.x` or `l2.x > r1.x`

#### **B. Above/Below Separation**
Rectangle $R1$ is above $R2$ if its bottom edge ($r1.y$) is higher than $R2$'s top edge ($l2.y$).
* **Condition:** `r1.y > l2.y` or `r2.y > l1.y`
*(Note: This assumes standard Cartesian coordinates where y increases upwards).*



---

### 3. Implementation in Java

```java
static boolean doOverlap(Point l1, Point r1, Point l2, Point r2) {
    // 1. If one rectangle is to the left side of the other
    if (l1.x > r2.x || l2.x > r1.x) {
        return false;
    }

    // 2. If one rectangle is above the other
    if (r1.y > l2.y || r2.y > l1.y) {
        return false;
    }

    return true;
}
```

---

### 4. Complexity Analysis
* **Time Complexity:** $O(1)$ — Only a fixed number of comparisons are performed regardless of the coordinates.
* **Auxiliary Space:** $O(1)$ — No extra memory is allocated beyond primitive variables.

---

### Summary Table

| Case | Logical Check | Result |
| :--- | :--- | :--- |
| **Separated Horizontally** | `l1.x > r2.x` OR `l2.x > r1.x` | No Overlap |
| **Separated Vertically** | `r1.y > l2.y` OR `r2.y > l1.y` | No Overlap |
| **Otherwise** | All other cases | **Overlap** |

---

## Logic Building: Factorial of a Number

The factorial of a non-negative integer $n$ (denoted as $n!$) is the product of all positive integers less than or equal to $n$. By definition, $0! = 1$.

---

### 1. Iterative Solution
This method uses a simple loop to accumulate the product from 1 to $n$.

* **Logic:** Initialize `ans = 1`. Iterate from 2 up to $n$, multiplying the current value of `ans` by the loop index $i$ in each step.
* **Complexity:**
    * **Time:** $O(n)$ — The loop executes $n-1$ times.
    * **Space:** $O(1)$ — Only a single variable is used to store the result.

#### Implementation (Java)
```java
public static int factorial(int n) {
    int ans = 1;
    for (int i = 2; i <= n; i++) {
        ans *= i;
    }
    return ans;
}
```

---

### 2. Recursive Solution
Recursion defines $n!$ in terms of a smaller subproblem: $n! = n \times (n-1)!$.

* **Logic:** * **Base Case:** if $n=0$ or $n=1$, return 1.
    * **Recursive Step:** return $n \times \text{factorial}(n-1)$.
* **Complexity:**
    * **Time:** $O(n)$ — There are $n$ recursive calls.
    * **Space:** $O(n)$ — The system must maintain a stack for $n$ function calls.



---

### 3. Key Considerations

#### **Handling Large Numbers**
Factorials grow extremely fast. For example, $13!$ exceeds the limit of a 32-bit `int`, and $21!$ exceeds a 64-bit `long`. 
* **Java Solution:** Use `java.math.BigInteger` for factorials of numbers larger than 20.

#### **Trailing Zeros**
To find the number of trailing zeros in $n!$ without calculating the full product, count the factors of 5 in the prime factorization of $n!$. Each pair of 2 and 5 creates a 10 (a trailing zero), and since factors of 2 are always more plentiful than 5, the count of 5s determines the zeros.

---

### Comparison Table

| Feature | Iterative Approach (Best) | Recursive Approach |
| :--- | :--- | :--- |
| **Performance** | Faster (No function call overhead) | Slower (Stack management) |
| **Memory** | **$O(1)$** | $O(n)$ (Call Stack) |
| **Readability** | Clear and direct | Elegant and mathematical |
| **Risk** | None | Potential `StackOverflowError` for large $n$ |

---

## Logic Building: Factorial of a Large Number

Calculating the factorial of numbers like 100 or 500 is impossible using standard primitive data types. For instance, **100!** has 158 digits, while a 64-bit `long` in Java can only hold up to 19 digits. To solve this, we must treat numbers as collections of individual digits.

---

### 1. Manual Multiplication Approach (Array-Based)
This method simulates how we multiply numbers on paper: multiplying a large number by a single digit and carrying over the remainder.

* **Logic:**
    1.  Create an array `res[]` where each index stores a single digit.
    2.  To multiply the current result by a number $x$, multiply each digit in the array by $x$ and add the carry from the previous position.
    3.  The result is stored in reverse order in the array (the unit digit at index 0) to make carrying easier.
* **Complexity:**
    * **Time:** $O(N \log(N!))$ — Roughly $O(N^2)$ for simpler analysis.
    * **Space:** $O(\text{Number of digits})$ — For 100!, an array of size 200–500 is sufficient.



#### Implementation Fragment (Java)
```java
static int multiply(int x, int res[], int res_size) {
    int carry = 0;
    for (int i = 0; i < res_size; i++) {
        int prod = res[i] * x + carry;
        res[i] = prod % 10; // Current digit
        carry = prod / 10;  // Carry for next position
    }
    // Append remaining carry as new digits
    while (carry != 0) {
        res[res_size] = carry % 10;
        carry /= 10;
        res_size++;
    }
    return res_size;
}
```

---

### 2. The Java `BigInteger` Approach
In professional Java development, you would use the `java.math.BigInteger` class, which handles arbitrary-precision integers automatically.

* **Logic:** `BigInteger` uses an internal array similar to the approach above but is highly optimized for performance and memory.
* **Complexity:**
    * **Time:** $O(N \cdot M)$ where $M$ is the number of bits.
    * **Space:** $O(1)$ (Relative to the user's code, though memory is used internally).

#### Implementation (Java)
```java
import java.math.BigInteger;

static BigInteger factorial(int N) {
    BigInteger f = BigInteger.ONE;
    for (int i = 2; i <= N; i++)
        f = f.multiply(BigInteger.valueOf(i));
    return f;
}
```

---

### 3. Linked List Approach
This is a variation of the array method. Instead of a fixed-size array, each digit is stored in a `Node`. This is more memory-efficient as it grows dynamically.

* **Logic:** Each node stores one digit and points to the `prev` node (representing the next higher place value). When a carry remains after traversing the list, we simply append new nodes.
* **Complexity:**
    * **Time:** $O(N^2)$
    * **Space:** $O(\text{Digits})$ — No wasted space from pre-allocated arrays.



---

### Comparison of Methods

| Feature | Array Method | `BigInteger` | Linked List |
| :--- | :--- | :--- | :--- |
| **Ease of Use** | Moderate | **High** | Moderate |
| **Memory Efficiency** | Fixed (Potentially wasteful) | High | **High** |
| **Speed** | Fast | **Fastest** | Moderate |
| **Best For** | Learning/Interviews | Production Code | Dynamic data structures study |

---

## Logic Building: Pair Cube Count

The problem asks us to find the number of pairs $(a, b)$ such that $a^3 + b^3 = n$, where $a \ge 1$ and $b \ge 0$. Since the order matters, $(1, 2)$ and $(2, 1)$ are counted as two distinct pairs.

---

### 1. Naive Approach: Nested Loops
This approach explores every possible combination of $a$ and $b$ up to $n$.

* **Logic:** Use two loops, one for $a$ and one for $b$. Check if the sum of their cubes equals $n$.
* **Complexity:**
    * **Time:** $O(n^2)$ — If $n=1000$, we perform $1,000,000$ checks.
    * **Space:** $O(1)$
* **Constraint Note:** This is highly inefficient for large $n$. Since $a^3$ must be $\le n$, $a$ only needs to go up to $\sqrt[3]{n}$.

---

### 2. Expected Approach: Cube Root Optimization
Instead of guessing both $a$ and $b$, we can fix $a$ and mathematically determine if a valid $b$ exists.

* **Logic:**
    1.  Iterate $a$ from 1 to $\sqrt[3]{n}$.
    2.  Calculate the remaining value needed: $diff = n - a^3$.
    3.  If $diff$ is a perfect cube, then a valid $b$ exists ($b = \sqrt[3]{diff}$).
    4.  **Important:** $b$ can be 0 (as per the $b \ge 0$ rule), so we check if $diff \ge 0$.
* **Complexity:**
    * **Time:** $O(\sqrt[3]{n})$ — For $n=1,000,000$, we only perform 100 iterations.
    * **Space:** $O(1)$



#### Implementation (Java)
```java
static int countPairs(int n) {
    int count = 0;
    // a goes from 1 up to the cube root of n
    for (int a = 1; a * a * a <= n; a++) {
        int aCube = a * a * a;
        int diff = n - aCube;

        // Find the cube root of the difference
        int b = (int) Math.round(Math.pow(diff, 1.0/3.0));

        // Check if b^3 exactly matches the difference
        if (b * b * b == diff) {
            count++;
        }
    }
    return count;
}
```

---

### Key Observation: The $b=0$ Case
In the condition $a^3 + b^3 = n$, if $n$ itself is a perfect cube (e.g., $n=8$), the pair $(2, 0)$ satisfies the equation because $2^3 + 0^3 = 8$. The optimized loop correctly identifies this by checking if the difference ($8-8=0$) is a perfect cube.

### Efficiency Comparison

| Method | Search Range for $a$ | Search Range for $b$ | Iterations for $n=10^6$ |
| :--- | :--- | :--- | :--- |
| **Nested Loops** | $1 \dots n$ | $0 \dots n$ | $1,000,000,000,000$ |
| **Single Loop** | $1 \dots \sqrt[3]{n}$ | Calculated ($O(1)$) | **100** |

---

## Logic Building: Greatest Common Divisor (GCD / HCF)

The Greatest Common Divisor (GCD), also known as the Highest Common Factor (HCF), of two numbers is the largest positive integer that divides both numbers without leaving a remainder. Finding the GCD is a cornerstone of number theory and is essential for simplifying fractions and solving linear Diophantine equations.

---

### 1. Naive Approach: Iterative Backwards Loop
This approach starts from the smallest of the two numbers and checks every integer downwards until it finds one that divides both.

* **Logic:** 1. Find `min(a, b)`.
    2. Start a loop from this minimum value down to 1.
    3. The first number that divides both `a` and `b` is the GCD.
* **Complexity:**
    * **Time:** $O(\min(a, b))$ — In the worst case (e.g., GCD is 1), the loop runs for the smaller number's duration.
    * **Space:** $O(1)$

---

### 2. Euclidean Algorithm (Subtraction Method)
The Euclidean algorithm is based on the principle that the GCD of two numbers does not change if the smaller number is subtracted from the larger one.



* **Logic:** Repeatedly subtract the smaller number from the larger one until both numbers become equal.
* **Complexity:**
    * **Time:** $O(\min(a, b))$ — If one number is very small (like 1) and the other very large, it takes many subtractions.
    * **Space:** $O(\min(a, b))$ due to the recursion stack.

---

### 3. Optimized Euclidean Algorithm (Modulo Method)
Instead of repeated subtraction, we can use the remainder operator (`%`). This is significantly faster because one modulo operation replaces multiple subtractions.



[Image of Euclidean algorithm flow chart]


* **Logic:** The GCD of $a$ and $b$ is the same as the GCD of $b$ and $a \% b$. We repeat this until the remainder becomes 0.
* **Complexity:**
    * **Time:** $O(\log(\min(a, b)))$ — This is extremely efficient even for massive numbers.
    * **Space:** $O(\log(\min(a, b)))$ for recursive calls (or $O(1)$ if implemented iteratively).

#### Implementation (Java)
```java
static int gcd(int a, int b) {
    if (b == 0) return a;
    return gcd(b, a % b);
}
```

---

### 4. Built-in Methods
In Java, for professional or competitive programming use, the `BigInteger` class provides a highly optimized `gcd()` method.

```java
import java.math.BigInteger;

int res = BigInteger.valueOf(a).gcd(BigInteger.valueOf(b)).intValue();
```

---

### Efficiency Comparison

| Method | Time Complexity | Best For |
| :--- | :--- | :--- |
| **Iterative Loop** | $O(\min(a, b))$ | Small numbers, learning loops. |
| **Euclidean (Subtraction)** | $O(\min(a, b))$ | Understanding the logic of subtraction. |
| **Euclidean (Modulo)** | $O(\log(\min(a, b)))$ | **Standard choice** for performance. |
| **Built-in Function** | $O(\log(\min(a, b)))$ | Production code and Big Integers. |

---

## Logic Building: GCD of More Than Two Numbers (Array)

Extending the Greatest Common Divisor logic from two numbers to an entire array relies on the **Associative Property** of GCD. This property states that the order in which you calculate the GCD of multiple numbers does not change the final result.

$$gcd(a, b, c) = gcd(a, gcd(b, c)) = gcd(gcd(a, b), c)$$

---

### 1. The Strategy: Cumulative GCD
To find the GCD of an array, we maintain a "running" GCD value. We initialize this value with the first element and then update it by finding the GCD of the current result and the next element in the array.

* **Step 1:** Initialize `result = arr[0]`.
* **Step 2:** Loop through the array from the second element to the last.
* **Step 3:** Update `result = gcd(result, arr[i])`.
* **Step 4:** **Optimization:** If `result` ever becomes **1**, stop the loop and return 1. Since $gcd(1, x) = 1$ for any integer $x$, no further calculations can change the result.



---

### 2. Implementation (Java)
We can use the optimized **Euclidean Algorithm** (modulo method) to calculate the GCD of pairs efficiently.

#### Recursive Implementation
```java
public static int gcd(int a, int b) {
    if (b == 0) return a;
    return gcd(b, a % b);
}

public static int findGCD(int[] arr) {
    int res = arr[0];
    for (int i = 1; i < arr.length; i++) {
        res = gcd(res, arr[i]);
        
        // Optimization: Early exit if GCD reaches 1
        if (res == 1) return 1;
    }
    return res;
}
```

---

### 3. Complexity Analysis
* **Time Complexity:** $O(n \times \log(\min(arr)))$
    * We traverse the array once ($n$).
    * For each element, we perform a GCD calculation, which takes logarithmic time relative to the value of the numbers.
* **Auxiliary Space:** * **Iterative:** $O(1)$.
    * **Recursive:** $O(\log(\min(arr)))$ due to the recursion stack for each pair.

---

### Summary Table

| Input Array | Intermediate Steps | Final GCD |
| :--- | :--- | :--- |
| `[2, 4, 6]` | $gcd(2, 4) = 2 \rightarrow gcd(2, 6) = 2$ | **2** |
| `[12, 18, 24]` | $gcd(12, 18) = 6 \rightarrow gcd(6, 24) = 6$ | **6** |
| `[3, 5, 7]` | $gcd(3, 5) = 1$ (Exit early) | **1** |

---

## Logic Building: Least Common Multiple (LCM)

The Least Common Multiple (LCM) of two integers $a$ and $b$ is the smallest positive integer that is perfectly divisible by both $a$ and $b$. While the concept is simple, the implementation varies significantly in efficiency.

---

### 1. Naive Approach: Iterative Multiples
This method follows the literal definition of LCM by checking multiples of the larger number.

* **Logic:** 1. Identify the larger number $g$ and the smaller number $s$.
    2. Check multiples of $g$ (i.e., $g, 2g, 3g, \dots$).
    3. The first multiple that is also divisible by $s$ is the LCM.
* **Complexity:**
    * **Time:** $O(\min(a, b))$ — In the worst case (like two prime numbers), you iterate until you reach $a \times b$.
    * **Space:** $O(1)$



---

### 2. Expected Approach: The GCD-LCM Formula
This is the most efficient method, leveraging the mathematical relationship between the Greatest Common Divisor (GCD) and the LCM.

**The Formula:**
$$a \times b = \text{GCD}(a, b) \times \text{LCM}(a, b)$$

Rearranging to find LCM:
$$\text{LCM}(a, b) = \frac{a \times b}{\text{GCD}(a, b)}$$

* **Logic:**
    1. Calculate the GCD of $a$ and $b$ using the Optimized Euclidean Algorithm (Modulo method).
    2. Use the formula to derive the LCM.
    3. **Best Practice:** Perform division before multiplication: `(a / gcd(a, b)) * b`. This prevents potential integer overflow that could occur if you calculated `a * b` first.
* **Complexity:**
    * **Time:** $O(\log(\min(a, b)))$ — Same as the Euclidean GCD algorithm.
    * **Space:** $O(\log(\min(a, b)))$ for recursive GCD calls.



#### Implementation (Java)
```java
static int gcd(int a, int b) {
    return (b == 0) ? a : gcd(b, a % b);
}

static int lcm(int a, int b) {
    if (a == 0 || b == 0) return 0;
    // Divide first to avoid overflow, then multiply
    return (Math.abs(a) / gcd(a, b)) * Math.abs(b);
}
```

---

### Comparison Table

| Feature | Naive Iteration | GCD-LCM Formula |
| :--- | :--- | :--- |
| **Logic** | Checking multiples | Mathematical relationship |
| **Speed** | Slow for large numbers | **Very Fast (Logarithmic)** |
| **Overflow Risk** | Low (if checked properly) | High (if multiplying $a \times b$ first) |
| **Reliability** | Good for small $n$ | **Standard for Competitive Programming** |

---

## Perfect Number

In number theory, a **Perfect Number** (also referred to as a "Complete Number") is a positive integer that equals the sum of its proper divisors. A proper divisor is any positive divisor of the number other than the number itself.

### The Core Concept
For any integer $n$, it is considered perfect if the sum of all its divisors (excluding $n$) is exactly equal to $n$.

**Example: The number 6**
* **Divisors of 6:** 1, 2, 3, and 6.
* **Proper Divisors:** 1, 2, and 3.
* **Sum:** $1 + 2 + 3 = 6$.
* **Result:** Since the sum equals the original number, 6 is a perfect number.

**Example: The number 28**
* **Proper Divisors:** 1, 2, 4, 7, and 14.
* **Sum:** $1 + 2 + 4 + 7 + 14 = 28$.
* **Result:** 28 is a perfect number.


---

### The Euclid-Euler Theorem
Even perfect numbers share a deep connection with **Mersenne Primes**. A Mersenne prime is a prime number that is one less than a power of two ($M_p = 2^p - 1$).

The **Euclid-Euler Theorem** states that every even perfect number can be generated using the formula:
$$2^{p-1}(2^p - 1)$$
*...where $(2^p - 1)$ must be a prime number.*

#### Generating the First Few Perfect Numbers:
1.  **For $p = 2$:** $2^1(2^2 - 1) = 2 \times 3 = \mathbf{6}$
2.  **For $p = 3$:** $2^2(2^3 - 1) = 4 \times 7 = \mathbf{28}$
3.  **For $p = 5$:** $2^4(2^5 - 1) = 16 \times 31 = \mathbf{496}$
4.  **For $p = 7$:** $2^6(2^7 - 1) = 64 \times 127 = \mathbf{8128}$


---

### Key Properties and Facts
* **Odd Perfect Numbers:** To date, no odd perfect numbers have been discovered. It is one of the oldest unsolved mysteries in mathematics whether any exist.
* **Abundance of Discovery:** As of late 2024, only **52 perfect numbers** have been found. The 52nd perfect number is massive, containing over 82 million digits.
* **Ending Digits:** All known (even) perfect numbers end in either 6 or 28.
* **Mersenne Link:** There is a one-to-one correspondence between even perfect numbers and Mersenne primes. Every time a new Mersenne prime is discovered, a new perfect number is also found.

### Comparison Table: First 5 Perfect Numbers

| Rank | Perfect Number | Proper Divisors | Digits |
| :--- | :--- | :--- | :--- |
| 1 | 6 | 1, 2, 3 | 1 |
| 2 | 28 | 1, 2, 4, 7, 14 | 2 |
| 3 | 496 | 1, 2, 4, 8, 16, 31, 62, 124, 248 | 3 |
| 4 | 8128 | 1, 2, 4, 8, 16, 32, 64, 127... | 4 |
| 5 | 33,550,336 | 1, 2, 4, 8, 16, 32, 64, 128... | 8 |

---

A **Perfect Number** is a specific type of positive integer in number theory that equals the sum of its proper divisors (all positive divisors excluding the number itself).

### Core Logic
To determine if a number $n$ is perfect:
1.  Identify all divisors of $n$ that are less than $n$.
2.  Calculate the sum of these divisors.
3.  If the sum equals $n$, the number is categorized as **Perfect**.

**Example:**
* **Input:** $n = 6$
* **Divisors:** 1, 2, 3
* **Sum:** $1 + 2 + 3 = 6$
* **Result:** 6 is a Perfect Number.

---

### Implementation Strategies

#### 1. Naive Approach (Linear Search)
The simplest method involves iterating through every integer from 1 up to $n-1$ and checking for divisibility.

* **Time Complexity:** $O(n)$
* **Space Complexity:** $O(1)$

```java
public static boolean isPerfect(int n) {
    if (n <= 1) return false;
    int sum = 0;
    for (int i = 1; i < n; i++) {
        if (n % i == 0) {
            sum += i;
        }
    }
    return sum == n;
}
```

#### 2. Optimized Approach (Square Root Method)
A more efficient way is to observe that divisors occur in pairs. If $i$ is a divisor of $n$, then $n/i$ is also a divisor. By iterating only up to $\sqrt{n}$, we can find all divisors significantly faster.

* **Time Complexity:** $O(\sqrt{n})$
* **Space Complexity:** $O(1)$



```java
public static boolean isPerfectOptimized(int n) {
    if (n <= 1) return false;
    
    // 1 is always a divisor, so we start sum with 1
    int sum = 1; 
    
    for (int i = 2; i * i <= n; i++) {
        if (n % i == 0) {
            if (i * i != n) {
                // Add both divisors in the pair
                sum = sum + i + (n / i);
            } else {
                // If it's a perfect square, add the root only once
                sum = sum + i;
            }
        }
    }
    return sum == n;
}
```

---

### Comparison of Methods

| Feature | Naive Method | Square Root Method |
| :--- | :--- | :--- |
| **Search Range** | $1$ to $n-1$ | $2$ to $\sqrt{n}$ |
| **Efficiency** | Lower (Slow for large $n$) | **Higher (Scalable)** |
| **Use Case** | Educational/Small inputs | Competitive Programming/DSA |

### Interesting Fact
All known perfect numbers are even. While the existence of odd perfect numbers is a famous unsolved problem in mathematics, none have been found as of early 2026.

[Perfect Number Practice Problem](https://www.youtube.com/watch?v=_HN_q6N_Yds)
This video provides a step-by-step walkthrough of solving the perfect number problem, which is helpful for visualizing the divisor summation logic.


---

## Logic Building: Adding Two Fractions

Adding two fractions ($\frac{n1}{d1} + \frac{n2}{d2}$) involves more than just adding the numerators and denominators. To get a mathematically correct and simplified result, we follow a structured approach using the **Least Common Multiple (LCM)** and **Greatest Common Divisor (GCD)**.

---

### 1. The Core Logic
The process can be broken down into three main steps:

1.  **Find a Common Denominator:** We find the LCM of the two denominators ($d1$ and $d2$). This ensures both fractions share a common base.
2.  **Adjust Numerators and Add:** Convert both fractions to the common denominator, add the adjusted numerators to get the new numerator ($n_{final}$), and use the LCM as the new denominator ($d_{final}$).
3.  **Simplify the Result:** Reduce the resulting fraction $\frac{n_{final}}{d_{final}}$ to its simplest form by dividing both the numerator and denominator by their GCD.


---

### 2. Mathematical Breakdown
Given fractions $\frac{a}{b}$ and $\frac{c}{d}$:

* **Common Denominator ($D$):** $\text{LCM}(b, d) = \frac{b \times d}{\text{GCD}(b, d)}$
* **Numerator Result ($N$):** $a \times (\frac{D}{b}) + c \times (\frac{D}{d})$
* **Final Simplification:**
    * Find $g = \text{GCD}(N, D)$
    * Simplified Result = $\frac{N/g}{D/g}$


---

### 3. Implementation (Java)
This approach is efficient and prevents unnecessary large numbers by simplifying at the end.

```java
public class FractionAddition {
    // Function to calculate GCD
    public static int gcd(int a, int b) {
        if (a == 0) return b;
        return gcd(b % a, a);
    }

    public static void addFraction(int n1, int d1, int n2, int d2) {
        // 1. Find common denominator (LCM of d1 and d2)
        int commonDen = (d1 * d2) / gcd(d1, d2);

        // 2. Adjust numerators and add
        int finalNum = (n1 * (commonDen / d1)) + (n2 * (commonDen / d2));

        // 3. Simplify the result
        int commonFactor = gcd(finalNum, commonDen);
        
        finalNum /= commonFactor;
        commonDen /= commonFactor;

        System.out.println(finalNum + "/" + commonDen);
    }

    public static void main(String[] args) {
        addFraction(1, 2, 3, 2); // Output: 2/1
        addFraction(1, 3, 3, 9); // Output: 2/3
    }
}
```

---

### 4. Complexity Analysis
* **Time Complexity:** $O(\log(\min(a, b)))$ — This is due to the Euclidean algorithm used for GCD.
* **Auxiliary Space:** $O(1)$ — We use a constant amount of extra space.

---

### Summary Table

| Step | Action | Tools Used |
| :--- | :--- | :--- |
| **Preparation** | Find common ground | LCM of denominators |
| **Addition** | Combine parts | Adjusted Numerator sum |
| **Cleaning** | Simplify | GCD of result |

---

## Logic Building: Finding the Day of the Week

Calculating the day of the week for any given date (past or future) is a common algorithmic challenge. The most efficient way to solve this is through a mathematical formula derived from **Zeller’s Congruence**.

---

### 1. The Strategy: Key Components
To find the day, we need to account for three main factors that shift the calendar:
1.  **Month Lengths:** Months have different numbers of days (28, 30, 31).
2.  **Leap Years:** Every 4 years, an extra day is added.
3.  **Century Rule:** Every 100 years is *not* a leap year, unless it is also divisible by 400.


---

### 2. The Optimized Formula
A simplified version of the algorithm uses a predefined array of "month shifts" (often called `t[]`).

**The Formula:**
$$\text{Day} = (y + \lfloor y/4 \rfloor - \lfloor y/100 \rfloor + \lfloor y/400 \rfloor + t[m-1] + d) \pmod 7$$

* **$d$:** The day of the month.
* **$m$:** The month.
* **$y$:** The year (if the month is January or February, we treat it as the 13th or 14th month of the *previous* year).
* **$t[]$:** An array storing month offsets: `{0, 3, 2, 5, 0, 3, 5, 1, 4, 6, 2, 4}`.


---

### 3. Implementation (Java)
This approach runs in constant time, $O(1)$, because it involves simple arithmetic regardless of how large the date is.

```java
public class DayFinder {
    static int dayOfWeek(int d, int m, int y) {
        // Month offset array
        int t[] = { 0, 3, 2, 5, 0, 3, 5, 1, 4, 6, 2, 4 };
        
        // If month is Jan or Feb, subtract 1 from the year
        if (m < 3) {
            y -= 1;
        }
        
        // Return 0 for Sunday, 1 for Monday, etc.
        return (y + y/4 - y/100 + y/400 + t[m-1] + d) % 7;
    }

    public static void main(String[] args) {
        int day = 30, month = 8, year = 2010;
        int res = dayOfWeek(day, month, year);
        
        String[] days = {"Sunday", "Monday", "Tuesday", "Wednesday", 
                         "Thursday", "Friday", "Saturday"};
        System.out.println("Day: " + days[res]);
    }
}
```

---

### 4. Complexity Analysis
* **Time Complexity:** $O(1)$ — The calculation takes the same amount of time for any date.
* **Auxiliary Space:** $O(1)$ — We only store a small fixed-size array and a few integers.

---

### Understanding the Results

| Result Code | Day of Week |
| :--- | :--- |
| **0** | Sunday |
| **1** | Monday |
| **2** | Tuesday |
| **3** | Wednesday |
| **4** | Thursday |
| **5** | Friday |
| **6** | Saturday |

---

## Logic Building: The Fibonacci Series

The Fibonacci series is a sequence where each number is the sum of the two preceding ones. It traditionally starts with **0** and **1**. This sequence appears frequently in nature (like the spirals of a seashell or the arrangement of leaves) and is a fundamental concept in algorithm design.

---

### 1. The Core Logic
The mathematical recurrence relation for the $n$-th Fibonacci number $F_n$ is:
$$F_n = F_{n-1} + F_{n-2}$$
*Where base cases are:*
$F_0 = 0, F_1 = 1$

**Example (First 10 terms):**
0, 1, 1, 2, 3, 5, 8, 13, 21, 34


---

### 2. Implementation Strategies

#### A. Iterative Approach (Most Efficient for Space)
This method uses a simple loop and three variables to track the current and previous two numbers.

* **Logic:** Start with `prev2 = 0` and `prev1 = 1`. In each iteration, calculate `curr = prev1 + prev2`, then shift the values.
* **Complexity:**
    * **Time:** $O(n)$
    * **Space:** $O(1)$

#### B. Recursive Approach (Intuitive but Inefficient)
This method calls the function itself for $(n-1)$ and $(n-2)$.
* **Drawback:** It recalculates the same values multiple times, leading to exponential time complexity.
* **Complexity:**
    * **Time:** $O(2^n)$
    * **Space:** $O(n)$ (due to recursion stack)


---

### 3. Implementation (Java - Iterative)
```java
public class Fibonacci {
    static void printFib(int n) {
        if (n < 1) return;

        int prev2 = 0;
        System.out.print(prev2 + " ");

        if (n == 1) return;

        int prev1 = 1;
        System.out.print(prev1 + " ");

        for (int i = 3; i <= n; i++) {
            int curr = prev1 + prev2;
            System.out.print(curr + " ");
            
            // Shift values for next iteration
            prev2 = prev1;
            prev1 = curr;
        }
    }

    public static void main(String[] args) {
        printFib(10); // Output: 0 1 1 2 3 5 8 13 21 34
    }
}
```

---

### 4. Advanced Connections
* **Golden Ratio ($\phi$):** The ratio of consecutive Fibonacci numbers ($\frac{F_{n+1}}{F_n}$) converges to approximately **1.618** as $n$ increases.
* **Fibonacci Spiral:** A spiral constructed by drawing quarter-circles in squares with side lengths equal to Fibonacci numbers.
* **Pascal’s Triangle:** The sums of the shallow diagonals of Pascal’s triangle form the Fibonacci sequence.


---

### Comparison of Methods

| Feature | Iterative | Recursive (Naive) | Dynamic Programming |
| :--- | :--- | :--- | :--- |
| **Logic** | Loops | Self-calling | Memoization |
| **Speed** | Fast ($O(n)$) | Very Slow ($O(2^n)$) | Fast ($O(n)$) |
| **Memory** | Minimal ($O(1)$) | High ($O(n)$ stack) | Moderate ($O(n)$ table) |

---

## Finding the Nth Fibonacci Number

Finding the $n$-th number in the Fibonacci sequence ($0, 1, 1, 2, 3, 5, \dots$) is a classic problem used to demonstrate various algorithmic techniques, from simple recursion to advanced matrix operations.

---

### 1. Approach Comparison Table
Depending on the value of $n$ and the constraints of your system, different methods are preferred.

| Method | Time Complexity | Space Complexity | Best For |
| :--- | :--- | :--- | :--- |
| **Recursion (Naive)** | $O(2^n)$ | $O(n)$ | Small $n$ values |
| **Memoization (Top-Down)** | $O(n)$ | $O(n)$ | Avoiding repeated work |
| **Bottom-Up DP** | $O(n)$ | $O(n)$ | Iterative clarity |
| **Space Optimized DP** | $O(n)$ | $O(1)$ | Memory efficiency |
| **Matrix Exponentiation** | $O(\log n)$ | $O(\log n)$ | Extremely large $n$ |
| **Golden Ratio (Binet's)** | $O(1)$ | $O(1)$ | Fast approximation |

---

### 2. The Efficient "Space-Optimized" Logic
Instead of storing the entire sequence in an array, we only keep track of the two previous numbers. This reduces memory usage significantly.


**Logic:**
1. Initialize `prev2 = 0` and `prev1 = 1`.
2. Loop from $2$ to $n$.
3. Calculate `curr = prev1 + prev2`.
4. Update: `prev2 = prev1` and `prev1 = curr`.
5. Return `curr` after the loop.


---

### 3. Java Implementation (Space Optimized)
```java
class Fibonacci {
    static int nthFibonacci(int n) {
        if (n <= 1) return n;

        int prev2 = 0;
        int prev1 = 1;
        int curr = 0;

        for (int i = 2; i <= n; i++) {
            curr = prev1 + prev2;
            prev2 = prev1;
            prev1 = curr;
        }
        return curr;
    }

    public static void main(String[] args) {
        int n = 9;
        System.out.println("The " + n + "th Fibonacci number is: " + nthFibonacci(n));
    }
}
```

---

### 4. Advanced: Matrix Exponentiation
For competitive programming where $n$ is very large (e.g., $n = 10^{18}$), we use the transformation matrix:

$$\begin{pmatrix} 1 & 1 \\ 1 & 0 \end{pmatrix}^n = \begin{pmatrix} F_{n+1} & F_n \\ F_n & F_{n-1} \end{pmatrix}$$

By calculating the $n$-th power of this matrix using **Binary Exponentiation**, we achieve $O(\log n)$ time.


---

### Summary of Strategies
* **Recursion:** Good for teaching, bad for production.
* **DP:** The standard "industry" way to solve it.
* **Matrix Power:** The "pro" way for huge constraints.

---


## Logic Building: Decimal to Binary Conversion

Converting a decimal number (Base 10) to binary (Base 2) is a fundamental operation in computer science. There are several ways to achieve this, ranging from simple division to high-performance bitwise operations.

---

### 1. The Core Logic: Repeated Division
The most common manual and algorithmic method is the **Double-Dabble** or **Repeated Division by 2**.


**The Steps:**
1.  Divide the decimal number by 2.
2.  Record the remainder (either 0 or 1).
3.  Update the number with the quotient from the division.
4.  Repeat until the number becomes 0.
5.  **Important:** The binary result is the sequence of remainders read in **reverse order** (from the last remainder to the first).

---

### 2. Implementation Strategies

#### A. Iterative Method (Using a Loop)
This is the standard approach. We store remainders in a string or array and reverse it at the end.
* **Time Complexity:** $O(\log_2 n)$ — The number of divisions is proportional to the number of bits.
* **Space Complexity:** $O(\log_2 n)$ — To store the binary digits.

#### B. Bitwise Method (High Performance)
Computers naturally store numbers in binary, so bitwise operators are the most direct way to "extract" these bits.
* **Logic:** Use `n & 1` to get the last bit, then `n >> 1` to shift the number right (equivalent to dividing by 2).
* **Benefit:** Bitwise operations are faster at the hardware level than arithmetic division and modulo.

---

### 3. Implementation (Java)

```java
public class Conversion {
    // Method 1: Iterative Division
    static String decToBinary(int n) {
        StringBuilder bin = new StringBuilder();
        while (n > 0) {
            int bit = n % 2;
            bin.append(bit);
            n = n / 2;
        }
        return bin.reverse().toString();
    }

    // Method 2: Bitwise (More efficient)
    static String decToBinaryBitwise(int n) {
        StringBuilder bin = new StringBuilder();
        while (n > 0) {
            // Get the least significant bit
            int bit = n & 1; 
            bin.append(bit);
            // Right shift to move to the next bit
            n = n >> 1; 
        }
        return bin.reverse().toString();
    }

    public static void main(String[] args) {
        int n = 12;
        System.out.println("Binary of 12: " + decToBinaryBitwise(n)); // Output: 1100
    }
}
```

---

### 4. Built-in Methods
In professional development, you would likely use a language's built-in library for simplicity:
* **Java:** `Integer.toBinaryString(n)`
* **Python:** `bin(n)[2:]`
* **JavaScript:** `n.toString(2)`

---

### Summary of Approaches

| Approach | Logic | Efficiency |
| :--- | :--- | :--- |
| **Division** | `n % 2` and `n / 2` | Standard |
| **Bitwise** | `n & 1` and `n >> 1` | High Performance |
| **Recursion** | Stack-based division | Elegant but uses more memory |
| **Built-in** | Library function | Recommended for production |

---

## Finding the N-th Term of the Series: 1, 3, 6, 10, 15, 21...

This specific sequence represents **Triangular Numbers**. The logic behind the series is that each term is the sum of all natural numbers up to $n$.

---

### 1. The Logic of Triangular Numbers
If you look at the difference between consecutive terms, you'll see a clear pattern:
* Term 1: **1**
* Term 2: $1 + 2 =$ **3**
* Term 3: $3 + 3 =$ **6**
* Term 4: $6 + 4 =$ **10**
* Term 5: $10 + 5 =$ **15**

The $n$-th term is the sum of the first $n$ natural numbers.


---

### 2. Implementation Strategies

#### A. Naive Approach (Iterative)
You can use a simple loop to add numbers from 1 to $n$.
* **Logic:** `for (i = 1 to n) { ans += i; }`
* **Complexity:**
    * **Time:** $O(n)$
    * **Space:** $O(1)$

#### B. Expected Approach (Formula-based)
Since the $n$-th term is simply the sum of the first $n$ natural numbers, we can use the mathematical formula for arithmetic progression:
$$S_n = \frac{n(n + 1)}{2}$$
* **Logic:** Plug $n$ directly into the formula.
* **Complexity:**
    * **Time:** $O(1)$
    * **Space:** $O(1)$

---

### 3. Implementation (Java)

```java
public class SeriesTerm {
    // Formula-based approach: O(1)
    static int findNthTerm(int n) {
        return n * (n + 1) / 2;
    }

    public static void main(String[] args) {
        int n = 4;
        System.out.println("The " + n + "th term is: " + findNthTerm(n)); 
        // Output: 10
    }
}
```

---

### Summary Table

| Method | Complexity | Pros | Cons |
| :--- | :--- | :--- | :--- |
| **Loop** | $O(n)$ | Easy to understand | Slower for very large $n$ |
| **Formula** | $O(1)$ | Mathematically optimal | Must remember the formula |

---

## Understanding Triangular Numbers

A number is considered a **Triangular Number** if it can be represented as a triangular grid of points where each row contains as many points as the row number. For example, the first row has 1 point, the second row has 2 points, the third has 3, and so on.


---

### 1. Key Mathematical Properties
* **Sequence:** 1, 3, 6, 10, 15, 21, 28, 36, 45, 55, ...
* **Formula:** The $n$-th triangular number $T_n$ is the sum of the first $n$ natural numbers:
  $$T_n = \frac{n(n + 1)}{2}$$
* **Geometric Intuition:** A triangular number corresponds to the number of dots in an equilateral triangle.

---

### 2. How to Check if a Number is Triangular

#### Approach 1: Iterative Summation (Naive)
We start adding natural numbers $(1, 2, 3, \dots)$ until the sum either equals the given number (True) or exceeds it (False).
* **Time Complexity:** $O(\sqrt{num})$ (since $T_n \approx n^2/2$, then $n \approx \sqrt{2 \cdot num}$)
* **Space Complexity:** $O(1)$

#### Approach 2: Quadratic Equation (Optimal)
We can use the formula $n(n+1)/2 = num$ and solve for $n$:
$$n^2 + n - 2 \cdot num = 0$$
Using the quadratic formula $n = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}$, where $a=1, b=1, c = -2 \cdot num$:
$$n = \frac{-1 \pm \sqrt{1 + 8 \cdot num}}{2}$$
If the positive root is an integer, the number is triangular.
* **Time Complexity:** $O(1)$ (or $O(\log n)$ depending on the implementation of the square root function)
* **Space Complexity:** $O(1)$

---

### 3. Java Implementation (Optimal Approach)

```java
public class TriangularCheck {
    static boolean isTriangular(int num) {
        if (num < 0) return false;

        // Use the discriminant: 1 + 8*num must be a perfect square
        double discriminant = 1 + 8.0 * num;
        double sqrtVal = Math.sqrt(discriminant);

        // Check if square root is an integer
        if (sqrtVal % 1 != 0) return false;

        // Solve for n = (-1 + sqrtVal) / 2
        double n = (sqrtVal - 1) / 2.0;

        // n must be an integer and positive
        return (n > 0 && n == Math.floor(n));
    }

    public static void main(String[] args) {
        int testNum = 55;
        if (isTriangular(testNum)) {
            System.out.println(testNum + " is a triangular number.");
        } else {
            System.out.println(testNum + " is NOT a triangular number.");
        }
    }
}
```

---

### 4. Interesting Fact: Relation to Square Numbers
An interesting property of triangular numbers is that the sum of two consecutive triangular numbers is always a **perfect square**:
$$T_{n-1} + T_n = n^2$$
*Example: $T_2(3) + T_3(6) = 9 (3^2)$*


---

## What is an Armstrong Number?

A positive integer of $n$ digits is called an **Armstrong Number** (also known as a narcissistic number) if the sum of its digits each raised to the power of $n$ equals the number itself.


---

### 1. The Mathematical Logic
To determine if a number $x$ with $n$ digits is an Armstrong number, follow this formula:
$$abcd\dots = a^n + b^n + c^n + d^n + \dots$$

**Examples:**
* **153:** It has 3 digits.
    $1^3 + 5^3 + 3^3 = 1 + 125 + 27 = 153$ (**True**)
* **9474:** It has 4 digits.
    $9^4 + 4^4 + 7^4 + 4^4 = 6561 + 256 + 2401 + 256 = 9474$ (**True**)
* **123:** It has 3 digits.
    $1^3 + 2^3 + 3^3 = 1 + 8 + 27 = 36$ (**False**)

---

### 2. Algorithmic Steps
1.  **Count Digits ($n$):** Determine how many digits are in the number.
2.  **Extract Digits:** Use a loop to get each digit (typically using `num % 10` and `num / 10`).
3.  **Calculate Power:** For each digit $r$, calculate $r^n$.
4.  **Sum Results:** Add these values together.
5.  **Compare:** Check if the final sum equals the original number.


---

### 3. Implementation (Java)

```java
import java.util.Scanner;

public class Armstrong {
    // Helper function to count digits
    static int countDigits(int n) {
        int count = 0;
        while (n != 0) {
            count++;
            n /= 10;
        }
        return count;
    }

    static boolean isArmstrong(int n) {
        int digits = countDigits(n);
        int temp = n;
        int sum = 0;

        while (temp != 0) {
            int lastDigit = temp % 10;
            // Add digit^digits to sum
            sum += Math.pow(lastDigit, digits);
            temp /= 10;
        }

        return (sum == n);
    }

    public static void main(String[] args) {
        int n = 153;
        System.out.println(n + " is Armstrong: " + isArmstrong(n));
    }
}
```

---

### 4. Complexity Analysis
* **Time Complexity:** $O(d \cdot \log d)$, where $d$ is the number of digits. The power function and the digit extraction both scale with the number of digits.
* **Space Complexity:** $O(1)$ as we only use a few integer variables.

---

## How to Check if a Number is a Palindrome

A **Palindrome Number** is an integer that remains the same when its digits are reversed. In other words, it reads the same forward and backward.


---

### 1. The Core Logic: Reversing the Number
The standard mathematical approach involves reversing the digits of the original number and then comparing the result to the original.

**The Process:**
1.  **Extract the last digit:** Use the modulo operator (`num % 10`).
2.  **Build the reversed number:** Multiply the current reversed value by 10 and add the extracted digit.
3.  **Remove the last digit:** Divide the original number by 10.
4.  **Repeat** until the number becomes 0.
5.  **Compare:** If `reversed_num == original_num`, it is a palindrome.


---

### 2. Implementation Strategies

#### A. Expected Approach (Integer Reversal)
This is the most memory-efficient method as it doesn't require extra data structures.
* **Time Complexity:** $O(\log_{10} n)$ — proportional to the number of digits.
* **Space Complexity:** $O(1)$ — only uses a few integer variables.

#### B. String Conversion Approach (For Large Numbers)
If the number is extremely large (exceeding 64-bit integer limits), it is safer to treat it as a string and use two pointers (one at the start, one at the end) to compare characters.
* **Time Complexity:** $O(\log_{10} n)$
* **Space Complexity:** $O(\log_{10} n)$ — to store the string representation.

---

### 3. Java Implementation (Integer Reversal)

```java
public class PalindromeChecker {
    static boolean isPalindrome(int n) {
        // Negative numbers are not palindromes (e.g., -121 reversed is 121-)
        if (n < 0) return false;

        int original = n;
        int reversed = 0;

        while (n != 0) {
            int digit = n % 10;
            reversed = (reversed * 10) + digit;
            n /= 10;
        }

        return original == reversed;
    }

    public static void main(String[] args) {
        int num = 12321;
        System.out.println(num + " is Palindrome: " + isPalindrome(num));
    }
}
```

---

### Summary Table

| Feature | Integer Reversal | String Comparison |
| :--- | :--- | :--- |
| **Space Usage** | Very Low ($O(1)$) | Moderate ($O(\text{digits})$) |
| **Overflow Risk** | High for very large numbers | None |
| **Best For** | Standard integers | Large inputs / competitive programming |

---

## What is a Digital Root?

The **Digital Root** (also known as the repeated digital sum) of a positive integer is the value obtained by summing its digits repeatedly until only a single-digit remains.


---

### 1. The Manual Process (Naive Approach)
1.  Sum the digits of the number.
2.  If the result is a single digit (0–9), that is the digital root.
3.  If the result is two or more digits, repeat step 1 with the new sum.

**Example: 1234**
* Sum of digits: $1 + 2 + 3 + 4 = 10$
* Since 10 is not a single digit: $1 + 0 = 1$
* **Digital Root = 1**

---

### 2. The Optimal Logic: Congruence Formula
Instead of looping through digits, we can find the digital root using a property of the number 9. Any number in the decimal system is congruent to the sum of its digits modulo 9. This is why the digital root of any number is simply the remainder when divided by 9 (with a special case for 9 itself).


#### The Formula:
$$
\text{dr}(n) = 
\begin{cases} 
0 & \text{if } n = 0 \\
9 & \text{if } n \neq 0, n \equiv 0 \pmod 9 \\
n \pmod 9 & \text{if } n \not\equiv 0 \pmod 9
\end{cases}
$$

A more concise version of this formula is:
$$\text{dr}(n) = 1 + ((n - 1) \pmod 9)$$

---

### 3. Implementation (Java)

```java
public class DigitalRoot {
    // Optimal Approach: O(1) Time
    static int getDigitalRoot(int n) {
        if (n == 0) return 0;
        
        // n % 9 == 0 means the digital root is 9
        return (n % 9 == 0) ? 9 : (n % 9);
    }

    // Alternative one-liner
    static int getDigitalRootConcise(int n) {
        return (n == 0) ? 0 : 1 + (n - 1) % 9;
    }

    public static void main(String[] args) {
        int n = 1234;
        System.out.println("Digital Root of " + n + " is: " + getDigitalRoot(n));
    }
}
```

---

### 4. Complexity Analysis
* **Time Complexity:** $O(1)$ — Using the formula avoids any loops or recursion.
* **Space Complexity:** $O(1)$ — No extra space is required.

---

### Summary Table

| Method | Logic | Time Complexity | Space Complexity |
| :--- | :--- | :--- | :--- |
| **Iterative** | Loops until single digit | $O(\text{digits})$ | $O(1)$ |
| **Recursive** | Recursively sums digits | $O(\text{digits})$ | $O(\text{stack depth})$ |
| **Formula** | $n \pmod 9$ | $O(1)$ | $O(1)$ |

---

## Finding the Square Root of an Integer

The goal is to find the square root of a positive integer $n$. If $n$ is not a perfect square, the program should return the **floor** of $\sqrt{n}$.

---

### 1. Naive Approach (Linear Search)
The simplest way is to iterate through integers starting from 1 and check their squares.
* **Logic:** Start with $i=1$. While $i \times i \le n$, increment $i$. The answer is $i-1$.
* **Time Complexity:** $O(\sqrt{n})$
* **Space Complexity:** $O(1)$

---

### 2. Expected Approach (Binary Search)
Since the square of numbers is a monotonic function (it only increases), we can use **Binary Search** to find the square root in a range from $1$ to $n$.


**The Algorithm:**
1.  Initialize `low = 1`, `high = n`, and `ans = 0`.
2.  While `low <= high`:
    * Calculate `mid = (low + high) / 2`.
    * If `mid * mid == n`, return `mid`.
    * If `mid * mid < n`, store `mid` in `ans` and search the right half (`low = mid + 1`).
    * If `mid * mid > n`, search the left half (`high = mid - 1`).
3.  Return `ans`.


---

### 3. Java Implementation (Binary Search)

```java
public class SquareRoot {
    static int floorSqrt(int n) {
        // Base cases
        if (n == 0 || n == 1) return n;

        int low = 1, high = n, ans = 0;
        while (low <= high) {
            int mid = low + (high - low) / 2;

            // Use long to prevent overflow during mid * mid
            long square = (long) mid * mid;

            if (square == n) return mid;

            if (square < n) {
                ans = mid; // Potential answer
                low = mid + 1;
            } else {
                high = mid - 1;
            }
        }
        return ans;
    }

    public static void main(String[] args) {
        int n = 11;
        System.out.println("Floor square root of " + n + " is: " + floorSqrt(n));
    }
}
```

---

### 4. Mathematical Approach (Calculator Formula)
Calculators often use logarithms to find roots:
$$\sqrt{n} = e^{\frac{1}{2} \cdot \ln(n)}$$
* **Logic:** Use built-in `exp()` and `log()` functions.
* **Complexity:** $O(1)$ (effectively, though logarithmic internally).
* **Note:** Floating-point precision may require a quick check like `if ((res+1)*(res+1) <= n) res++;`.

---

### Summary Table

| Method | Time Complexity | Space Complexity | Best For |
| :--- | :--- | :--- | :--- |
| **Linear Search** | $O(\sqrt{n})$ | $O(1)$ | Small values of $n$ |
| **Binary Search** | $O(\log n)$ | $O(1)$ | Large values / Interviews |
| **Built-in / Math** | $O(1)$ | $O(1)$ | Real-world applications |

---

## Numbers with Exactly 3 Divisors

The problem is to find all numbers from $1$ to $n$ that have exactly three divisors.

---

### 1. The Mathematical Key
A number has exactly three divisors **if and only if it is the square of a prime number**.

**Why?**
* Every number has at least two divisors: 1 and itself.
* If a number $X$ is a square of a prime $p$ (i.e., $X = p^2$), its divisors are exactly **1, $p$, and $p^2$**.
* If $X$ is a square of a composite number (e.g., $16 = 4^2$), it will have more than three divisors (for 16: 1, 2, 4, 8, 16).
* If $X$ is not a perfect square, it will always have an even number of divisors.


---

### 2. Algorithmic Approach

To count such numbers up to $n$:
1.  Calculate the square root of $n$: $limit = \sqrt{n}$.
2.  Find all prime numbers up to $limit$.
3.  The count of these primes is the answer, because the square of each prime will be $\le n$ and will have exactly 3 divisors.

---

### 3. Java Implementation (Optimized)
Using the **Sieve of Eratosthenes** to find primes up to $\sqrt{n}$ is the most efficient way.

```java
import java.util.Arrays;

public class ThreeDivisors {
    public static int countExactly3Divisors(int n) {
        int limit = (int) Math.sqrt(n);
        boolean[] isPrime = new boolean[limit + 1];
        Arrays.fill(isPrime, true);
        isPrime[0] = isPrime[1] = false;

        // Sieve of Eratosthenes
        for (int p = 2; p * p <= limit; p++) {
            if (isPrime[p]) {
                for (int i = p * 2; i <= limit; i += p)
                    isPrime[i] = false;
            }
        }

        int count = 0;
        for (int i = 2; i <= limit; i++) {
            if (isPrime[i]) {
                count++;
            }
        }
        return count;
    }

    public static void main(String[] args) {
        int n = 100;
        System.out.println("Numbers with 3 divisors up to " + n + ": " + countExactly3Divisors(n));
    }
}
```

---

### 4. Complexity Analysis
* **Time Complexity:** $O(\sqrt{n} \log(\log \sqrt{n}))$ using the Sieve. This is much faster than checking every number up to $n$.
* **Space Complexity:** $O(\sqrt{n})$ to store the boolean array for the sieve.

---

### Comparison of Approaches

| Approach | Logic | Complexity |
| :--- | :--- | :--- |
| **Naive** | Check every number from 1 to $n$ and count its divisors. | $O(n \sqrt{n})$ |
| **Mathematical** | Find primes up to $\sqrt{n}$ and count them. | $O(\sqrt{n} \log \log \sqrt{n})$ |

---

## Checking Divisibility by 11 for Large Numbers

When dealing with extremely large numbers (stored as strings), we cannot use the standard modulo operator (`%`) because the value will exceed the limits of standard integer types (like `int` or `long`).

---

### 1. The Mathematical Rule
A number is divisible by 11 if the **difference** between the sum of digits at **odd positions** and the sum of digits at **even positions** is either **0 or a multiple of 11**.


**Example: 76945**
* Digits at odd positions (1st, 3rd, 5th): $7 + 9 + 5 = 21$
* Digits at even positions (2nd, 4th): $6 + 4 = 10$
* Difference: $21 - 10 = 11$
* Since 11 is divisible by 11, **76945 is divisible by 11**.

---

### 2. Why Does This Work?
This property stems from the fact that:
* $10^0 \equiv 1 \pmod{11}$
* $10^1 \equiv -1 \pmod{11}$
* $10^2 \equiv 1 \pmod{11}$
* $10^3 \equiv -1 \pmod{11}$

Because the powers of 10 alternate between $1$ and $-1$ when divided by 11, the remainder of a number like $abcd$ is simply $d - c + b - a$.

---

### 3. Java Implementation (String Input)

```java
public class DivisibilityBy11 {
    static boolean isDivisibleBy11(String s) {
        int oddSum = 0;
        int evenSum = 0;

        for (int i = 0; i < s.length(); i++) {
            // Convert character to integer value
            int digit = s.charAt(i) - '0';

            // We use the index to track position (0-based)
            if (i % 2 == 0) {
                oddSum += digit;
            } else {
                evenSum += digit;
            }
        }

        // Check if the absolute difference is divisible by 11
        return (oddSum - evenSum) % 11 == 0;
    }

    public static void main(String[] args) {
        String largeNum = "1234567589333892";
        System.out.println("Is divisible by 11: " + isDivisibleBy11(largeNum));
    }
}
```

---

### 4. Complexity Analysis
* **Time Complexity:** $O(n)$, where $n$ is the number of digits in the string. We traverse the string exactly once.
* **Space Complexity:** $O(1)$ (auxiliary space), as we only store two integer sums regardless of the input size.

---

### Summary Table

| Method | Best For | Complexity |
| :--- | :--- | :--- |
| **Direct Modulo (`%`)** | Small numbers (up to 18 digits) | $O(1)$ |
| **Digit Sum Difference** | Large numbers (String input) | $O(n)$ |

---

## Checking Divisibility by 13 for Large Numbers

Checking divisibility for large numbers (represented as strings) requires specialized logic to avoid integer overflow.

---

### 1. The 3-Digit Block Rule (Alternating Sum)
A number is divisible by 13 if the **alternating sum of its 3-digit blocks** (starting from the right) is divisible by 13.

**Example: 2,911,285**
1.  **Split into blocks of 3 from the right:** `285`, `911`, and `002`.
2.  **Apply alternating signs:** $+285 - 911 + 2 = -624$.
3.  **Check result:** $624 \div 13 = 48$. Since the result is an integer, the original number is divisible by 13.


---

### 2. The String-Based Modulo Approach
This is the most common way to handle large numbers in programming. You process the string from left to right, maintaining a "running remainder."

**The Logic:**
For each digit in the string:
`remainder = (remainder * 10 + current_digit) % 13`

**Example: "27"**
* Digit '2': `(0 * 10 + 2) % 13 = 2`
* Digit '7': `(2 * 10 + 7) % 13 = 27 % 13 = 1`
* Final remainder is 1 (not 0), so 27 is **not** divisible by 13.

---

### 3. Java Implementation (Optimal)

```java
public class DivisibilityBy13 {
    static boolean isDivisibleBy13(String s) {
        int remainder = 0;

        // Process each digit from left to right
        for (int i = 0; i < s.length(); i++) {
            int digit = s.charAt(i) - '0';
            
            // Running remainder formula
            remainder = (remainder * 10 + digit) % 13;
        }

        // If remainder is 0, the number is divisible
        return remainder == 0;
    }

    public static void main(String[] args) {
        String num = "2911285";
        if (isDivisibleBy13(num)) {
            System.out.println("The number is divisible by 13");
        } else {
            System.out.println("The number is NOT divisible by 13");
        }
    }
}
```

---

### 4. Complexity Analysis
* **Time Complexity:** $O(n)$ — You only need to pass through the string of $n$ digits once.
* **Space Complexity:** $O(1)$ — You only need a single integer variable to track the remainder.

---

### Comparison of Methods

| Method | Best For | Logic Complexity |
| :--- | :--- | :--- |
| **3-Digit Block** | Mental math or manual calculation | Medium |
| **String Modulo** | Programming and very large strings | Low |
| **Osculator Method** | Specialized number theory tasks | High |

---

## K-th Digit in $a^b$ (from the right)

The objective is to find the $k$-th digit from the right side of the value $a$ raised to the power $b$.

---

### 1. The Core Logic
Calculating $a^b$ directly for large values of $a$ and $b$ will cause an overflow (e.g., $100^{100}$ is far too large for any standard integer type). 

**The Insight:** To find the $k$-th digit from the right, we only need the last $k$ digits of the total value. We can obtain the last $k$ digits by calculating:
$$a^b \pmod{10^k}$$


Once we have the last $k$ digits, we can simply divide by $10^{k-1}$ to isolate the $k$-th digit.

---

### 2. Algorithmic Steps
1.  **Calculate the Modulo:** Compute $M = 10^k$.
2.  **Modular Exponentiation:** Calculate $P = a^b \pmod M$ using the **Binary Exponentiation** (or Power in Logarithmic Time) algorithm to prevent overflow and ensure efficiency.
3.  **Isolate the Digit:** The $k$-th digit is $\lfloor \frac{P}{10^{k-1}} \rfloor$.


---

### 3. Java Implementation

```java
public class KthDigit {
    static int getKthDigit(int a, int b, int k) {
        // Calculate 10^k
        long mod = (long) Math.pow(10, k);
        
        // Modular Exponentiation: (a^b) % mod
        long res = 1;
        long base = a % mod;
        
        while (b > 0) {
            // If b is odd, multiply res with base
            if ((b & 1) == 1) {
                res = (res * base) % mod;
            }
            // square the base and reduce b
            base = (base * base) % mod;
            b >>= 1; // b = b / 2
        }
        
        // At this point, 'res' contains the last k digits.
        // To get the k-th digit from the right:
        for (int i = 1; i < k; i++) {
            res /= 10;
        }
        
        return (int) (res % 10);
    }

    public static void main(String[] args) {
        int a = 3, b = 3, k = 1; // 3^3 = 27, 1st digit is 7
        System.out.println("The " + k + "-th digit is: " + getKthDigit(a, b, k));
        
        int a2 = 5, b2 = 2, k2 = 2; // 5^2 = 25, 2nd digit is 2
        System.out.println("The " + k2 + "-th digit is: " + getKthDigit(a2, b2, k2));
    }
}
```

---

### 4. Complexity Analysis
* **Time Complexity:** $O(\log b)$ because of the binary exponentiation process.
* **Space Complexity:** $O(1)$ as we only store a few long variables.

---

### Comparison of Methods

| Method | Limit | Complexity |
| :--- | :--- | :--- |
| **Simple Math (`Math.pow`)** | Small $a, b$ | $O(1)$ (but overflows easily) |
| **BigInteger (Java)** | Very large numbers | $O(b)$ (slow and memory-heavy) |
| **Modular Exponentiation** | Any $a, b$ | $O(\log b)$ (Optimal) |

---

## Representing a Fraction as a String (with Recurring Decimals)

The problem asks to convert a fraction $a/b$ into its decimal string representation. If the fractional part repeats, you must enclose the repeating sequence in parentheses.

---

### 1. The Core Challenge
Standard division stops once you reach the limit of a floating-point variable. However, to identify a **recurring (repeating) decimal**, you need to detect when a **remainder** repeats during the long division process.


---

### 2. Algorithmic Approach
1.  **Handle Signs:** Determine if the result is negative using XOR on the signs of $a$ and $b$.
2.  **Integer Part:** Calculate the quotient ($a / b$) and the initial remainder ($a \% b$).
3.  **Fractional Part:** * If the remainder is 0, the division is complete.
    * If not, add a decimal point and keep track of each remainder using a **HashMap (or Dictionary)**.
    * **The Map Key:** The remainder itself.
    * **The Map Value:** The index (position) in the string where that remainder first appeared.
4.  **Detecting Loops:** * If you encounter a remainder that is already in the Map, a cycle has begun. 
    * Insert an opening parenthesis `(` at the index stored in the Map and append a closing parenthesis `)` at the end.


---

### 3. Java Implementation

```java
import java.util.HashMap;

public class FractionToString {
    public static String convertFraction(int numerator, int denominator) {
        if (numerator == 0) return "0";

        StringBuilder res = new StringBuilder();
        // Handle negative results
        if ((numerator < 0) ^ (denominator < 0)) res.append("-");

        long num = Math.abs((long) numerator);
        long den = Math.abs((long) denominator);

        // Integral part
        res.append(num / den);
        long rem = num % den;
        if (rem == 0) return res.toString();

        res.append(".");
        
        // Map to store (remainder, index in string)
        HashMap<Long, Integer> map = new HashMap<>();
        while (rem != 0) {
            if (map.containsKey(rem)) {
                int index = map.get(rem);
                res.insert(index, "(");
                res.append(")");
                break;
            }

            map.put(rem, res.length());
            rem *= 10;
            res.append(rem / den);
            rem %= den;
        }

        return res.toString();
    }

    public static void main(String[] args) {
        System.out.println(convertFraction(50, 22)); // Output: 2.(27)
        System.out.println(convertFraction(1, 6));   // Output: 0.1(6)
    }
}
```

---

### 4. Complexity Analysis
* **Time Complexity:** $O(\text{denominator})$. In the worst case, the number of unique remainders when dividing by $b$ is $b-1$. Thus, the loop runs at most $b$ times.
* **Space Complexity:** $O(\text{denominator})$ to store the remainders in the HashMap.

---

### Example Trace: $1/6$
* `1 / 6` = `0`, Remainder = `1`
* String: `0.` | Map: `{1: 2}`
* `10 / 6` = `1`, Remainder = `4`
* String: `0.1` | Map: `{1: 2, 4: 3}`
* `40 / 6` = `6`, Remainder = `4`
* **Loop Detected!** Remainder `4` is already in the map at index `3`.
* Result: `0.1(6)`

---

## Finding the Recurring Sequence in a Fraction

When a fraction is converted into a decimal, it either terminates (like $1/2 = 0.5$) or eventually enters a cycle of repeating digits (like $1/3 = 0.333...$ or $1/6 = 0.1666...$). The goal of this algorithm is to extract exactly that repeating sequence.

---

### 1. The Logic: Tracking Remainders
The key observation is that **the decimal part starts repeating as soon as a remainder repeats.**

During manual long division:
1. You divide the numerator by the denominator.
2. You take the remainder, multiply it by 10, and divide again.
3. If you ever see a remainder you’ve seen before, the subsequent quotients will be identical to what followed the first time you saw that remainder.


---

### 2. Algorithmic Steps
1.  **Calculate Initial Remainder:** `rem = numerator % denominator`.
2.  **Use a Map:** Store each remainder and its **position** in the resulting string.
3.  **Loop until:**
    * The remainder becomes `0` (terminating decimal).
    * The remainder repeats (recurring decimal).
4.  **Extract Sequence:** If the remainder repeats, the recurring sequence starts from the index where that remainder was first seen.

---

### 3. Java Implementation

```java
import java.util.HashMap;

public class RecurringSequence {
    static String getRecurringSequence(int numr, int denr) {
        String res = ""; // To store the fractional digits
        HashMap<Integer, Integer> map = new HashMap<>();

        // Get initial remainder
        int rem = numr % denr;

        while (rem != 0 && !map.containsKey(rem)) {
            // Store remainder and its current position in 'res'
            map.put(rem, res.length());

            rem = rem * 10;
            int quotient = rem / denr;
            res += String.valueOf(quotient);
            
            rem = rem % denr;
        }

        if (rem == 0) return "No recurring sequence";
        
        // Return only the part from where the remainder first appeared
        return res.substring(map.get(rem));
    }

    public static void main(String[] args) {
        System.out.println("50/22: " + getRecurringSequence(50, 22)); // Output: 27
        System.out.println("1/6: " + getRecurringSequence(1, 6));   // Output: 6
    }
}
```

---

### 4. Complexity Analysis
* **Time Complexity:** $O(D)$, where $D$ is the denominator. The number of possible remainders when dividing by $D$ is finite ($0$ to $D-1$). Therefore, the loop will run at most $D$ times.
* **Space Complexity:** $O(D)$ to store the remainders and their positions in the HashMap.

---

### Why do we need the Position in the Map?
Consider $1/6$:
* $1 \div 6 = 0$ rem $1$.
* $10 \div 6 = 1$ rem **$4$**. (Digit: 1)
* $40 \div 6 = 6$ rem **$4$**. (Digit: 6)
* The remainder **$4$** repeats. If we didn't know its position, we might accidentally include the `1` (from index 0) in the sequence. By knowing the position, we correctly identify that only `6` repeats.


---

## Calculating $nPr$ (Permutations)

The term **$nPr$** refers to the number of ways to arrange $r$ elements selected from a total set of $n$ elements. In permutations, the **order of arrangement matters**.

---

### 1. The Formula
The mathematical formula for calculating permutations is:
$$nPr = \frac{n!}{(n - r)!}$$
Where:
* $n$ is the total number of items.
* $r$ is the number of items to be arranged.
* $!$ denotes the **factorial** (e.g., $5! = 5 \times 4 \times 3 \times 2 \times 1 = 120$).


---

### 2. Logic & Example
To find the number of ways to arrange 2 people out of 5 into 2 chairs:
* $n = 5$
* $r = 2$
* $5P2 = \frac{5!}{(5 - 2)!} = \frac{5!}{3!} = \frac{120}{6} = 20$.


---

### 3. Java Implementation
There are two ways to implement this: a naive approach (calculating full factorials) and an optimized approach (multiplying only the necessary terms).

#### Optimized Java Code
Instead of calculating $n!$, which can cause overflow quickly, we can simplify the formula:
$\frac{n!}{(n-r)!} = n \times (n-1) \times \dots \times (n-r+1)$

```java
public class Permutation {
    static long calculateNPr(int n, int r) {
        // Edge cases
        if (r > n) return 0;
        
        long result = 1;
        // Multiply n * (n-1) * ... for r terms
        for (int i = 0; i < r; i++) {
            result *= (n - i);
        }
        return result;
    }

    public static void main(String[] args) {
        int n = 5, r = 2;
        System.out.println("Value of " + n + "P" + r + " is " + calculateNPr(n, r));
    }
}
```

---

### 4. Complexity Analysis
* **Time Complexity:** $O(r)$ — We perform $r$ multiplications to get the result.
* **Space Complexity:** $O(1)$ — We only store the running product.

---

### Key Differences: Permutation vs. Combination

| Feature | Permutation ($nPr$) | Combination ($nCr$) |
| :--- | :--- | :--- |
| **Order** | Order Matters | Order Doesn't Matter |
| **Formula** | $\frac{n!}{(n-r)!}$ | $\frac{n!}{r!(n-r)!}$ |
| **Example** | Arranging books on a shelf | Picking players for a team |

---

## Calculating $nCr$ (Combinations)

The term **$nCr$** represents the number of ways to choose $r$ elements from a set of $n$ elements **without regard to order**. This is also known as the **Binomial Coefficient**.

---

### 1. The Formula
The standard formula for combinations is:
$$nCr = \frac{n!}{r! \times (n - r)!}$$


**Key Observation:** $nCr$ is always equal to $nC(n-r)$. For example, picking 2 people out of 5 is the same as picking the 3 people who will be left behind ($5C2 = 5C3$).

---

### 2. Implementation Strategies

#### A. Naive Approach (Factorial)
Calculate $n!$, $r!$, and $(n-r)!$ separately and apply the formula.
* **Risk:** Factorials grow extremely fast. $20!$ already exceeds the limit of a 64-bit `long` in Java.

#### B. Recursive Approach (Pascal's Identity)
Using the property: $nCr = (n-1)C(r-1) + (n-1)Cr$

#### C. Optimized Iterative Approach (Preferred)
You can calculate $nCr$ in $O(r)$ time by simplifying the formula:
$$nCr = \frac{n \times (n-1) \times \dots \times (n-r+1)}{1 \times 2 \times \dots \times r}$$

---

### 3. Java Implementation (Optimized)

This approach avoids full factorial calculation by multiplying and dividing in the same loop, which helps prevent early overflow.

```java
public class Combination {
    static long calculateNCR(int n, int r) {
        if (r > n) return 0;
        if (r == 0 || r == n) return 1;

        // Optimization: nCr is same as nC(n-r)
        if (r > n / 2) {
            r = n - r;
        }

        long res = 1;
        for (int i = 1; i <= r; i++) {
            // Formula: res = res * (n - i + 1) / i
            res = res * (n - i + 1) / i;
        }
        return res;
    }

    public static void main(String[] args) {
        int n = 5, r = 2;
        System.out.println("5C2 = " + calculateNCR(n, r)); // Output: 10
    }
}
```

---

### 4. Complexity Analysis
* **Time Complexity:** $O(r)$ — The loop runs $r$ times.
* **Space Complexity:** $O(1)$ — No extra data structures are used.

---

### Summary of Differences

| Feature | Permutation ($nPr$) | Combination ($nCr$) |
| :--- | :--- | :--- |
| **Focus** | Arrangement / Order | Selection / Grouping |
| **Formula** | $\frac{n!}{(n-r)!}$ | $\frac{n!}{r!(n-r)!}$ |
| **Result** | Higher value | Lower value (divided by $r!$) |

[Image comparing permutations and combinations for picking 2 letters from {A, B, C}]

---

## Pascal's Triangle

**Pascal's Triangle** is a triangular array of binomial coefficients. Each number in the triangle is the sum of the two numbers directly above it.


---

### 1. Key Properties
* **Symmetry:** The triangle is symmetric; the numbers on the left side are mirror images of those on the right.
* **Sum of Rows:** The sum of the numbers in the $n$-th row is $2^n$.
* **Binomial Expansion:** The $n$-th row contains the coefficients of $(a + b)^n$. For example, the 2nd row (1, 2, 1) corresponds to $1a^2 + 2ab + 1b^2$.
* **Edge Values:** Every row starts and ends with **1**.

[Image showing the relationship between Pascal's Triangle and Binomial Expansion]

---

### 2. Implementation Approaches

#### A. Dynamic Programming ($O(n^2)$ Time, $O(n^2)$ Space)
We can store the triangle in a 2D array where `mat[i][j] = mat[i-1][j-1] + mat[i-1][j]`.

#### B. Space-Optimized ($O(n^2)$ Time, $O(1)$ Space)
Instead of storing previous rows, we can calculate each element in a row using the previous element's value:
$$nCi = nC(i-1) \times \frac{n - i + 1}{i}$$

---

### 3. Java Implementation (Space-Optimized)

This approach prints the triangle row by row without using any extra arrays or matrices.

```java
public class PascalsTriangle {
    public static void printPascal(int n) {
        for (int line = 1; line <= n; line++) {
            int C = 1; // Used to represent lineCi
            for (int i = 1; i <= line; i++) {
                // The first value in a line is always 1
                System.out.print(C + " ");
                C = C * (line - i) / i;
            }
            System.out.println();
        }
    }

    public static void main(String[] args) {
        int n = 5;
        printPascal(n);
    }
}
```

**Output for $n=5$:**
```text
1 
1 1 
1 2 1 
1 3 3 1 
1 4 6 4 1
```

---

### 4. Complexity Analysis
* **Time Complexity:** $O(n^2)$ — Two nested loops to calculate each element of each row.
* **Space Complexity:** $O(1)$ — We only use a few variables (`C`, `i`, `line`) regardless of the triangle's size (excluding the space for printing).

---

## Finding All Factors of a Natural Number

A **factor** (or divisor) of a natural number $n$ is a number that divides $n$ exactly, leaving no remainder. For example, the factors of 10 are 1, 2, 5, and 10.

---

### 1. The Logic: Divisors Occur in Pairs
The most efficient way to find factors is to realize that they always come in pairs. If $a$ is a factor of $n$, then $b = n/a$ is also a factor.

**Example: $n = 36$**
* $1 \times 36 = 36$
* $2 \times 18 = 36$
* $3 \times 12 = 36$
* $4 \times 9 = 36$
* $6 \times 6 = 36$ (Special case: Perfect square)

By the time we reach $\sqrt{n}$ (which is 6 for 36), we have already found all unique factors because any factor larger than $\sqrt{n}$ would have been paired with a factor smaller than $\sqrt{n}$.

---

### 2. Algorithmic Steps ($O(\sqrt{n})$)
1.  **Iterate** from $i = 1$ up to $\sqrt{n}$.
2.  **Check Divisibility:** If $n \% i == 0$:
    * Add $i$ to the list.
    * If $i$ is not the same as $n/i$, add $n/i$ to the list as well.
3.  **Sort (Optional):** The pairs will be found out of order (e.g., 1, 10, 2, 5), so you may need to sort them if an ordered list is required.

---

### 3. Java Implementation

```java
import java.util.*;

public class FindFactors {
    public static List<Integer> getFactors(int n) {
        List<Integer> factors = new ArrayList<>();
        
        // Loop runs from 1 to sqrt(n)
        for (int i = 1; i <= Math.sqrt(n); i++) {
            if (n % i == 0) {
                factors.add(i); // Add the smaller factor
                
                // Add the paired factor if it's different
                if (i != n / i) {
                    factors.add(n / i);
                }
            }
        }
        
        Collections.sort(factors); // Sorting for cleaner output
        return factors;
    }

    public static void main(String[] args) {
        System.out.println("Factors of 10: " + getFactors(10));
        System.out.println("Factors of 36: " + getFactors(36));
    }
}
```

---

### 4. Complexity Analysis
* **Time Complexity:** $O(\sqrt{n})$ — We only iterate up to the square root of $n$.
* **Space Complexity:** $O(k)$, where $k$ is the number of factors. This space is used to store the results.

---

### Summary Table: Naive vs. Optimized

| Method | Range | Time Complexity | Efficiency |
| :--- | :--- | :--- | :--- |
| **Naive** | $1$ to $n$ | $O(n)$ | Slow for large $n$ |
| **Optimized** | $1$ to $\sqrt{n}$ | $O(\sqrt{n})$ | Much faster |

[Image comparing O(n) vs O(sqrt n) growth curves]

---

## Prime Factorization

**Prime Factorization** is the process of finding which prime numbers multiply together to make a original number. For example, the prime factors of 60 are $2 \times 2 \times 3 \times 5$.


---

### 1. Efficient Trial Division ($O(\sqrt{n})$)
The most common way to find prime factors for a single number is to divide it by 2 until it's odd, then check every odd number up to $\sqrt{n}$.

#### The Logic
1.  **Divide by 2:** While $n$ is even, the prime factor is 2. Divide $n$ by 2 repeatedly.
2.  **Iterate Odds:** Start from $i=3$ up to $\sqrt{n}$. If $i$ divides $n$, then $i$ is a prime factor. Divide $n$ by $i$ repeatedly to remove all occurrences of this prime.
3.  **Final Prime:** If $n > 2$ after the loop, the remaining $n$ is itself a prime factor.

---

### 2. Java Implementation (Trial Division)

```java
import java.util.*;

public class PrimeFactors {
    public static void printPrimeFactors(int n) {
        // Step 1: Handle factor 2
        while (n % 2 == 0) {
            System.out.print(2 + " ");
            n /= 2;
        }

        // Step 2: Handle odd factors from 3 to sqrt(n)
        for (int i = 3; i <= Math.sqrt(n); i += 2) {
            while (n % i == 0) {
                System.out.print(i + " ");
                n /= i;
            }
        }

        // Step 3: If n is still > 2, then n is prime
        if (n > 2) {
            System.out.print(n);
        }
    }

    public static void main(String[] args) {
        int n = 315;
        System.out.print("Prime factors of " + n + " are: ");
        printPrimeFactors(n); // Output: 3 3 5 7
    }
}
```

---

### 3. Sieve-Based Optimization ($O(\log n)$)
If you need to find prime factors for many numbers (e.g., in an array), it is faster to precompute the **Smallest Prime Factor (SPF)** for every number using a modified Sieve of Eratosthenes.


1.  **Precompute SPF:** Build an array where `spf[i]` stores the smallest prime factor of $i$.
2.  **Query:** To factorize $n$, repeatedly look up `spf[n]`, add it to your list, and update $n = n / spf[n]$ until $n=1$.

---

### Complexity Comparison

| Approach | Time Complexity (Single Query) | Best Used For |
| :--- | :--- | :--- |
| **Trial Division** | $O(\sqrt{n})$ | Finding factors for one large number. |
| **Sieve/SPF** | $O(\log n)$* | Factorizing many numbers in a range. |

*\*Requires $O(n \log \log n)$ precomputation time.*

---

## Finding the Largest Prime Factor

The goal is to find the maximum prime number that divides a given positive integer $n$ (up to $10^{15}$).

---

### 1. The Logic: Optimized Trial Division
To find the largest prime factor efficiently, we follow a process of elimination:

1.  **Remove Even Factors:** Since 2 is the only even prime, we divide $n$ by 2 repeatedly until it's odd.
2.  **Remove Factors of 3:** Similarly, divide by 3 until it is no longer a factor.
3.  **Check Primes in the Form $6k \pm 1$:** All primes greater than 3 can be expressed as $6k-1$ or $6k+1$. This allows us to skip all even numbers and multiples of 3, making the loop significantly faster.
4.  **Final Prime:** After checking all potential factors up to $\sqrt{n}$, if $n$ is still greater than 1, the remaining $n$ is the largest prime factor.


---

### 2. Java Implementation

```java
public class LargestPrimeFactor {
    static long getLargestPrimeFactor(long n) {
        long maxPrime = -1;

        // Step 1: Remove all factors of 2
        while (n % 2 == 0) {
            maxPrime = 2;
            n /= 2;
        }

        // Step 2: Remove all factors of 3
        while (n % 3 == 0) {
            maxPrime = 3;
            n /= 3;
        }

        // Step 3: Check odd factors of the form 6k +/- 1 up to sqrt(n)
        for (long i = 5; i * i <= n; i += 6) {
            while (n % i == 0) {
                maxPrime = i;
                n /= i;
            }
            while (n % (i + 2) == 0) {
                maxPrime = i + 2;
                n /= (i + 2);
            }
        }

        // Step 4: If n is still > 1, it is a prime factor
        if (n > 1) {
            maxPrime = n;
        }

        return maxPrime;
    }

    public static void main(String[] args) {
        long n = 15;
        System.out.println("Largest prime factor of " + n + " is: " + getLargestPrimeFactor(n));
        
        n = 28; // Factors: 2, 2, 7
        System.out.println("Largest prime factor of " + n + " is: " + getLargestPrimeFactor(n));
    }
}
```

---

### 3. Complexity Analysis
* **Time Complexity:** $O(\sqrt{n})$ — In the worst case (when $n$ is prime), the loop runs up to $\sqrt{n}$. For large numbers like $10^{15}$, $\sqrt{n}$ is roughly $3.16 \times 10^7$, which is well within the limits for a standard execution time.
* **Space Complexity:** $O(1)$ — We only use a constant amount of extra space for variables.

---

### Comparison: Why $6k \pm 1$?
By checking only $6k \pm 1$, we skip approximately **66%** of the numbers compared to checking every integer, and **33%** compared to checking every odd integer.

| Method | Sequence of Divisors Checked | Efficiency |
| :--- | :--- | :--- |
| **All Inteers** | 2, 3, 4, 5, 6, 7, 8... | Lowest |
| **Odd Integers** | 2, 3, 5, 7, 9, 11, 13... | Moderate |
| **$6k \pm 1$** | 2, 3, 5, 7, 11, 13, 17... | **Highest** |

[Image comparing number of iterations for different trial division strategies]

---


## Modular Exponentiation

**Modular Exponentiation** is used to calculate $(x^n) \pmod M$ efficiently. This is a fundamental operation in cryptography (like RSA) and competitive programming because $x^n$ grows extremely large, often exceeding the storage capacity of standard data types.

---

### 1. The Core Idea: Binary Exponentiation
The goal is to calculate $x^n$ by breaking the power down into smaller parts using the properties of exponents:
* If $n$ is **even**: $x^n = (x^{n/2})^2$
* If $n$ is **odd**: $x^n = x \times x^{n-1}$

By halving the power at each step, we reduce the number of multiplications from $n$ to $\log n$.


---

### 2. Properties of Modulo
The property $(a \times b) \pmod M = ((a \pmod M) \times (b \pmod M)) \pmod M$ allows us to apply the modulo operator at every multiplication step, ensuring our intermediate results never overflow.

---

### 3. Iterative Algorithm (Step-by-Step)
1.  Initialize `res = 1`.
2.  While $n > 0$:
    * If $n$ is **odd**, multiply `res` with $x$ and take modulo: `res = (res * x) % M`.
    * **Square** the base $x$: `x = (x * x) % M`.
    * **Halve** the exponent $n$: `n = n / 2`.
3.  Return `res`.

[Image illustrating the iterative steps of modular exponentiation for 2^10 mod 7]

---

### 4. Java Implementation

```java
class ModularExponentiation {
    static long power(long x, long n, long M) {
        long res = 1;     // Initialize result
        x = x % M;        // Update x if it is more than or equal to M

        if (x == 0) return 0; // In case x is divisible by M

        while (n > 0) {
            // If n is odd, multiply x with result
            if ((n & 1) != 0) {
                res = (res * x) % M;
            }

            // n must be even now
            n = n >> 1; // n = n/2
            x = (x * x) % M; // x = x^2
        }
        return res;
    }

    public static void main(String[] args) {
        long x = 2, n = 10, M = 5;
        System.out.println("Result: " + power(x, n, M)); // Output: 4
    }
}
```

---

### 5. Complexity Analysis
* **Time Complexity:** $O(\log n)$ — Since the exponent $n$ is halved in every iteration.
* **Space Complexity:** $O(1)$ — Only a constant amount of extra space is used for variables.

---

### Summary Table

| Feature | Naive Approach | Modular Exponentiation |
| :--- | :--- | :--- |
| **Logic** | Multiply $x$, $n$ times | Halve power using squaring |
| **Time Complexity** | $O(n)$ | $O(\log n)$ |
| **Overflow Risk** | High (if modulo not applied) | Low (modulo applied at each step) |

[Image comparing O(n) and O(log n) growth for large exponents]

---

## $n^{th}$ Catalan Number

**Catalan numbers** form a sequence of natural numbers that occur in various counting problems, often where structures are defined recursively. The first few numbers in the sequence are: **1, 1, 2, 5, 14, 42, 132...**

---

### 1. Applications of Catalan Numbers
These numbers appear in many combinatorial problems:
* **Balanced Parentheses:** Number of ways to arrange $n$ pairs of correctly matched parentheses.
* **Binary Search Trees (BST):** Number of possible BSTs that can be formed with $n$ keys.
* **Polygon Triangulation:** Number of ways to divide a convex polygon with $n+2$ sides into triangles.
* **Mountain Ranges:** Number of ways to form a mountain range with $n$ upstrokes and $n$ downstrokes.

---

### 2. Mathematical Formula
The $n^{th}$ Catalan number $C_n$ can be expressed using the binomial coefficient:

$$C_n = \frac{1}{n+1} \binom{2n}{n} = \frac{(2n)!}{(n+1)!n!}$$

---

### 3. Java Implementation ($O(n)$ Approach)
While you can use Dynamic Programming ($O(n^2)$), the most efficient way to find a single $C_n$ is using the binomial coefficient logic.

```java
class CatalanNumber {
    // Returns value of Binomial Coefficient C(n, k)
    static long binomialCoeff(int n, int k) {
        long res = 1;
        if (k > n - k) k = n - k;
        for (int i = 0; i < k; ++i) {
            res *= (n - i);
            res /= (i + 1);
        }
        return res;
    }

    // A function to find nth catalan number in O(n) time
    static long findCatalan(int n) {
        // Calculate 2nCn
        long c = binomialCoeff(2 * n, n);
        // Return 2nCn / (n + 1)
        return c / (n + 1);
    }

    public static void main(String[] args) {
        int n = 5;
        System.out.println(n + "th Catalan number is: " + findCatalan(n));
    }
}
```

---

### 4. Complexity Analysis
* **Time Complexity:** $O(n)$ — Calculating the binomial coefficient takes linear time.
* **Space Complexity:** $O(1)$ — Only a few variables are used.

---

### Summary Table: Different Approaches

| Method | Recurrence Relation | Time Complexity | Space Complexity |
| :--- | :--- | :--- | :--- |
| **Recursive** | $C_n = \sum C_i C_{n-i-1}$ | Exponential | $O(n)$ |
| **Dynamic Programming** | Tabulation of above | $O(n^2)$ | $O(n)$ |
| **Binomial Coefficient** | $\frac{1}{n+1} \binom{2n}{n}$ | **$O(n)$** | **$O(1)$** |

---


## Binomial Coefficient (nCr) using Dynamic Programming

The **Binomial Coefficient** $C(n, k)$ represents the number of ways to choose $k$ elements from a set of $n$ elements. It is also the coefficient of the $x^k$ term in the expansion of $(1 + x)^n$.

---

### 1. The Recursive Formula
The logic for solving this with Dynamic Programming (DP) is based on **Pascal's Identity**:

$$C(n, k) = C(n-1, k-1) + C(n-1, k)$$

**Base Cases:**
* $C(n, 0) = 1$ (Only 1 way to choose 0 items)
* $C(n, n) = 1$ (Only 1 way to choose all $n$ items)


---

### 2. Why Use Dynamic Programming?
If we use simple recursion, we solve the same subproblems multiple times. For example, to calculate $C(5, 2)$, we would calculate $C(3, 1)$ several times. 

* **Optimal Substructure:** $C(n, k)$ is built from smaller solutions.
* **Overlapping Subproblems:** The same $C(i, j)$ values are needed repeatedly.


---

### 3. Java Implementation (Tabulation)
This approach uses a 2D array to store results of subproblems in a bottom-up manner.

```java
class BinomialCoefficient {
    static int nCr(int n, int k) {
        int[][] dp = new int[n + 1][k + 1];

        for (int i = 0; i <= n; i++) {
            for (int j = 0; j <= Math.min(i, k); j++) {
                // Base Cases
                if (j == 0 || j == i) {
                    dp[i][j] = 1;
                } 
                // Using previously calculated values
                else {
                    dp[i][j] = dp[i - 1][j - 1] + dp[i - 1][j];
                }
            }
        }
        return dp[n][k];
    }

    public static void main(String[] args) {
        int n = 5, k = 2;
        System.out.println("Value of C(" + n + ", " + k + ") is " + nCr(n, k));
    }
}
```

---

### 4. Space Optimization ($O(k)$ Space)
Notice that to calculate a row in Pascal's triangle, we only need the previous row. We can use a 1D array and update it from right to left to avoid using values from the "current" iteration.

```java
static int optimizednCr(int n, int k) {
    int[] dp = new int[k + 1];
    dp[0] = 1; // nC0 is always 1

    for (int i = 1; i <= n; i++) {
        // Update from right to left
        for (int j = Math.min(i, k); j > 0; j--) {
            dp[j] = dp[j] + dp[j - 1];
        }
    }
    return dp[k];
}
```

---

### 5. Complexity Comparison

| Approach | Time Complexity | Space Complexity |
| :--- | :--- | :--- |
| **Recursive** | $O(2^n)$ | $O(n)$ (stack space) |
| **DP Tabulation** | $O(n \times k)$ | $O(n \times k)$ |
| **Optimized DP** | **$O(n \times k)$** | **$O(k)$** |

---

## Power Set (Subsets of a Set)

The **Power Set** $P(S)$ of a set $S$ is the set of all possible subsets of $S$, including the empty set and $S$ itself. If a set has $n$ elements, its power set will contain $2^n$ elements.

---

### 1. Examples
* **Input:** $S = \{a, b\}$
* **Output:** $\emptyset, \{a\}, \{b\}, \{a, b\}$
* **Total Subsets:** $2^2 = 4$


---

### 2. Method 1: Bit Manipulation (Iterative)
This approach maps each subset to a binary number from $0$ to $2^n - 1$. For a set of size $n$, each bit in an $n$-bit integer represents whether an element is "in" (1) or "out" (0) of a subset.

**Steps:**
1.  Loop from $i = 0$ to $2^n - 1$.
2.  For each $i$, check which bits are set (equal to 1).
3.  If the $j^{th}$ bit is set, include the $j^{th}$ element of the set in the current subset.

[Image mapping binary numbers 000-111 to subsets of {a, b, c}]

---

### 3. Java Implementation (Bit Manipulation)

```java
import java.util.*;

class PowerSet {
    static void printPowerSet(char[] set, int n) {
        // Run from i = 000..0 to 111..1
        long powerSetSize = (long) Math.pow(2, n);

        for (int i = 0; i < powerSetSize; i++) {
            System.out.print("{ ");
            for (int j = 0; j < n; j++) {
                // Check if j-th bit is set in i
                if ((i & (1 << j)) > 0) {
                    System.out.print(set[j] + " ");
                }
            }
            System.out.println("}");
        }
    }

    public static void main(String[] args) {
        char[] set = {'a', 'b', 'c'};
        printPowerSet(set, 3);
    }
}
```

---

### 4. Method 2: Backtracking (Recursive)
In this approach, for every element, we have two choices:
1.  **Include** the element in the current subset.
2.  **Exclude** the element from the current subset.


---

### 5. Complexity Analysis
* **Time Complexity:** $O(n \times 2^n)$ — There are $2^n$ subsets, and for each subset, we iterate through $n$ elements.
* **Space Complexity:** $O(n)$ — To store the current subset (or recursion stack space).

---

### Summary Table

| Feature | Bit Manipulation | Backtracking (Recursive) |
| :--- | :--- | :--- |
| **Paradigm** | Iterative / Bitwise | Recursive / Decision Tree |
| **Ease of Use** | Best for small $n$ ($n \le 31$ or $63$) | More flexible for large $n$ or filtering |
| **Complexity** | $O(n \times 2^n)$ | $O(n \times 2^n)$ |

---

