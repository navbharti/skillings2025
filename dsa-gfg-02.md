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

