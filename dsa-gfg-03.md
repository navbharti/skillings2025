## Array Data Structure: A Comprehensive Guide

An **Array** is a fundamental linear data structure that stores elements of the same type in **contiguous memory locations**. This physical arrangement allows for efficient data access and manipulation.


---

### 1. Key Characteristics
* **Contiguous Storage:** In languages like C/C++ and Java (primitives), elements are stored side-by-side. In Python or JavaScript, the array stores *references* to objects in a contiguous block.
* **Fixed vs. Dynamic:** Standard arrays have a fixed size defined at creation. Dynamic arrays (like `ArrayList` in Java or `vector` in C++) can resize themselves automatically.
* **Zero-based Indexing:** Most modern languages start counting array positions from 0.

---

### 2. Core Advantages
* **Random Access:** You can access the $i$-th element in **$O(1)$** time using the formula: $\text{Address} = \text{Base Address} + (i \times \text{Size of Element})$.
* **Cache Friendliness:** Because elements are stored together, they exhibit high **locality of reference**, making them much faster for the CPU to process than linked structures.

---

### 3. Basic Operations and Complexities

| Operation | Time Complexity | Description |
| :--- | :--- | :--- |
| **Access** | $O(1)$ | Direct access via index. |
| **Search** | $O(n)$ | Linear search (unsorted). $O(\log n)$ for Binary Search (sorted). |
| **Insertion** | $O(n)$ | Requires shifting elements to make room. |
| **Deletion** | $O(n)$ | Requires shifting elements to fill the gap. |

[Image illustrating element shifting during array insertion and deletion]

---

### 4. Implementation in Different Languages
* **C++:** `int arr[5]` (Fixed) or `std::vector<int>` (Dynamic).
* **Java:** `int[] arr = new int[5]` (Fixed) or `ArrayList<Integer>` (Dynamic).
* **Python:** `list` (Always dynamic).
* **JavaScript:** `Array` (Always dynamic).

---

### 5. Common Applications
Arrays serve as the building blocks for many advanced data structures and algorithms:
* **Other Data Structures:** Implementing Stacks, Queues, Heaps, and Hash Tables.
* **Matrix Operations:** Representing 2D data like images or spreadsheets.
* **CPU Scheduling:** Maintaining a list of processes.
* **Lookup Tables:** Storing precomputed values for fast retrieval.

---

### 6. Popular Array Problems to Practice
* **Basic:** Reversing an array, finding the maximum/minimum element.
* **Intermediate:** Two Pointers technique, Sliding Window problems, Prefix Sum.
* **Advanced:** Trapping Rain Water, Next Permutation, Median of two sorted arrays.

---

## Introduction to Arrays: Data Structure and Algorithms

An **Array** is a linear data structure that collects items of the same type and stores them in **contiguous memory locations**. It is one of the most fundamental structures in programming, used to organize data efficiently so that related values can be easily searched or sorted.


---

### 1. Key Terminology
* **Array Element:** The individual data items stored in the array.
* **Array Index:** A numerical value used to identify the location of an element. In most languages, indexing is **zero-based** (the first element is at index 0).

---

### 2. Memory Representation
Because arrays use contiguous memory, the computer can calculate the exact memory address of any element if it knows the base address (the start of the array). This enables **Random Access**, allowing you to jump to any element instantly.


---

### 3. Classification of Arrays

#### A. Based on Size
* **Fixed-Size Arrays:** The size is determined at the time of declaration and cannot be changed during execution (e.g., `int arr[5]` in C++).
* **Dynamic Arrays:** The size can grow or shrink as needed during runtime (e.g., `vector` in C++, `ArrayList` in Java, or `list` in Python).

#### B. Based on Dimensions
* **1D Array:** Elements are stored in a single row or linear sequence.
* **2D Array (Matrix):** An array of arrays, organized into rows and columns.
* **3D Array:** Can be thought of as a cube of data or an array of 2D matrices.


---

### 4. Why Use Arrays?
Imagine tracking the marks of 100 students. Creating 100 separate variables (`student1`, `student2`, etc.) is impractical. An array allows you to store all 100 values in a single variable (`marks[100]`), making it easier to:
* Iterate through all values using a loop.
* Sort the data.
* Pass the entire collection to a function.

---

### 5. Common Operations
* **Traversal:** Visiting every element in the array once.
* **Insertion:** Adding an element at a specific index (requires shifting other elements).
* **Deletion:** Removing an element (requires shifting elements to fill the gap).
* **Searching:** Finding the index of a specific value (Linear or Binary Search).

[Image illustrating element shifting during insertion and deletion in an array]

---


## Applications, Advantages, and Disadvantages of Arrays

Arrays are one of the most widely used linear data structures due to their simplicity and efficient performance in specific scenarios. Below is a breakdown of why they are used and where they fall short.

---

### 1. Applications of Arrays
Arrays serve as the backbone for many complex systems and algorithms:
* **Data Storage & Retrieval:** Provides constant-time $O(1)$ access to any element using its index.
* **Building Other Data Structures:** Used to implement Stacks, Queues, Heaps, and Hash Tables.
* **Matrices & Image Processing:** 2D arrays represent pixels in images and are used for mathematical matrix computations.
    * **Dynamic Programming:** Storing intermediate results (memoization) to solve complex problems efficiently.
* **Data Buffers:** Temporarily holding data like network packets or file streams before they are processed.

---

### 2. Advantages of Arrays
* **Random Access:** Any element can be accessed immediately if the index is known, regardless of the array's size.
* **Cache Friendliness:** Because elements are stored in contiguous memory, CPUs can pre-fetch data more effectively, leading to faster execution.
    * **Memory Efficiency:** No extra memory is needed for pointers or links (unlike Linked Lists), meaning almost 100% of the allocated space is used for actual data.
* **Hardware Compatibility:** Most hardware architectures are optimized to work with contiguous memory blocks, making arrays highly performant.

---

### 3. Disadvantages of Arrays
* **Fixed Size:** Standard arrays have a static size. To increase capacity, you must create a new, larger array and copy all existing elements—a time-consuming $O(n)$ process.
* **Expensive Insertions/Deletions:** Adding or removing an element (except at the very end) requires shifting all subsequent elements to maintain order, resulting in $O(n)$ complexity.
    [Image illustrating element shifting during array insertion and deletion]
* **Memory Waste/Shortage:** If you allocate too much space, memory is wasted. If you allocate too little, the program may crash or require expensive resizing.
* **Contiguous Memory Requirement:** For very large arrays, it may be difficult to find a single, unbroken block of free memory, even if the total free memory is sufficient.

---

### Summary Table

| Feature | Performance | Note |
| :--- | :--- | :--- |
| **Access** | $O(1)$ | Best in class for direct access. |
| **Search (Sorted)** | $O(\log n)$ | Very efficient with Binary Search. |
| **Insertion/Deletion** | $O(n)$ | Generally slow due to shifting. |
| **Memory Overhead** | Low | No pointers required. |

# Array in Different Language
- Arrays in C
- Vector in C++ STL
- Arrays in Java
- ArrayList in Java
- List in Python

---

## Arrays in C Programming

In C, an **Array** is a linear data structure that stores a fixed-size sequence of elements of the same data type in **contiguous memory locations**. This structure is essential for managing large sets of related data under a single name.


---

### 1. Key Characteristics
* **Fixed Size:** The size of a C array must be known at compile time and cannot be changed during execution.
* **Same Data Type:** All elements in the array must be of the same type (e.g., all `int`, all `float`).
* **Contiguous Memory:** Elements are placed immediately next to each other in memory, which allows for fast access.
* **Random Access:** Any element can be accessed instantly using its index.

---

### 2. Declaration and Initialization

#### A. Declaration
To declare an array, you specify the data type, the name, and the number of elements in square brackets `[]`.
```c
int marks[5]; // Declares an array of 5 integers
```

#### B. Initialization
You can assign values to the array at the time of declaration.
```c
int arr[5] = {10, 20, 30, 40, 50}; // Full initialization
int arr[] = {1, 2, 3};             // Size is automatically 3
int arr[5] = {10, 20};             // Partial: remaining elements are 0
```
[Image showing partial array initialization in C where remaining spots are filled with zeros]

---

### 3. Accessing and Updating Elements
C uses **zero-based indexing**, meaning the first element is at index `0` and the last is at `size - 1`.
* **Access:** `int x = arr[2];` (Gets the 3rd element).
* **Update:** `arr[0] = 100;` (Changes the 1st element to 100).

---

### 4. Array Traversal
To visit every element, a `for` loop is typically used:
```c
for (int i = 0; i < 5; i++) {
    printf("%d ", arr[i]);
}
```

---

### 5. Finding the Size of an Array
Since C arrays do not store their own size, you can calculate it using the `sizeof()` operator:
```c
int length = sizeof(arr) / sizeof(arr[0]);
```
* `sizeof(arr)` gives the total bytes of the array.
* `sizeof(arr[0])` gives the bytes of a single element.

---

### 6. Multidimensional Arrays
C supports arrays with multiple dimensions, most commonly 2D arrays (matrices).
```c
int matrix[2][3] = { {1, 2, 3}, {4, 5, 6} };
```

---

### 7. Important Notes
* **Array Bounds:** C does **not** check if an index is valid. Accessing `arr[10]` on an array of size 5 will lead to **Undefined Behavior** (crashes or garbage data).
* **Array vs. Pointer:** In most contexts, the name of an array acts as a constant pointer to its first element.

---

## Vector in C++ STL

A **Vector** is a dynamic array provided by the C++ Standard Template Library (STL). Unlike traditional arrays, vectors can resize themselves automatically when an element is inserted or deleted, with their storage being handled automatically by the container.


---

### 1. Key Features
* **Dynamic Sizing:** Automatically grows when elements are added beyond its current capacity.
* **Contiguous Storage:** Just like arrays, vectors store elements in adjacent memory locations, allowing for $O(1)$ access time.
* **Iterators:** Supports various iterators to traverse and manipulate data.
* **Bounds Checking:** While `v[i]` does not check bounds (faster), `v.at(i)` provides bounds-checked access and throws an exception if the index is out of range.

---

### 2. Declaration and Initialization
To use vectors, you must include the `<vector>` header.
```cpp
#include <vector>
std::vector<int> v1;               // Empty vector of integers
std::vector<int> v2(5, 10);        // Vector of size 5, all elements initialized to 10
std::vector<int> v3 = {1, 2, 3};   // Initialization using initializer list
```

---

### 3. Essential Functions

#### A. Capacity Functions
* `size()` – Returns the number of elements currently in the vector.
* `capacity()` – Returns the size of the storage space currently allocated.
* `empty()` – Returns `true` if the vector contains no elements.
* `shrink_to_fit()` – Reduces the capacity to fit the current size.

[Image illustrating the difference between vector size and vector capacity]

#### B. Element Access
* `at(i)` – Access element at index `i` with bounds checking.
* `operator[]` – Access element at index `i` (no bounds checking).
* `front()` – Access the first element.
* `back()` – Access the last element.

#### C. Modifiers
* `push_back(val)` – Adds an element to the end.
* `pop_back()` – Removes the last element.
* `insert(it, val)` – Inserts an element at a specific position (using an iterator).
* `erase(it)` – Removes an element at a specific position.
* `clear()` – Removes all elements from the vector.

[Image showing push_back and pop_back operations in a C++ vector]

---

### 4. Performance (Time Complexity)
* **Random Access:** $O(1)$
* **Insertion/Deletion at the end:** Amortized $O(1)$
* **Insertion/Deletion at the middle/beginning:** $O(n)$ (requires shifting elements)

---

### 5. 2D Vectors (Multidimensional)
A 2D vector is essentially a vector of vectors. It is highly flexible as each "row" can have a different number of "columns" (jagged array).
```cpp
std::vector<std::vector<int>> matrix = {
    {1, 2, 3},
    {4, 5},
    {6, 7, 8, 9}
};
```

---

## Arrays in Java

In Java, an **Array** is a collection of elements of the same data type stored in **contiguous memory locations**. Java treats arrays as **objects**, and they are always allocated memory on the **heap**.


---

### 1. Key Characteristics
* **Same Data Type:** Can hold primitive types (e.g., `int`, `char`) or non-primitive types (e.g., `String`, objects).
* **Contiguous Memory:**
    * **Primitives:** Actual values are stored side-by-side.
    * **Objects:** References (memory addresses) to the objects are stored side-by-side.
* **Fixed Size:** Once an array is created, its length is permanent. To use a dynamic list, you would use `ArrayList`.
* **The `length` Property:** Every Java array has a built-in property `length` that stores the number of elements it can hold.

---

### 2. Declaration and Initialization

#### A. Declaration
You can declare an array in two ways:
```java
int[] arr;   // Preferred style
int arr[];   // Also valid (inherited from C)
```

#### B. Allocation & Initialization
Declaring an array only creates a reference. You must use the `new` keyword to allocate memory.
```java
arr = new int[5]; // Allocates memory for 5 integers, defaults to 0
```

#### C. Array Literal
If you know the values beforehand, you can use a literal:
```java
int[] arr = {10, 20, 30, 40};
```
[Image showing array initialization with specific values in Java]

---

### 3. Arrays of Objects
In Java, you can create an array to store objects. This is essentially an array of references.
```java
Student[] students = new Student[3];
students[0] = new Student("Alice");
```

---

### 4. Important Concepts

| Concept | Description |
| :--- | :--- |
| **Default Values** | `new int[5]` fills with `0`. `boolean` defaults to `false`. Objects default to `null`. |
| **Bounds Checking** | Accessing an index outside `0` to `length - 1` throws **`ArrayIndexOutOfBoundsException`**. |
| **Passing to Methods** | Arrays are passed by reference. Changes made inside a method affect the original array. |
| **Anonymous Arrays** | You can create an array without a name to pass it immediately: `method(new int[]{1, 2, 3});` |

---

### 5. Multidimensional Arrays
A 2D array in Java is technically an **array of arrays**. This allows for "Jagged Arrays" where each row has a different number of columns.
```java
int[][] matrix = new int[3][3]; // Regular 3x3 matrix
int[][] jagged = new int[2][];  // Jagged array
jagged[0] = new int[3];
jagged[1] = new int[5];
```

---

## ArrayList in Java

The **ArrayList** class is a resizable array, which can be found in the `java.util` package. Unlike a standard array, which has a fixed size, an `ArrayList` can grow and shrink dynamically as you add or remove elements.



---

### 1. Key Characteristics
* **Dynamic Resizing:** It automatically increases its capacity when it becomes full.
* **Ordered Collection:** It maintains the insertion order of elements.
* **Allows Duplicates:** You can store multiple identical values.
* **Non-Primitive Only:** It can only store objects. To store primitives like `int` or `char`, Java uses **Auto-boxing** to convert them into their wrapper classes (`Integer`, `Character`).
* **Random Access:** Since it is backed by an array, it provides $O(1)$ time complexity for accessing elements by index.

---

### 2. Declaration and Initialization
To use `ArrayList`, you must import `java.util.ArrayList`.
```java
import java.util.ArrayList;

ArrayList<String> list = new ArrayList<>(); // Create an empty list of Strings
ArrayList<Integer> numbers = new ArrayList<>(10); // Initial capacity of 10
```

---

### 3. Core Operations

| Operation | Method | Time Complexity |
| :--- | :--- | :--- |
| **Add Element** | `add(value)` | Amortized $O(1)$ |
| **Access Element** | `get(index)` | $O(1)$ |
| **Modify Element** | `set(index, value)` | $O(1)$ |
| **Remove Element** | `remove(index)` | $O(n)$ (requires shifting) |
| **Check Size** | `size()` | $O(1)$ |

[Image illustrating how ArrayList internal array shifts elements during a remove operation]

---

### 4. How ArrayList Works Internally
When an `ArrayList` reaches its capacity, it performs the following steps:
1. It creates a new, larger array (usually 1.5x the old size).
2. It copies all elements from the old array to the new one.
3. The old array is discarded, and the `ArrayList` points to the new memory block.

---

### 5. Methods of Traversal
There are multiple ways to iterate through an `ArrayList`:
* **For Loop:** Using an index and `get()`.
* **Enhanced For-Each Loop:** `for (String s : list)`.
* **Iterator:** Using the `Iterator` interface for safe removal during iteration.
* **Java 8+ forEach:** `list.forEach(item -> System.out.println(item));`.

---

### 6. ArrayList vs. Vector vs. LinkedList

| Feature | ArrayList | Vector | LinkedList |
| :--- | :--- | :--- | :--- |
| **Synchronization** | Not Synchronized | Synchronized (Thread-safe) | Not Synchronized |
| **Performance** | Faster | Slower | Fast for add/remove at ends |
| **Structure** | Dynamic Array | Dynamic Array | Doubly Linked List |
| **Best Use Case** | Frequent search/access | Legacy/Thread-safety | Frequent add/remove |



---

## Python Lists

In Python, a **List** is a versatile, built-in data structure used to store an ordered collection of items. Unlike arrays in many other languages, Python lists are highly flexible and can store elements of different data types within the same list.


---

### 1. Key Characteristics
* **Ordered:** They maintain the order in which elements are inserted.
* **Mutable:** You can change, add, or remove items after the list has been created.
* **Allows Duplicates:** The same value can appear multiple times at different indices.
* **Heterogeneous:** A single list can contain integers, strings, floats, and even other lists.

---

### 2. Creating a List
```python
# Using square brackets
my_list = [10, "Python", 3.14, True]

# Using the list() constructor
another_list = list((1, 2, 3))

# Creating a list with repeated elements
zeros = [0] * 5  # Result: [0, 0, 0, 0, 0]
```

---

### 3. Accessing Elements
Python uses **Zero-based Indexing**. It also supports **Negative Indexing** to access elements from the end of the list.
* `my_list[0]` – Accesses the first element.
* `my_list[-1]` – Accesses the last element.
* `my_list[1:3]` – **Slicing**: Accesses elements from index 1 up to (but not including) index 3.


---

### 4. Common List Methods

| Method | Description | Complexity |
| :--- | :--- | :--- |
| **`append(x)`** | Adds item `x` to the end of the list. | $O(1)$ |
| **`insert(i, x)`**| Inserts item `x` at index `i`. | $O(n)$ |
| **`extend(iterable)`**| Appends all items from an iterable to the list. | $O(k)$ |
| **`pop(i)`** | Removes and returns the item at index `i` (defaults to last). | $O(n)$ |
| **`remove(x)`** | Removes the first occurrence of value `x`. | $O(n)$ |
| **`sort()`** | Sorts the list in ascending order in-place. | $O(n \log n)$ |

---

### 5. List Comprehension
This is a concise way to create lists based on existing iterables. It is often faster and more readable than using traditional loops.
```python
# Create a list of squares for even numbers from 0 to 8
squares = [x**2 for x in range(10) if x % 2 == 0]
# Result: [0, 4, 16, 36, 64]
```

---

### 6. Internal Storage Mechanism
Python lists do not store the actual objects directly. Instead, they store **references (pointers)** to the objects in memory. This is why lists can hold different data types so easily.

[Image showing Python list as an array of pointers to objects in memory]

---

### 7. Nested Lists (2D Arrays)
Lists can contain other lists, allowing you to create grids or matrices.
```python
matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]
print(matrix[1][2]) # Output: 6 (row 1, column 2)
```

---

# Array Related Basic Problems
- Print Alternates
- Leaders in an array
- Remove Duplicates from Sorted
- Generate all Subarrays
- Reverse an Array
- Rotate an Array
- Zeroes to End
- Min Increments to Make Equal
- Min Cost to Make Size 1
---

## Print Alternate Elements of an Array

The task is to print every alternate element of a given array, starting from the first element (index 0).

**Example:**
* **Input:** `[10, 20, 30, 40, 50]`
* **Output:** `10 30 50`
* **Explanation:** Starting at index 0 (10), skip index 1 (20), print index 2 (30), skip index 3 (40), and print index 4 (50).


---

### 1. Iterative Approach (Recommended)
The most efficient way to solve this is using a `for` loop that increments the index by **2** in each iteration.

#### **Logic:**
1. Start a loop from index `i = 0`.
2. Print the element at `arr[i]`.
3. Increment `i` by 2 (`i += 2`).
4. Repeat until `i` is no longer less than the array length.

#### **Implementations:**

**C++**
```cpp
void printAlternates(vector<int> &arr) {
    for(int i = 0; i < arr.size(); i += 2) {
        cout << arr[i] << " ";
    }
}
```

**Java**
```java
void printAlternates(int[] arr) {
    for (int i = 0; i < arr.length; i += 2) {
        System.out.print(arr[i] + " ");
    }
}
```

**Python**
```python
def print_alternates(arr):
    # Using range with a step of 2
    for i in range(0, len(arr), 2):
        print(arr[i], end=" ")
        
    # Pythonic Way (Slicing)
    # print(*(arr[::2]))
```

**Complexity:**
* **Time Complexity:** $O(n)$, where $n$ is the number of elements.
* **Auxiliary Space:** $O(1)$, as no extra space is used.

---

### 2. Recursive Approach
You can also achieve this by recursively calling a function with the next alternate index.

#### **Logic:**
1. Base Case: If the current index is $\ge$ array size, stop.
2. Print the element at the current index.
3. Recursive Call: Call the function with `index + 2`.


**Complexity:**
* **Time Complexity:** $O(n)$
* **Auxiliary Space:** $O(n)$ due to the recursive call stack.

---

### Comparison of Approaches

| Feature | Iterative | Recursive |
| :--- | :--- | :--- |
| **Simplicity** | High | Medium |
| **Memory Efficiency**| High ($O(1)$ space) | Lower ($O(n)$ space) |
| **Best For** | General Use | Learning Recursion |

---

## Leaders in an Array

An element in an array is called a **Leader** if it is greater than or equal to all the elements to its right side. By definition, the rightmost element is always a leader.

**Example:**
* **Input:** `[16, 17, 4, 3, 5, 2]`
* **Output:** `[17, 5, 2]`
* **Explanation:**
    * **17** is a leader because it's greater than `4, 3, 5, 2`.
    * **5** is a leader because it's greater than `2`.
    * **2** is a leader because there is nothing to its right.


---

### 1. Naive Approach (Nested Loops)
The simplest way is to check every element against all elements to its right.
* **Algorithm:** Use an outer loop to pick an element and an inner loop to see if any element to its right is larger. If none are larger, it’s a leader.
* **Time Complexity:** $O(n^2)$
* **Space Complexity:** $O(1)$

---

### 2. Optimized Approach (Suffix Maximum)
Instead of re-checking the right side for every element, we can traverse the array from **right to left**.

#### **Logic:**
1. The rightmost element is always a leader. Store it and call it `max_from_right`.
2. Move to the left. If the current element is greater than or equal to `max_from_right`, it is a leader.
3. Update `max_from_right` whenever a new leader is found.
4. (Optional) Reverse the result list if you need the leaders in their original relative order.

[Image illustrating the right-to-left scan of an array to find leaders with a running maximum]

#### **Implementations:**

**C++**
```cpp
vector<int> findLeaders(int arr[], int n) {
    vector<int> leaders;
    int max_from_right = arr[n-1];
    leaders.push_back(max_from_right);

    for (int i = n-2; i >= 0; i--) {
        if (arr[i] >= max_from_right) {
            max_from_right = arr[i];
            leaders.push_back(max_from_right);
        }
    }
    reverse(leaders.begin(), leaders.end());
    return leaders;
}
```

**Python**
```python
def find_leaders(arr):
    n = len(arr)
    max_from_right = arr[n-1]
    leaders = [max_from_right]
    
    for i in range(n-2, -1, -1):
        if arr[i] >= max_from_right:
            max_from_right = arr[i]
            leaders.append(arr[i])
            
    return leaders[::-1] # Reverse to maintain order
```

**Complexity:**
* **Time Complexity:** $O(n)$ — We only pass through the array once.
* **Auxiliary Space:** $O(1)$ (if not counting the space for the output list).

---

### Comparison

| Method | Time Complexity | Space Complexity | Efficiency |
| :--- | :--- | :--- | :--- |
| **Nested Loops** | $O(n^2)$ | $O(1)$ | Slow for large arrays |
| **Suffix Scan** | $O(n)$ | $O(1)$ | Highly Efficient |

---

## Remove Duplicates from Sorted Array

Given a **sorted** array, the objective is to remove all duplicate elements such that each unique element appears only once at the beginning of the array. The function should return the count of these unique elements.

**Example:**
* **Input:** `[1, 2, 2, 3, 4, 4, 4, 5]`
* **Output:** `5` (The modified array starts with `[1, 2, 3, 4, 5]`)


---

### 1. Two-Pointers Approach (Optimal)
Since the array is already sorted, all identical elements are adjacent. We can use two pointers to process the array in a single pass without extra space.

#### **Logic:**
1. Initialize a pointer `idx = 1`. This pointer will track where the next unique element should be placed.
2. Iterate through the array starting from the second element (`i = 1`).
3. Compare the current element `arr[i]` with the previous element `arr[i-1]`.
4. If they are different (`arr[i] != arr[i-1]`), it means we found a new unique element.
5. Place this unique element at `arr[idx]` and increment `idx`.
6. After the loop, the first `idx` elements are the unique ones.

[Image illustrating the two-pointer technique for removing duplicates in a sorted array]

#### **Implementations:**

**C++**
```cpp
int removeDuplicates(vector<int>& arr) {
    int n = arr.size();
    if (n <= 1) return n;

    int idx = 1; // Position for the next unique element
    for (int i = 1; i < n; i++) {
        if (arr[i] != arr[i - 1]) {
            arr[idx++] = arr[i];
        }
    }
    return idx;
}
```

**Java**
```java
public static int removeDuplicates(int[] arr) {
    if (arr.length <= 1) return arr.length;
    
    int idx = 1;
    for (int i = 1; i < arr.length; i++) {
        if (arr[i] != arr[i-1]) {
            arr[idx++] = arr[i];
        }
    }
    return idx;
}
```

**Python**
```python
def remove_duplicates(arr):
    if not arr: return 0
    
    idx = 1
    for i in range(1, len(arr)):
        if arr[i] != arr[i-1]:
            arr[idx] = arr[i]
            idx += 1
    return idx
```

**Complexity:**
* **Time Complexity:** $O(n)$ — Single traversal of the array.
* **Auxiliary Space:** $O(1)$ — No extra data structures used.

---

### 2. Using a Hash Set (Works for Unsorted Too)
While less efficient for memory in this specific problem, using a set is a more general solution that doesn't require the array to be sorted.
* **Logic:** Traverse the array and store elements in a Set. If an element isn't in the set, move it to the next available "unique" position in the array.
* **Time Complexity:** $O(n)$
* **Auxiliary Space:** $O(n)$ (to store the set).

---

### Key Comparison

| Approach | Space Complexity | Best For... |
| :--- | :--- | :--- |
| **Two-Pointers** | $O(1)$ | Sorted Arrays (Memory Efficient) |
| **Hash Set** | $O(n)$ | Unsorted Arrays or when order doesn't matter |

---

## Generating Subarrays Using Recursion

A **subarray** is a contiguous part of an array. For an array of size $n$, there are $n \times (n+1) / 2$ non-empty subarrays. Generating these using recursion involves defining a systematic way to pick start and end indices.



---

### 1. The Recursive Logic
To generate all subarrays, we essentially need to explore every possible pair of `(start, end)` indices where `start <= end`.

#### **Base Case:**
* If the `start` index reaches the end of the array, stop the recursion.
* If the `end` index reaches the end of the array, move to the next `start` index and reset `end = start`.

#### **Recursive Step:**
1. Print the elements from the current `start` to the current `end`.
2. Call the function again, incrementing the `end` index by 1.
3. Once all subarrays starting at `start` are printed, trigger a new recursive branch incrementing `start` by 1.

---

### 2. Implementation Examples

**C++**
```cpp
void generateSubarrays(vector<int> &arr, int start, int end) {
    // Base Case: start reaches end of array
    if (start == arr.size()) return;

    // If end reaches end of array, increment start and reset end
    if (end == arr.size()) {
        generateSubarrays(arr, start + 1, start + 1);
        return;
    }

    // Print subarray from start to end
    cout << "[";
    for (int i = start; i <= end; i++) {
        cout << arr[i] << (i == end ? "" : ", ");
    }
    cout << "]" << endl;

    // Increment end for the next subarray
    generateSubarrays(arr, start, end + 1);
}
```

**Python**
```python
def generate_subarrays(arr, start, end):
    if start == len(arr):
        return
    
    if end == len(arr):
        generate_subarrays(arr, start + 1, start + 1)
        return
    
    # Print current subarray
    print(arr[start : end + 1])
    
    # Recursive call to increment end index
    generate_subarrays(arr, start, end + 1)

# Driver code
arr = [1, 2, 3]
generate_subarrays(arr, 0, 0)
```



---

### 3. Complexity Analysis

* **Time Complexity:** $O(n^2)$ recursive calls. Since printing each subarray takes $O(n)$ time, the total time complexity is **$O(n^3)$**. 
* **Auxiliary Space:** **$O(n^2)$** due to the depth of the recursive call stack (one call for every possible subarray).

---

### 4. Key Differences: Subarray vs. Subsequence vs. Subset

| Term | Contiguous? | Order Maintained? | Total Count |
| :--- | :--- | :--- | :--- |
| **Subarray** | Yes | Yes | $n(n+1)/2$ |
| **Subsequence** | No | Yes | $2^n$ |
| **Subset** | No | No | $2^n$ |

[Image comparing a subarray, a subsequence, and a subset of the same original array]

---

## Reverse an Array

Reversing an array means rearranging the elements so that the first becomes the last, the second becomes the second-to-last, and so on.

**Example:**
* **Input:** `[1, 4, 3, 2, 6, 5]`
* **Output:** `[5, 6, 2, 3, 4, 1]`


---

### 1. Two-Pointers Approach (Optimal)
This is the standard and most efficient way to reverse an array in-place.

#### **Logic:**
1. Maintain two pointers: `left` (starting at index 0) and `right` (starting at the last index).
2. While `left < right`:
    * Swap the elements at `arr[left]` and `arr[right]`.
    * Increment `left` and decrement `right`.
3. Stop when the pointers meet or cross in the middle.

[Image illustrating the two-pointer technique for array reversal with pointers moving inward]

#### **Implementations:**

**Java**
```java
static void reverseArray(int[] arr) {
    int left = 0, right = arr.length - 1;
    while (left < right) {
        // Swap elements
        int temp = arr[left];
        arr[left] = arr[right];
        arr[right] = temp;
        
        left++;
        right--;
    }
}
```

**Python**
```python
def reverse_array(arr):
    left = 0
    right = len(arr) - 1
    while left < right:
        arr[left], arr[right] = arr[right], arr[left]
        left += 1
        right -= 1

# Using Python Slicing (Short-hand)
# reversed_arr = arr[::-1]
```

**Complexity:**
* **Time Complexity:** $O(n)$ — We visit each element once (specifically $n/2$ swaps).
* **Auxiliary Space:** $O(1)$ — No extra memory used.

---

### 2. Recursive Approach
Reversal can also be done by recursively swapping the outer elements and shrinking the problem size.
* **Logic:** Swap `arr[low]` and `arr[high]`, then call the function for `(low + 1, high - 1)`.
* **Base Case:** If `low >= high`, return.

---

### 3. Using Built-in Methods
Most languages provide high-level functions to do this quickly.
* **Java:** `Collections.reverse(Arrays.asList(arr))` (for objects) or `IntStream`.
* **Python:** `arr.reverse()` (in-place) or `list(reversed(arr))`.
* **C++:** `std::reverse(arr.begin(), arr.end())`.

---

### Complexity Comparison

| Approach | Time Complexity | Space Complexity | Notes |
| :--- | :--- | :--- | :--- |
| **Two Pointers** | $O(n)$ | $O(1)$ | Best for memory efficiency. |
| **Temporary Array** | $O(n)$ | $O(n)$ | Easy to implement but uses extra memory. |
| **Recursion** | $O(n)$ | $O(n)$ | Uses $O(n)$ space for the call stack. |

---

## Complete Guide on Array Rotations

Array rotation involves shifting each element in an array to a new position. Rotations can be **Right (Clockwise)** or **Left (Counter-Clockwise)**.


---

### Types of Rotations

1.  **Right Rotation:** Elements shift to the right. The last element moves to the first position.
    * *Example:* `[1, 2, 3, 4, 5]` rotated right by 2 becomes `[4, 5, 1, 2, 3]`.
2.  **Left Rotation:** Elements shift to the left. The first element moves to the last position.
    * *Example:* `[1, 2, 3, 4, 5]` rotated left by 2 becomes `[3, 4, 5, 1, 2]`.

---

### Implementation Methods

#### 1. The Reversal Algorithm (Expected Approach)
This is the most efficient method for rotating an array in-place.

**Logic (For Right Rotation by $d$):**
1. Reverse the entire array.
2. Reverse the first $d$ elements.
3. Reverse the remaining $n-d$ elements.


**Complexity:**
* **Time:** $O(n)$
* **Space:** $O(1)$

---

#### 2. Juggling Algorithm
Based on finding the Greatest Common Divisor (GCD) of the array size $n$ and rotation count $d$. The array is divided into different sets, and elements are moved within these sets.


**Complexity:**
* **Time:** $O(n)$
* **Space:** $O(1)$

---

#### 3. Using a Temporary Array
A simpler but less memory-efficient approach.
1. Create a temporary array of size $n$.
2. For right rotation, copy the last $d$ elements to the start of the temp array.
3. Copy the first $n-d$ elements to the rest of the temp array.
4. Copy everything back to the original array.

**Complexity:**
* **Time:** $O(n)$
* **Space:** $O(n)$

---

### Implementation Code (Reversal Algorithm)

**C++**
```cpp
void rotateArr(vector<int>& arr, int d) {
    int n = arr.size();
    d %= n;
    reverse(arr.begin(), arr.end());
    reverse(arr.begin(), arr.begin() + d);
    reverse(arr.begin() + d, arr.end());
}
```

**Python**
```python
def rotate_arr(arr, d):
    n = len(arr)
    d %= n
    arr.reverse()
    arr[:d] = reversed(arr[:d])
    arr[d:] = reversed(arr[d:])
```

---

### Comparison Summary

| Method | Time Complexity | Space Complexity | Best For |
| :--- | :--- | :--- | :--- |
| **Reversal** | $O(n)$ | $O(1)$ | General purpose/Interviews |
| **Juggling** | $O(n)$ | $O(1)$ | Mathematical elegance |
| **Temp Array**| $O(n)$ | $O(n)$ | Simplicity (if memory allows)|
| **One-by-One**| $O(n \times d)$ | $O(1)$ | Small $d$ values only |

---

## Move All Zeroes to the End

The task is to move all zeros in an array to the end while maintaining the original relative order of the non-zero elements.

**Example:**
* **Input:** `[1, 2, 0, 4, 3, 0, 5, 0]`
* **Output:** `[1, 2, 4, 3, 5, 0, 0, 0]`


---

### 1. Two-Traversals Approach (Better)
This method uses a single pointer to track the position of the next non-zero element.

#### **Logic:**
1. Initialize a variable `count = 0` to track the index of non-zero elements.
2. **First Traversal:** Iterate through the array. Whenever you find a non-zero element, move it to `arr[count]` and increment `count`.
3. **Second Traversal:** Once all non-zero elements are moved to the front, fill the remaining indices from `count` to the end of the array with zeros.

[Image showing the two-step process of shifting non-zero elements then filling remaining space with zeros]

#### **Implementations:**

**Java**
```java
void pushZerosToEnd(int[] arr) {
    int count = 0; 
    // Shift non-zero elements to the front
    for (int i = 0; i < arr.length; i++) {
        if (arr[i] != 0) {
            arr[count++] = arr[i];
        }
    }
    // Fill remaining array with 0s
    while (count < arr.length) {
        arr[count++] = 0;
    }
}
```

**Python**
```python
def push_zeros_to_end(arr):
    count = 0
    # Step 1: Move non-zero elements
    for i in range(len(arr)):
        if arr[i] != 0:
            arr[count] = arr[i]
            count += 1
    
    # Step 2: Fill the rest with 0
    while count < len(arr):
        arr[count] = 0
        count += 1
```

---

### 2. One-Traversal Approach (Optimal)
We can achieve this in a single pass by using the **Swap** technique.

#### **Logic:**
1. Maintain a pointer `count = 0` for the position of the first zero encountered.
2. Iterate through the array. When you find a non-zero element `arr[i]`, swap it with `arr[count]` and increment `count`.
3. This effectively "bubbles" the zeros toward the end as you discover more non-zero numbers.

[Image illustrating the swap-based one-pass method to move zeroes to the end]

#### **Implementations:**

**C++**
```cpp
void pushZerosToEnd(vector<int>& arr) {
    int count = 0;
    for (int i = 0; i < arr.size(); i++) {
        if (arr[i] != 0) {
            swap(arr[i], arr[count]);
            count++;
        }
    }
}
```

---

### Complexity Comparison

| Approach | Time Complexity | Space Complexity | Pass Count |
| :--- | :--- | :--- | :--- |
| **Temporary Array** | $O(n)$ | $O(n)$ | 2 Passes |
| **Two-Traversals** | $O(n)$ | $O(1)$ | 2 Passes |
| **Swap (Optimal)** | $O(n)$ | $O(1)$ | 1 Pass |

---

## Minimum Increment by K Operations to Make Elements Equal

Given an array of $n$ elements and an integer $k$, find the minimum number of operations required to make all array elements equal. In one operation, you can increment an element by $k$. If it is impossible, return `-1`.

**Examples:**
* **Input:** `arr[] = {4, 7, 19, 16}`, `k = 3`
* **Output:** `10`
* **Input:** `arr[] = {4, 2, 6, 8}`, `k = 3`
* **Output:** `-1` (Differences are not divisible by 3)

---

### 1. Logical Approach
To make all elements equal by only incrementing them, every element must eventually equal the **maximum element** currently in the array. 

#### **Key Observations:**
1.  **Target Value:** The target must be the maximum value in the array ($max$). If we picked a smaller value, we would need to decrement elements, which isn't allowed.
2.  **Feasibility Check:** For an element $arr[i]$ to become equal to $max$ by adding $k$ repeatedly, the difference $(max - arr[i])$ **must be divisible by $k$**.
    * Condition: $(max - arr[i]) \pmod k == 0$
3.  **Operation Count:** The number of operations for a single element is $(max - arr[i]) / k$.

---

### 2. Step-by-Step Algorithm
1.  Find the maximum element in the array ($maxVal$).
2.  Initialize `res = 0` to store the total operations.
3.  Iterate through each element $x$ in the array:
    * If $(maxVal - x) \pmod k \neq 0$, return `-1` (impossible).
    * Otherwise, add $(maxVal - x) / k$ to `res`.
4.  Return `res`.

[Image illustrating an array with different bar heights being incremented by fixed blocks of size K to reach the maximum height]

---

### 3. Implementation

**Java**
```java
static int minOps(int[] arr, int k) {
    int maxVal = Arrays.stream(arr).max().getAsInt();
    int res = 0;

    for (int x : arr) {
        // If the gap cannot be filled by adding k, return -1
        if ((maxVal - x) % k != 0) {
            return -1;
        }
        res += (maxVal - x) / k;
    }
    return res;
}
```

**Python**
```python
def min_ops(arr, k):
    max_val = max(arr)
    res = 0
    
    for x in arr:
        if (max_val - x) % k != 0:
            return -1
        res += (max_val - x) // k
        
    return res
```

---

### 4. Complexity Analysis
* **Time Complexity:** $O(n)$ — One pass to find the maximum and another pass to calculate operations.
* **Auxiliary Space:** $O(1)$ — Only a few variables are used regardless of input size.

---


## Minimum Cost to Reduce Array Size to 1

In this problem, you are given an array of $n$ integers. You need to reduce the array to a single element by repeatedly performing an operation: select any two elements and remove the larger one. The cost of this operation is equal to the value of the smaller element. The goal is to find the minimum total cost to reach an array size of 1.

**Example:**
* **Input:** `arr[] = [4, 3, 2]`
* **Output:** `4`
* **Explanation:** 1. Select `(4, 2)`. Smallest is `2`. Remove `4`. Array: `[3, 2]`. Cost: `2`.
    2. Select `(3, 2)`. Smallest is `2`. Remove `3`. Array: `[2]`. Cost: `2`.
    3. Total Cost: $2 + 2 = 4$.


---

### 1. Greedy Logic
To minimize the total cost, we want to perform every removal operation using the **absolute minimum value** present in the array. 

* Every time we remove an element, the array size decreases by 1. 
* To reach size 1 from size $n$, we must perform exactly **$n - 1$** operations.
* If we always pair the smallest element in the array with any other element, we remove the larger element at the cost of the smallest one.
* Since the smallest element is never removed (it is always the "survivor" in its pair until the end), the cost for every single one of the $n-1$ operations will be the same minimum value.

**Formula:**
$$\text{Min Cost} = (n - 1) \times \min(\text{array})$$

---

### 2. Implementation

**Java**
```java
public static int minCost(int[] arr) {
    int n = arr.length;
    if (n <= 1) return 0;

    int minVal = arr[0];
    for (int i = 1; i < n; i++) {
        if (arr[i] < minVal) {
            minVal = arr[i];
        }
    }

    return (n - 1) * minVal;
}
```

**Python**
```python
def min_cost(arr):
    if len(arr) <= 1:
        return 0
    return (len(arr) - 1) * min(arr)
```

---

### 3. Complexity Analysis
* **Time Complexity:** $O(n)$ — We only need one pass to find the minimum element in the array.
* **Auxiliary Space:** $O(1)$ — No extra data structures are required.

---

### Why not other elements?
If we use any value other than the minimum to remove an element, the cost of that specific operation will be higher than if we had used the minimum value. Since the minimum value is always available (it's never the "larger" one to be removed), it is always optimal to use it.

---

# Easy Problems
- Duplicate within K Distance
- Make Even Positioned Greater
- Sum of all Subarrays
- Stock Buy and Sell – Multiple Transactions
- Single Among Doubles
- Missing Number
- Missing and Repeating
- Only Repeating from 1 to n-1
- Sorted Subsequence of Size 3
- Max Subarray Sum
- Equilibrium index
- Split array into three equals
---

