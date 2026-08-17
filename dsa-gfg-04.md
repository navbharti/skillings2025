# Searching Algorithms: A Complete Guide

Searching algorithms are designed to retrieve or check for an element within any data structure where it is stored. They are categorized based on the type of search operation they perform and the nature of the data.

---

### 1. Classification of Searching Algorithms

#### **A. Sequential Search**
The data is traversed sequentially, and every element is checked.
* **Linear Search:** The most basic algorithm. It checks each element one by one until a match is found.
    * **Best Use:** Unsorted arrays or small data sets.
    * **Complexity:** $O(n)$

#### **B. Interval Search**
Specifically designed for **sorted** data structures. These are much more efficient than linear search.
* **Binary Search:** Repeatedly divides the search interval in half.
    * **Complexity:** $O(\log n)$
* **Ternary Search:** Divides the array into three parts instead of two.
    * **Complexity:** $O(\log_3 n)$
* **Jump Search:** Jumps ahead by fixed steps to find the block where the element might exist, then performs a linear search in that block.
    * **Complexity:** $O(\sqrt{n})$


---

### 2. Comparison of Popular Searching Algorithms

| Algorithm | Data Requirement | Time Complexity | Auxiliary Space |
| :--- | :--- | :--- | :--- |
| **Linear Search** | None (Unsorted) | $O(n)$ | $O(1)$ |
| **Binary Search** | Sorted | $O(\log n)$ | $O(1)$ |
| **Jump Search** | Sorted | $O(\sqrt{n})$ | $O(1)$ |
| **Interpolation**| Sorted & Uniform | $O(\log(\log n))$ | $O(1)$ |
| **Exponential** | Sorted | $O(\log n)$ | $O(1)$ |

[Image illustrating jump search with blocks and linear scan within a block]

---

### 3. Key Algorithms in Detail

#### **Binary Search (The Gold Standard)**
Binary search works by comparing the target value to the middle element of the array. If they are not equal, the half in which the target cannot lie is eliminated, and the search continues on the remaining half.

**Java (Iterative)**
```java
int binarySearch(int[] arr, int target) {
    int low = 0, high = arr.length - 1;
    while (low <= high) {
        int mid = low + (high - low) / 2;
        if (arr[mid] == target) return mid;
        if (arr[mid] < target) low = mid + 1;
        else high = mid - 1;
    }
    return -1;
}
```

[Image showing the divide and conquer mechanism of binary search on a sorted array]

#### **Interpolation Search**
An improvement over Binary Search for instances where the values in a sorted array are **uniformly distributed**. It estimates the position of the target value based on the values at the ends of the search range.

---

### 4. Which one to choose?
* **Use Linear Search** if the data is small or completely unsorted.
* **Use Binary Search** for most sorted data scenarios.
* **Use Interpolation Search** if the sorted data is uniformly distributed (e.g., a phone book).
* **Use Exponential Search** for searching in infinite or unbounded arrays.

---

## Introduction to Searching Algorithms

Searching is the fundamental process of locating a specific element or item within a collection of data. This collection can take various forms, such as arrays, lists, trees, or other structured representations.

---

### 1. Categories of Searching Algorithms

Searching algorithms are broadly divided into two categories based on how they process the data:

* **Sequential Search:** The list or array is traversed sequentially and every element is checked. 
    * *Example:* **Linear Search**.
* **Interval Search:** These algorithms are specifically designed for searching in sorted data structures. They are much more efficient than linear search as they repeatedly target the center of the search structure and divide the search space in half.
    * *Example:* **Binary Search**, **Ternary Search**.


---

### 2. Common Searching Algorithms

#### **Linear Search**
* **Logic:** Checks each element of the list one by one until a match is found or the whole list has been searched.
* **Pros:** Works on both sorted and unsorted data; very simple to implement.
* **Cons:** Slow for large datasets ($O(n)$ complexity).

#### **Binary Search**
* **Logic:** Works on sorted arrays by repeatedly dividing the search interval in half. If the target is less than the middle element, it narrows the interval to the lower half. Otherwise, it narrows it to the upper half.
* **Requirement:** Data **must** be sorted.
* **Complexity:** Very efficient at $O(\log n)$.


#### **Ternary Search**
* **Logic:** A divide-and-conquer algorithm that divides the search space into **three equal parts** using two midpoints (`mid1` and `mid2`).
* **Use Case:** Often used to find the maximum or minimum of a unimodal function.
* **Complexity:** $O(\log_3 n)$.

---

### 3. Comparison Table

| Algorithm | Best Case | Worst Case | Space | Requirement |
| :--- | :--- | :--- | :--- | :--- |
| **Linear Search** | $O(1)$ | $O(n)$ | $O(1)$ | None (Unsorted ok) |
| **Binary Search** | $O(1)$ | $O(\log n)$ | $O(1)$ | Sorted data |
| **Ternary Search** | $O(1)$ | $O(\log_3 n)$ | $O(1)$ | Unimodal data |
| **Jump Search** | $O(1)$ | $O(\sqrt{n})$ | $O(1)$ | Sorted data |
| **Interpolation Search** | $O(1)$ | $O(n)$ | $O(1)$ | Sorted & Uniform |
| **Exponential Search** | $O(1)$ | $O(\log n)$ | $O(1)$ | Sorted data |


---

### 4. Which Search to Use?
* Use **Linear Search** for small or unsorted collections.
* Use **Binary Search** for larger, sorted collections.
* Use **Jump Search** if you are on a system where "jumping" back is costly (it only jumps forward and then performs a small linear search).
* Use **Interpolation Search** if the data is sorted and distributed uniformly (like a telephone directory).

---

## Linear Search Algorithm

Linear Search (also known as Sequential Search) is the simplest searching algorithm. It works by starting at the beginning of a data set and checking each element one by one until the target value is found or the end of the data set is reached.


---

### 1. How it Works
1.  Start from the first element (index 0).
2.  Compare the current element with the target value $x$.
3.  If they match, return the current index.
4.  If they don't match, move to the next element.
5.  Repeat until the element is found or you reach the end of the array.
6.  If the loop finishes without a match, return `-1`.

---

### 2. Implementation

**Java**
```java
public static int linearSearch(int[] arr, int x) {
    for (int i = 0; i < arr.length; i++) {
        if (arr[i] == x) {
            return i; // Target found
        }
    }
    return -1; // Target not found
}
```

**Python**
```python
def linear_search(arr, x):
    for i in range(len(arr)):
        if arr[i] == x:
            return i
    return -1
```

---

### 3. Complexity Analysis
* **Best Case:** $O(1)$ — The target element is at the very first position.
* **Worst Case:** $O(n)$ — The target element is at the last position or not present at all.
* **Average Case:** $O(n)$ — On average, the element is found in the middle.
* **Auxiliary Space:** $O(1)$ — No additional storage is needed beyond a few variables.

---

### 4. Pros and Cons

| Advantages | Disadvantages |
| :--- | :--- |
| Works on **unsorted** arrays. | Very slow for large datasets ($O(n)$). |
| Extremely easy to implement. | Inefficient compared to Binary Search ($O(\log n)$). |
| Memory efficient (in-place). | Performance degrades linearly as $n$ increases. |
| Can be used on any data type. | |

[Image comparing linear search vs binary search efficiency on a graph]

### 5. When to Use Linear Search?
* When the dataset is **small**.
* When the data is **unsorted** and you don't want to spend time sorting it.
* When searching through a **Linked List** (since random access isn't possible).
* When the search is performed only a few times.

---

## Binary Search Algorithm

Binary Search is an efficient algorithm for finding an item from a **sorted** list of items. It works by repeatedly dividing in half the portion of the list that could contain the item until you've narrowed down the possible locations to just one.


---

### 1. Prerequisite
For Binary Search to work, the data structure must meet two conditions:
* The data must be **sorted** (ascending or descending).
* The data structure must allow **constant time $O(1)$ access** to any element (like an array).

---

### 2. How it Works (Divide and Conquer)
1.  **Find the Middle:** Calculate the middle index: $mid = low + \frac{high - low}{2}$.
2.  **Compare:**
    * If `arr[mid] == target`, you found it! Return `mid`.
    * If `target < arr[mid]`, the target must be in the **left half**. Set `high = mid - 1`.
    * If `target > arr[mid]`, the target must be in the **right half**. Set `low = mid + 1`.
3.  **Repeat:** Continue until `low > high` (not found).

---

### 3. Implementation

**Iterative (Preferred for Space Efficiency)**
```java
int binarySearch(int[] arr, int x) {
    int low = 0, high = arr.length - 1;
    while (low <= high) {
        int mid = low + (high - low) / 2;
        if (arr[mid] == x) return mid;
        if (arr[mid] < x) low = mid + 1;
        else high = mid - 1;
    }
    return -1;
}
```

**Recursive**
```python
def binary_search_recursive(arr, low, high, x):
    if high >= low:
        mid = low + (high - low) // 2
        if arr[mid] == x: return mid
        elif arr[mid] > x: return binary_search_recursive(arr, low, mid - 1, x)
        else: return binary_search_recursive(arr, mid + 1, high, x)
    return -1
```

---

### 4. Complexity Analysis
* **Time Complexity:**
    * **Best Case:** $O(1)$ (Target is the middle element).
    * **Average/Worst Case:** $O(\log n)$ (Search space is halved each step).
* **Space Complexity:**
    * **Iterative:** $O(1)$ (No extra space).
    * **Recursive:** $O(\log n)$ (Due to the recursion stack).

[Image illustrating the logarithmic growth of binary search compared to linear search]

---

### 5. Why $low + (high - low) / 2$ instead of $(low + high) / 2$?
In most programming languages, `low + high` can cause an **integer overflow** if the sum exceeds the maximum value of a 32-bit integer. Using the subtraction method prevents this while giving the same result.

---

