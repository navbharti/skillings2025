## Analysis of Algorithms

Analysis of algorithms is the process of finding the computational complexity of algorithms—specifically the amount of time, storage, or other resources needed to execute them.

---

### 1. Why Analyze Algorithms?
The goal is to predict the resources required by an algorithm to solve a specific problem. By analyzing different algorithms for the same task, we can:
* **Predict Performance:** Determine how an algorithm will scale with larger inputs.
* **Compare Solutions:** Select the most efficient approach for a given problem.
* **Identify Bottlenecks:** Optimize specific parts of the code to improve overall speed.

---

### 2. Asymptotic Analysis
Asymptotic analysis defines the mathematical boundaries of an algorithm's performance. It focuses on the **order of growth** of the resource consumption as the input size ($n$) increases toward infinity.


#### The Three Main Notations:
1.  **Big-O Notation ($O$):** Represents the **Upper Bound**. It guarantees that the algorithm will not take longer than this time. (Worst Case).
2.  **Omega Notation ($\Omega$):** Represents the **Lower Bound**. It guarantees that the algorithm will take at least this much time. (Best Case).
3.  **Theta Notation ($\Theta$):** Represents the **Tight Bound**. It describes the exact growth rate of the algorithm. (Average Case).


---

### 3. Types of Analysis
* **Worst Case Analysis:** The maximum number of steps taken on any instance of size $n$. This is the most common metric because it provides a "guarantee."
* **Best Case Analysis:** The minimum number of steps taken on any instance of size $n$. Usually not very useful in real-world scenarios.
* **Average Case Analysis:** The average number of steps taken over all possible inputs of size $n$. This involves more complex mathematical calculations.

---

### 4. Time vs. Space Complexity
1.  **Time Complexity:** The amount of time taken by an algorithm to run as a function of the length of the input.
2.  **Space Complexity:** The amount of memory space required by the algorithm in its life cycle. This includes:
    * **Instruction Space:** Memory for the code.
    * **Data Space:** Memory for variables and constants.
    * **Stack Space:** Memory for function calls (especially critical in recursion).

---

### 5. Common Complexity Classes

| Notation | Name | Example |
| :--- | :--- | :--- |
| $O(1)$ | Constant | Accessing an array element |
| $O(\log n)$ | Logarithmic | Binary Search |
| $O(n)$ | Linear | Linear Search |
| $O(n \log n)$ | Linearithmic | Merge Sort / Quick Sort |
| $O(n^2)$ | Quadratic | Bubble Sort / Insertion Sort |
| $O(2^n)$ | Exponential | Recursive Fibonacci |

---

### 6. Analyzing Loops (Rules of Thumb)
* **Single Loop:** If a loop runs from $1$ to $n$ and increases by a constant, it is $O(n)$.
* **Nested Loops:** If a loop of $n$ is inside another loop of $n$, it is $O(n^2)$.
* **Divide and Conquer:** If the loop variable is divided or multiplied by a constant (e.g., `i = i / 2`), it is $O(\log n)$.

---

## What is an Algorithm and Why is Analysis Important?

An **Algorithm** is a step-by-step procedure or a set of rules to be followed in calculations or other problem-solving operations. In computer science, it is a finite sequence of well-defined instructions to solve a specific problem.

---

### 1. Key Characteristics of an Algorithm
To be effective, an algorithm should generally satisfy these criteria:
* **Input:** Zero or more quantities are externally supplied.
* **Output:** At least one quantity is produced.
* **Definiteness:** Each instruction is clear and unambiguous.
* **Finiteness:** The algorithm terminates after a finite number of steps.
* **Effectiveness:** Every instruction must be basic enough to be carried out in principle by a person using only pencil and paper.


---

### 2. Why is Analysis of Algorithms Important?
Analysis provides a **theoretical estimation** of the resources required by an algorithm. While factors like security, modularity, and user-friendliness are vital, they often depend on the underlying performance.

#### A. Predict Scalability
Software that works perfectly for 10 users might crash when 1 million users access it. Analysis helps predict how an algorithm behaves as the input size ($n$) grows. 


#### B. Compare Different Solutions
Most problems can be solved in multiple ways (e.g., Linear Search vs. Binary Search). Analysis allows us to compare these methods mathematically without having to write code and run benchmarks for every single one.

#### C. Resource Management (Time & Space)
* **Time:** How long does it take to run? (Efficiency)
* **Space:** How much memory does it need? (Economy)

#### D. Performance as "Currency"
Think of performance as a currency. If you have a highly performant algorithm, you can "spend" that extra speed on adding more features, better security, or a more complex user interface. Without performance, adding these features makes the software unusable.

---

### 3. Practical Example: Searching for a Name
* **Linear Search:** Checking names one by one until you find the right one.
* **Binary Search:** In a sorted list, jumping to the middle and eliminating half the names in each step.

For a phonebook of 1,000,000 names:
* **Linear Search** might take 1,000,000 checks (Worst Case).
* **Binary Search** will take only about 20 checks.


---

### Summary Table: The Goal of Analysis

| Goal | Description |
| :--- | :--- |
| **Efficiency** | Measuring time complexity to ensure the software is fast. |
| **Optimization** | Identifying parts of the algorithm that consume the most resources. |
| **Comparison** | Choosing the most suitable algorithm for a specific task. |
| **Reliability** | Ensuring the algorithm doesn't fail under heavy load (Big Data). |

---

## Order of Growth in Asymptotic Analysis

In the context of the GATE syllabus and algorithm analysis, **Order of Growth** describes how the execution time or space requirements of an algorithm increase as the input size ($n$) grows. It allows us to ignore hardware-specific details and focus on the inherent efficiency of the logic.

---

### 1. Defining "Faster Growth"
A function $f(n)$ is said to grow faster than $g(n)$ if, as $n$ approaches infinity, the ratio of $g(n)$ to $f(n)$ becomes zero:

$$\lim_{n \to \infty} \frac{g(n)}{f(n)} = 0$$

Essentially, $f(n)$ will eventually "overtake" $g(n)$ regardless of any constant multipliers.


---

### 2. How to Find the Order of Growth
When analyzing a complex mathematical expression for time complexity, follow these two rules:
1.  **Ignore Lower-Order Terms:** In the expression $4n^2 + 3n + 100$, the $3n$ and $100$ become insignificant as $n$ becomes very large.
2.  **Ignore Constants:** The coefficient $4$ is ignored because it doesn't change the shape of the growth curve.

**Result:** The order of growth is $n^2$.

---

### 3. Comparison of Standard Functions
For GATE preparation, it is crucial to remember the standard hierarchy of growth rates. From slowest growing (most efficient) to fastest growing (least efficient):

$$c < \log(\log n) < \log n < n^{1/3} < n^{1/2} < n < n \log n < n^2 < n^3 < 2^n < n! < n^n$$

> **Note:** Here, $c$ represents any constant value.

---

### 4. Practice Examples

| Expression | Dominant Term | Order of Growth |
| :--- | :--- | :--- |
| $100n + \log n$ | $100n$ | $O(n)$ |
| $n^2 + 10^6 n$ | $n^2$ | $O(n^2)$ |
| $2^n + n^{100}$ | $2^n$ | $O(2^n)$ |
| $\frac{n}{\log n} + \log n$ | $\frac{n}{\log n}$ | $O(\frac{n}{\log n})$ |


---

### 5. Why it Matters for GATE
In competitive exams like GATE, you are often asked to:
* **Arrange functions** in increasing or decreasing order of growth.
* **Identify the tightest upper bound** for a given recursive or iterative algorithm.
* **Determine if $f(n) = O(g(n))$** based on their growth rates.

---


## Asymptotic Analysis and Input Size

Asymptotic analysis is the primary method used to evaluate an algorithm's performance based on the size of the input ($n$), rather than the actual time taken on a specific machine. It measures the **order of growth** of time or space complexity.

---

### 1. The Machine-Independence Principle
A common mistake in comparing algorithms is running them on different machines. 
* **Scenario:** Imagine running Linear Search on a supercomputer (A) and Binary Search on an old laptop (B).
* **Small Input:** For 100 items, the supercomputer might finish Linear Search in 20 seconds, while the old laptop takes nearly 2 hours for Binary Search due to its slow processor.
* **Large Input:** For 1 billion items, the supercomputer would take **6.3 years** for Linear Search, while the old laptop finishes Binary Search in just **8.3 hours**.


Asymptotic analysis focuses on this long-term behavior where the algorithm's logic (logarithmic vs. linear) eventually outweighs the machine's speed.

---

### 2. Why Use Asymptotic Analysis?
* **Scalability:** It tells us how the algorithm will handle "Big Data."
* **Simplicity:** It allows us to ignore hardware constants and focus on the formula.
* **Consistency:** It provides a universal language for developers to discuss efficiency.

---

### 3. Understanding Asymptotic Notations
To mathematically describe the order of growth, we use three specific notations:

#### Big-O Notation ($O$) - The Upper Bound
It defines the maximum time an algorithm will take. It is used to describe the **Worst Case** scenario. If an algorithm is $O(n^2)$, it will never perform worse than $n^2$ for large inputs.

#### Omega Notation ($\Omega$) - The Lower Bound
It defines the minimum time an algorithm will take. It describes the **Best Case** scenario. If an algorithm is $\Omega(n)$, it will take at least $n$ steps.

#### Theta Notation ($\Theta$) - The Tight Bound
It defines the exact growth rate. An algorithm is $\Theta(f(n))$ if it is both $O(f(n))$ and $\Omega(f(n))$. This is used for **Average Case** analysis.

---

### 4. Limitations of Asymptotic Analysis
1.  **Ignores Constants:** It doesn't distinguish between $2n$ and $1000n$. In real-world low-latency systems, that $500x$ difference matters.
2.  **Focuses on Large $n$:** Some algorithms are asymptotically slower but perform much better for small, everyday input sizes (e.g., Insertion Sort vs. Quick Sort).
3.  **Hardware Realities:** It doesn't account for modern hardware features like cache memory, branch prediction, or parallel processing.

---

### Summary of Common Complexities

| Input Size ($n$) | $O(\log n)$ | $O(n)$ | $O(n \log n)$ | $O(n^2)$ |
| :--- | :--- | :--- | :--- | :--- |
| **10** | 3 steps | 10 steps | 30 steps | 100 steps |
| **1,000** | 10 steps | 1k steps | 10k steps | 1M steps |
| **1,000,000** | 20 steps | 1M steps | 20M steps | 1T steps |

---

## Worst, Average, and Best Case Analysis

When analyzing an algorithm, we look at how it performs under different input scenarios. This helps us understand its boundaries and typical behavior.

---

### 1. Worst Case Analysis (Upper Bound)
This is the **maximum** number of operations an algorithm will perform for any input of size $n$. It is the most common form of analysis because it provides a performance guarantee.
* **Example (Linear Search):** The worst case occurs when the element is not in the array or is at the very end. The algorithm must check every single element ($n$ comparisons).
* **Notation:** Usually expressed with **Big-O** ($O$).


---

### 2. Best Case Analysis (Lower Bound)
This is the **minimum** number of operations an algorithm will perform for an input of size $n$. While interesting, it is rarely used in real-world software engineering because it doesn't help us prepare for high-load scenarios.
* **Example (Linear Search):** The best case occurs when the target element is at the very first index. The algorithm finds it immediately (1 comparison).
* **Notation:** Usually expressed with **Omega** ($\Omega$).


---

### 3. Average Case Analysis
This is the **expected** number of operations. It involves taking the sum of operations for all possible inputs and dividing by the total number of inputs.
* **Example (Linear Search):** If the element is equally likely to be at any position, the average number of comparisons is roughly $n/2$. 
* **Notation:** Usually expressed with **Theta** ($\Theta$).


---

### Comparison Table: Why Focus on the Worst Case?

| Case | Reliability | Calculation | Importance |
| :--- | :--- | :--- | :--- |
| **Worst** | **Highest** | Identifies the bottleneck input. | Crucial for system stability. |
| **Average** | **Medium** | Mathematically complex; requires input distribution. | Useful for algorithms like Quick Sort. |
| **Best** | **Lowest** | Doesn't account for failures or delays. | Minimal value in performance planning. |

---

### 4. Algorithm Sensitivity Examples

Some algorithms perform the same regardless of the input, while others are highly sensitive:

1.  **Merge Sort:** $O(n \log n)$ in all cases (Best, Worst, and Average). It always divides and merges the same way.
2.  **Quick Sort:** * **Best:** $O(n \log n)$ (Pivot divides array in half).
    * **Worst:** $O(n^2)$ (Array is already sorted or reverse-sorted).
3.  **Insertion Sort:**
    * **Best:** $O(n)$ (Array is already sorted).
    * **Worst:** $O(n^2)$ (Array is reverse-sorted).

---

# Asymptotic Notations

## Big O Analysis of Algorithms

**Big O Notation** is a mathematical notation used to describe the **upper bound** of an algorithm's time or space complexity. It provides a worst-case scenario, guaranteeing that the algorithm will not perform worse than a specific rate as the input size ($n$) grows.


---

### 1. Mathematical Definition
Given two functions $f(n)$ and $g(n)$, we say that $f(n)$ is **$O(g(n))$** if there exist positive constants $c$ and $n_0$ such that:
$$0 \le f(n) \le c \cdot g(n) \text{ for all } n \ge n_0$$

This means that $g(n)$ is an asymptotic upper bound for $f(n)$.

---

### 2. How to Calculate Big O for an Expression
To find the Big O notation of a polynomial or complex expression, follow these two simplification rules:
1.  **Drop Constants:** $O(2n)$ becomes $O(n)$. $O(500)$ becomes $O(1)$.
2.  **Keep the Dominant Term:** In $O(n^2 + 5n + 10)$, the $n^2$ term grows the fastest. So, the complexity is $O(n^2)$.

**Example:** If $f(n) = 3n^3 + 4n^2 + 10$, the dominant term is $3n^3$. After dropping the constant $3$, we get **$O(n^3)$**.

---

### 3. Common Big O Complexities

| Notation | Name | Typical Example |
| :--- | :--- | :--- |
| **$O(1)$** | Constant | Accessing an array element by index. |
| **$O(\log n)$** | Logarithmic | Binary Search in a sorted array. |
| **$O(n)$** | Linear | Iterating through an array once. |
| **$O(n \log n)$** | Superlinear | Efficient sorting (Merge Sort, Heap Sort). |
| **$O(n^2)$** | Quadratic | Nested loops (Bubble Sort, Selection Sort). |
| **$O(2^n)$** | Exponential | Recursive Fibonacci, Generating all subsets. |
| **$O(n!)$** | Factorial | Generating all permutations of a string. |


---

### 4. Properties of Big O
* **Reflexivity:** $f(n) = O(f(n))$ (A function is its own upper bound).
* **Transitivity:** If $f(n) = O(g(n))$ and $g(n) = O(h(n))$, then $f(n) = O(h(n))$.
* **Sum Rule:** $O(f(n)) + O(g(n)) = O(\max(f(n), g(n)))$.
* **Product Rule:** $O(f(n)) \times O(g(n)) = O(f(n) \times g(n))$.

---

### 5. Big O vs. Omega vs. Theta

| Notation | Formal Name | Meaning |
| :--- | :--- | :--- |
| **$O(g(n))$** | Big O | **Upper Bound** (Worst Case) |
| **$\Omega(g(n))$** | Big Omega | **Lower Bound** (Best Case) |
| **$\Theta(g(n))$** | Big Theta | **Tight Bound** (Average Case) |

---

## Big Theta ($\Theta$) Notation

**Big Theta Notation** provides an **asymptotically tight bound** for an algorithm's growth rate. Unlike Big O (which only provides an upper limit) or Big Omega (which only provides a lower limit), Big Theta bounds a function from both the top and the bottom.


---

### 1. Mathematical Definition
A function $f(n)$ is said to be in $\Theta(g(n))$ if there exist positive constants $c_1, c_2,$ and $n_0$ such that:
$$0 \le c_1 \cdot g(n) \le f(n) \le c_2 \cdot g(n) \text{ for all } n \ge n_0$$

In simpler terms, $f(n)$ grows at the same rate as $g(n)$ as $n$ approaches infinity. If an algorithm is $\Theta(g(n))$, it is both $O(g(n))$ and $\Omega(g(n))$.

---

### 2. Why is Big Theta Preferred?
Big Theta is the most precise way to describe an algorithm's complexity because it eliminates the ambiguity of "loose" bounds.
* **Example:** If an algorithm takes exactly $5n^2$ steps, saying it is $O(n^3)$ is mathematically correct (since $n^3$ is an upper bound), but it's not helpful. Saying it is $\Theta(n^2)$ is the most accurate description of its behavior.

---

### 3. Practical Example: Linear Search
In a linear search of an array of size $n$:
1.  **Best Case:** $\Omega(1)$ (found at the first index).
2.  **Worst Case:** $O(n)$ (not found or at the last index).
3.  **Average Case:** If we assume the key is equally likely to be at any position or absent, the average number of comparisons is approximately $(n+1)/2$.
    * After removing constants, the average case complexity is **$\Theta(n)$**.

---

### 4. Comparison of Notations

| Notation | Bound Type | Use Case |
| :--- | :--- | :--- |
| **Big O ($O$)** | Upper Bound | Guaranteeing "it won't take longer than this." |
| **Big Omega ($\Omega$)** | Lower Bound | Stating "it will take at least this long." |
| **Big Theta ($\Theta$)** | Tight Bound | Describing the **exact** growth rate. |

[Image comparing O, Omega, and Theta notation graphs side-by-side]

---

### 5. Common Tight Bounds
* **Binary Search:** Worst-case is **$\Theta(\log n)$**.
* **Merge Sort:** All cases (best, worst, average) are **$\Theta(n \log n)$**.
* **Nested Loops (Square Matrix):** Printing all elements is **$\Theta(n^2)$**.

---

## Big Omega ($\Omega$) Notation

**Big Omega Notation** is used to define the **asymptotic lower bound** of an algorithm's time or space complexity. It provides a "best-case" or "at least" guarantee, stating that an algorithm will not perform faster than a certain rate for large input sizes ($n$).


---

### 1. Mathematical Definition
Given two functions $f(n)$ and $g(n)$, we say that $f(n)$ is **$\Omega(g(n))$** if there exist positive constants $c$ and $n_0$ such that:
$$f(n) \ge c \cdot g(n) \text{ for all } n \ge n_0$$

This means that $g(n)$ is a lower bound for $f(n)$. Effectively, the algorithm takes at least $c \cdot g(n)$ time.

---

### 2. Practical Examples
* **Linear Search:** In the best case (when the element is at the first index), the complexity is **$\Omega(1)$**.
* **Printing All Pairs:** For an array of size $n$, if you use two nested loops to print every pair, the execution time is always **$\Omega(n^2)$** because it must perform at least $n \times n$ operations regardless of the array's content.
* **Insertion Sort:** In the best case (when the array is already sorted), the complexity is **$\Omega(n)$**.

---

### 3. Big-Omega ($\Omega$) vs. Little-Omega ($\omega$)
While both represent lower bounds, they differ in how "tight" that bound is:

| Parameter | Big-Omega ($\Omega$) | Little-Omega ($\omega$) |
| :--- | :--- | :--- |
| **Bound Type** | Loose or Equal Lower Bound | **Strict** Lower Bound |
| **Formal Logic** | $f(n) \ge c \cdot g(n)$ | $f(n) > c \cdot g(n)$ |
| **Growth Rate** | $f(n)$ grows at least as fast as $g(n)$. | $f(n)$ grows **strictly faster** than $g(n)$. |

[Image comparing Big-Omega and Little-Omega notation growth curves]

---

### 4. Why Use Big Omega?
While Big-O (Worst Case) is more common for system reliability, Big Omega is useful for:
1.  **Lower Bound Proofs:** Proving that a problem *cannot* be solved faster than a certain complexity (e.g., comparison-based sorting is $\Omega(n \log n)$).
2.  **Optimistic Planning:** Understanding how the system performs under ideal input conditions.
3.  **Tight Bound Derivation:** If an algorithm is both $O(g(n))$ and $\Omega(g(n))$, we can conclude it is $\Theta(g(n))$.

---

### Summary Table: Asymptotic Bounds

| Notation | Type of Bound | Analogy |
| :--- | :--- | :--- |
| **$O(g(n))$** | Upper Bound | $\le$ (Less than or equal to) |
| **$\Omega(g(n))$** | Lower Bound | $\ge$ (Greater than or equal to) |
| **$\Theta(g(n))$** | Tight Bound | $=$ (Equivalent to) |

---

## Understanding Time Complexity with Simple Examples

Time complexity is a way to describe how the running time of an algorithm increases as the size of the input data ($n$) increases. It is **not** the actual time in seconds, but a measure of the number of operations performed.


---

### 1. Real-World Analogy: Finding a Pen
Imagine you gave your pen to one student in a class of 100 and now need to find it:

* **$O(n)$ (Linear):** You ask each student one by one. If there are $n$ students, you might have to ask $n$ times.
* **$O(n^2)$ (Quadratic):** You ask the first student, and then you ask that student about every other student in the class, then move to the second student and repeat.
* **$O(\log n)$ (Logarithmic):** You divide the class in half and ask, "Is the pen on the left or right?" You keep dividing the remaining group in half until only one person is left.

---

### 2. Is Time Complexity the Same as Execution Time?
**No.** Actual execution time is machine-dependent.
* **Machine A** (Fast) might run an $O(n^2)$ algorithm faster than **Machine B** (Slow) runs an $O(n)$ algorithm for a very small input.
* However, as $n$ grows (e.g., 1 million), the $O(n)$ algorithm will eventually be much faster than the $O(n^2)$ algorithm, regardless of the machine's speed.

---

### 3. Code Examples and Analysis

#### Example 1: Constant Time — $O(1)$
The code does the same amount of work regardless of any input.
```cpp
cout << "Hello World"; // Executes exactly once
```
**Time Complexity:** $O(1)$

#### Example 2: Linear Time — $O(n)$
The number of operations grows directly with $n$.
```cpp
for (int i = 1; i <= n; i++) {
    cout << "Hello World !!!\n"; // Executes 'n' times
}
```
**Time Complexity:** $O(n)$


---

### 4. How to Calculate Time Complexity
To find the complexity of a function, we look at the "cost" of each line and how many times it repeats.

**Algorithm: Summing an Array**
1.  Initialize `sum = 0` (1 operation)
2.  Start loop from `0` to `n-1` (n+1 comparisons)
3.  Inside loop: `sum = sum + A[i]` (n additions)
4.  Return `sum` (1 operation)

**Total Cost:** $T(n) = 1 + (n+1) + n + 1 = 2n + 3$
In Big O notation, we ignore constants and lower-order terms. 
**Final Complexity:** **$O(n)$**

---

### 5. Common Complexities in Brief

| Complexity | Name | Example |
| :--- | :--- | :--- |
| **$O(1)$** | Constant | Accessing a specific array index. |
| **$O(\log n)$** | Logarithmic | Finding a word in a dictionary (Binary Search). |
| **$O(n)$** | Linear | Reading a book page by page. |
| **$O(n \log n)$** | Superlinear | Efficient sorting algorithms like Merge Sort. |
| **$O(n^2)$** | Quadratic | Comparing every element with every other element (Nested Loops). |


---

## Auxiliary Space vs. Space Complexity (G-Fact 86)

It is common to see the terms "Space Complexity" and "Auxiliary Space" used interchangeably, but they represent different measurements of an algorithm's memory usage.

---

### 1. Key Definitions

* **Auxiliary Space:** This refers specifically to the **extra** space or temporary space used by an algorithm while it is running. It does *not* include the memory required to store the initial input.
* **Space Complexity:** This is the **total** space taken by the algorithm relative to the input size. It is the sum of the input space and the auxiliary space.
    $$\text{Space Complexity} = \text{Input Space} + \text{Auxiliary Space}$$

---

### 2. Why the Distinction Matters
When comparing algorithms, **Auxiliary Space** is often a better criterion for efficiency. 

**Example: Sorting Algorithms**
Consider an array of size $n$. To store the array itself, we already need $O(n)$ space.
* **Merge Sort:** Uses $O(n)$ extra space to merge sub-arrays. Its auxiliary space is $O(n)$, and its space complexity is $O(n + n) = O(n)$.
* **Heap Sort:** Sorts the array "in-place" without needing extra arrays. Its auxiliary space is $O(1)$, and its space complexity is $O(n + 1) = O(n)$.


If we only looked at space complexity ($O(n)$ for both), we might think they are equally efficient in memory. However, looking at auxiliary space shows that Heap Sort is much more memory-efficient.

---

### 3. Space in Recursive vs. Iterative Calls
The call stack plays a major role in space analysis:

* **Recursive Stack Space:** Each recursive call adds a new layer to the stack. A function that recurses $n$ times (like a recursive factorial) will use **$O(n)$** auxiliary space because all those calls exist in memory at the same time.
* **Iterative Space:** If a function calls another helper function inside a loop (but not recursively), those calls do not exist simultaneously. Once a helper function returns, its stack space is cleared. Thus, the auxiliary space remains **$O(1)$**.

---

### 4. General Rule of Thumb

| Structure | Space Required |
| :--- | :--- |
| **Simple Variable** | $O(1)$ |
| **1D Array of size $n$** | $O(n)$ |
| **2D Array of size $n \times n$** | $O(n^2)$ |
| **Recursion Depth $n$** | $O(n)$ |


---

# Analyzing Examples

## How to Analyze Loops for Complexity Analysis

Analyzing loops involves determining the number of operations performed as a function of the input size ($n$). The goal is to find the **order of growth** of the loop execution.

---

### 1. Constant Time — $O(1)$
A loop is $O(1)$ if it runs a fixed number of times, regardless of the input size.
```cpp
for (int i = 1; i <= 100; i++) {
    // O(1) operations
}
```
**Complexity:** $O(1)$

---

### 2. Linear Time — $O(n)$
A loop is $O(n)$ if the loop variable is incremented or decremented by a **constant amount** ($c$).
```cpp
for (int i = 1; i <= n; i += c) {
    // O(1) operations
}
```
As $i$ goes from $1$ to $n$ in steps of $c$, the loop runs $n/c$ times. In Big O, we drop the constant $1/c$, resulting in **$O(n)$**.

---

### 3. Quadratic Time — $O(n^2)$
This typically occurs with **nested loops**, where both the outer and inner loops run $n$ times.
```cpp
for (int i = 1; i <= n; i++) {
    for (int j = 1; j <= n; j++) {
        // O(1) operations
    }
}
```

**Total operations:** $n \times n = n^2$.
**Complexity:** $O(n^2)$

---

### 4. Logarithmic Time — $O(\log n)$
A loop is $O(\log n)$ if the loop variable is **multiplied or divided** by a constant amount ($c > 1$) in each iteration.
```cpp
for (int i = 1; i <= n; i *= c) {
    // O(1) operations
}
// OR
for (int i = n; i > 0; i /= c) {
    // O(1) operations
}
```
The number of iterations is the number of times you can multiply $1$ by $c$ before reaching $n$, which is $\log_c n$.

---

### 5. Log Log Time — $O(\log \log n)$
This occurs when the loop variable increases or decreases **exponentially**.
```cpp
for (int i = 2; i <= n; i = i * i) {
    // O(1) operations
}
// OR
for (int i = n; i > 1; i = sqrt(i)) {
    // O(1) operations
}
```
The number of iterations here grows extremely slowly relative to $n$.

---

### 6. Combining Consecutive Loops
If you have two loops one after the other, you **add** their complexities.
```cpp
for (int i = 1; i <= m; i++) { ... } // O(m)
for (int i = 1; i <= n; i++) { ... } // O(n)
```
**Total Complexity:** $O(m + n)$. If $m = n$, it simplifies to $O(2n) \rightarrow \mathbf{O(n)}$.

---

### 7. Handling If-Else inside Loops
When analyzing loops with conditional statements, we generally focus on the **Worst-Case Scenario**. 
* Assume the condition that leads to the most operations is always true.
* Example: In a search loop, assume the item is at the very end or not present at all.

[Image comparing linear vs logarithmic vs quadratic growth for loop analysis]

---

## Analyzing Complexity of Recurrence Relations

When an algorithm is recursive, its time complexity is often expressed as a **recurrence relation**. This is a mathematical equation that defines the running time of a problem of size $n$ in terms of smaller versions of the same problem.


---

### 1. What is a Recurrence Relation?
A recurrence relation consists of:
1.  **Recursive part:** The work done by recursive calls (e.g., $2T(n/2)$).
2.  **Non-recursive part:** The work done within the current call (e.g., partitioning, merging, or printing).
3.  **Base case:** The time taken for the smallest possible input (usually $T(1) = \text{constant}$).

**Example (Merge Sort):** $$T(n) = 2T(n/2) + \Theta(n)$$
* $2T(n/2)$: Sorting two halves.
* $\Theta(n)$: Merging the two sorted halves.

---

### 2. Common Methods to Solve Recurrences

#### A. Substitution Method
1.  **Guess** the form of the solution (e.g., $O(n \log n)$).
2.  Use **Mathematical Induction** to prove that the guess is correct.
* *Best for:* Verifying a known or suspected complexity.

#### B. Recursion Tree Method
This method visualizes the recurrence as a tree where:
* Each node represents the cost of a single subproblem.
* You sum the costs of all nodes at each level.
* The total complexity is the sum of costs across all levels.


* *Best for:* Getting a visual intuition and a good guess for the substitution method.

#### C. Master Theorem
The Master Theorem provides a "shortcut" for recurrences of the form:
$$T(n) = aT(n/b) + f(n)$$
Where $a \ge 1, b > 1,$ and $f(n)$ is the work done outside the recursion.

There are three cases based on the comparison between $f(n)$ and $n^{\log_b a}$:
1.  **Case 1:** If $f(n)$ grows slower, the complexity is $\Theta(n^{\log_b a})$.
2.  **Case 2:** If $f(n)$ grows at the same rate, the complexity is $\Theta(n^{\log_b a} \log n)$.
3.  **Case 3:** If $f(n)$ grows faster, the complexity is $\Theta(f(n))$.


---

### 3. Comparison of Methods

| Method | Ease of Use | Accuracy |
| :--- | :--- | :--- |
| **Substitution** | Hard (requires a guess) | Very High |
| **Recursion Tree** | Moderate | High (good for intuition) |
| **Master Theorem** | Easy (formula-based) | Limited (only for specific forms) |

---

### 4. Important Examples

| Algorithm | Recurrence | Complexity |
| :--- | :--- | :--- |
| **Binary Search** | $T(n) = T(n/2) + c$ | $O(\log n)$ |
| **Merge Sort** | $T(n) = 2T(n/2) + n$ | $O(n \log n)$ |
| **Matrix Multiplication (Strassen)** | $T(n) = 7T(n/2) + n^2$ | $O(n^{2.81})$ |
| **Towers of Hanoi** | $T(n) = 2T(n-1) + 1$ | $O(2^n)$ |

---

## Introduction to Amortized Analysis

**Amortized Analysis** is a technique used to find the average cost of an operation over a sequence of operations. Unlike "Average Case" analysis, which uses probability, amortized analysis provides a **guaranteed** average performance in the worst-case sequence, ensuring that rare expensive operations are offset by many cheap ones.

---

### 1. The Dynamic Array Example
The most common application is a dynamic array (like `std::vector` in C++ or `ArrayList` in Java).
* **Cheap Operation:** Inserting an element when there is space available ($O(1)$).
* **Expensive Operation:** When the array is full, we must create a new array (usually double the size) and copy all $n$ elements ($O(n)$).

If we only looked at the worst case, we might say insertion is $O(n)$. However, because the expensive resize happens so infrequently, the "amortized" cost for any single insertion is actually **$O(1)$**.


---

### 2. Three Methods of Amortized Analysis

#### A. Aggregate Method
You calculate the total cost of a sequence of $n$ operations ($T(n)$) and divide it by $n$.
$$\text{Amortized Cost} = \frac{T(n)}{n}$$
* *Example:* In $n$ stack operations (Push, Pop, Multipop), the total cost is $O(n)$, so each operation is amortized $O(1)$.

#### B. Accounting Method (Banker's Method)
You assign different "charges" to operations:
* **Overcharge** cheap operations and save the extra as "credit."
* **Use credit** later to pay for expensive operations so they don't "cost" the system anything extra at the time of execution.
* *Rule:* The total credit in the system must never be negative.


#### C. Potential Method (Physicist's Method)
This uses a "Potential Function" ($\Phi$) to represent the energy or "stored work" in a data structure. 
$$\text{Amortized Cost} = \text{Actual Cost} + \Delta\Phi$$
* When an operation is cheap, it increases the potential ($\Delta\Phi > 0$).
* When an operation is expensive, it decreases the potential ($\Delta\Phi < 0$), paying for the extra work.

---

### 3. Comparison of Methods

| Method | Approach | Key Concept |
| :--- | :--- | :--- |
| **Aggregate** | Global | Total cost / Number of operations. |
| **Accounting** | Local | Saving credits from cheap tasks for expensive ones. |
| **Potential** | State-based | Using a mathematical function to track stored energy. |

---

### 4. Key Applications
* **Hash Tables:** Resizing when the load factor is exceeded.
* **Disjoint Set Union (DSU):** Path compression and union by rank.
* **Splay Trees / Red-Black Trees:** Self-adjusting operations.
* **Priority Queues:** Specifically Fibonacci Heaps.

[Image comparing worst-case vs amortized-case complexity for various data structures]

