# Bubble Sort

## What is Bubble Sort?
- Bubble Sort is a simple sorting algorithm that compares adjacent elements and swaps them if they are in the wrong order.
- The name “Bubble Sort” comes from the way smaller elements “bubble” to the top of the list (like bubbles rising in water).

## How Does Bubble Sort Work?
Let’s say we have a list of numbers: [5, 3, 4, 2]. Here’s how Bubble Sort would sort this list in ascending order:
- Step 1: Compare the first two elements (5 and 3). Since 5 > 3, swap them. The list becomes [3, 5, 4, 2].
- Step 2: Compare the next two elements (5 and 4). Since 5 > 8, swap them. The list becomes [3, 4, 5, 2]
- Step 3: Compare 5 and 2. Since 5 > 2, swap them. The list becomes [3, 4, 2, 5].
- Step 4: Repeat the process for the remaining unsorted part of the list ([3, 4, 2]).
After each full pass through the list, the largest unsorted element “bubbles up” to its correct position. This process continues until the entire list is sorted and becomes [2, 3, 4, 5]

## Bubble Sort in C++
### Simple Bubble Sort (Basic Approach)
```cpp
#include <iostream>using namespace std;
void bubbleSort(int arr[], int n) {
    for (int i = 0; i < n - 1; i++) {
        for (int j = 0; j < n - i - 1; j++) {
            if (arr[j] > arr[j + 1]) {
                // Swap adjacent elements if they are in the wrong order
                swap(arr[j], arr[j + 1]);
            }
        }
    }
}
int main() {
    int arr[] = {5, 3, 4, 2};
    int n = sizeof(arr) / sizeof(arr[0]);
    cout << "Original array: ";
    printArray(arr, n);
    
    for (int i = 0; i < size; i++) {
        cout << arr[i] << " ";
    }
    cout << endl;
    
    bubbleSort(arr, n);
    cout << "Sorted Array: ";
    for (int i = 0; i < size; i++) {
        cout << arr[i] << " ";
    }
    cout << endl;
    return 0;
}
```

### Optimized Bubble Sort (With Early Stopping)
The above implementation always performs n-1 passes, even if the list gets sorted early. We can optimize it by introducing a flag to stop execution when no swaps are made.

```cpp
#include <iostream>using namespace std;
void bubbleSort(int arr[], int size) {
    for (int i = 0; i < size - 1; i++) {
        // Flag to check if any swapping happened
        bool swapped = false;
        // Compare adjacent elements
        for (int j = 0; j < size - i - 1; j++) {
            if (arr[j] > arr[j + 1]) {
                // Swap if elements are out of order
                swap(arr[j], arr[j + 1]);
                swapped = true;
            }
        }
        // If no swapping happened, the list is already sorted
        if (!swapped) {
            break;
        }
    }
}
int main() {
    int arr[] = {5, 3, 4, 2};
    int size = sizeof(arr) / sizeof(arr[0]);
    cout << "Original Array: ";
    for (int i = 0; i < size; i++) {
        cout << arr[i] << " ";
    }
    cout << endl;
    // Perform Bubble Sort
    bubbleSort(arr, size);
    cout << "Sorted Array: ";
    for (int i = 0; i < size; i++) {
        cout << arr[i] << " ";
    }
    cout << endl;
    return 0;
}
```

## Bubble Sort in Python
### Simple Bubble Sort (Basic Approach)
```python
def bubble_sort(arr):
    n = len(arr)
    for i in range(n - 1):
        for j in range(n - i - 1):
            if arr[j] > arr[j + 1]:
                # Swap adjacent elements if they are in the wrong order
                arr[j], arr[j + 1] = arr[j + 1], arr[j]
arr = [5, 3, 4, 2]
print("Original Array:", arr)
bubble_sort(arr)
print("Sorted Array:", arr)
```

### Optimized Bubble Sort (With Early Stopping)
```python
def bubble_sort_optimized(arr):
    n = len(arr)
    for i in range(n - 1):
        swapped = False
        for j in range(n - i - 1):
            if arr[j] > arr[j + 1]:
                arr[j], arr[j + 1] = arr[j + 1], arr[j]
                swapped = True
        if not swapped:  # If no swapping happened, break early
            break
arr = [5, 3, 4, 2]
print("Original Array:", arr)
bubble_sort_optimized(arr)
print("Sorted Array:", arr)
```

## Bubble Sort in Java
### Simple Bubble Sort (Basic Approach)
```java
class BubbleSort {
    static void bubbleSort(int arr[]) {
        int n = arr.length;
        for (int i = 0; i < n - 1; i++) {
            for (int j = 0; j < n - i - 1; j++) {
                if (arr[j] > arr[j + 1]) {
                    // Swap adjacent elements if they are in the wrong order
                    int temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                }
            }
        }
    }
public static void main(String args[]) {
        int arr[] = {5, 3, 4, 2};
        System.out.print("Original Array: ");
        for (int num : arr)
            System.out.print(num + " ");
        System.out.println();
        bubbleSort(arr);
        System.out.print("Sorted Array: ");
        for (int num : arr)
            System.out.print(num + " ");
        System.out.println();
    }
}
```

### Optimized Bubble Sort (With Early Stopping)
```java
class OptimizedBubbleSort {
    static void bubbleSort(int arr[]) {
        int n = arr.length;
        for (int i = 0; i < n - 1; i++) {
            boolean swapped = false;
            for (int j = 0; j < n - i - 1; j++) {
                if (arr[j] > arr[j + 1]) {
                    // Swap adjacent elements if they are in the wrong order
                    int temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                    swapped = true;
                }
            }
            if (!swapped)  // If no swapping happened, the list is already sorted
                break;
        }
    }
public static void main(String args[]) {
        int arr[] = {5, 3, 4, 2};
        System.out.print("Original Array: ");
        for (int num : arr)
            System.out.print(num + " ");
        System.out.println();
        bubbleSort(arr);
        System.out.print("Sorted Array: ");
        for (int num : arr)
            System.out.print(num + " ");
        System.out.println();
    }
}
```

## Explanation of the Code:
- Outer Loop (i): This loop runs from the first element to the second-last element. It ensures that the largest unsorted element "bubbles up" to its correct position in each iteration.
- Inner Loop (j): This loop compares adjacent elements and swaps them if they are in the wrong order.
- Swapped Flag: This flag optimizes the algorithm. If no swaps occur during a pass, the list is sorted, and the algorithm stops early.
- Swap Function: The swap() function is used to swap two elements in the array.

## Time and Space Complexity
- Time Complexity: O(n²) — The algorithm uses two nested loops.
- Space Complexity: O(1) — Bubble Sort is an in-place sorting algorithm, it doesn’t require extra memory.

## Advantages of Bubble Sort
- Simple and Easy to Understand: It’s one of the easiest sorting algorithms to implement.
- No Extra Memory Required: It sorts the list in place, making it memory-efficient.
- Good for Small Datasets: It works well for small lists or when the list is almost sorted.

## When to Use Bubble Sort?
- When you’re working with small datasets.
- When you need a simple algorithm for educational purposes.
- When memory usage is a concern (since it’s in-place).
















# Selection Sort

Selection Sort is a simple sorting algorithm that works by repeatedly finding the smallest (or largest) element from the unsorted part of the list and placing it at the beginning.

## Key Points:
- **Time Complexity: O(n²)** — This means it’s not the fastest for large datasets but great for small lists.
- **Space Complexity: O(1)** — It uses constant extra memory, making it memory-efficient.
- **In-Place Sorting**: It doesn’t require additional storage space; it sorts the list within the original array.

## How Does Selection Sort Work?
![](/images/selection_sort.jpg)
- **Step 1:** Find the smallest element in the unsorted part of the list. In this case, the smallest number is 2.
- **Step 2:** Swap it with the first element of the unsorted list. Now, the list becomes [2, 6, 4, 5].
- **Step 3:** Repeat the process for the remaining unsorted part of the list ([6, 4, 5]). The smallest element is 4, so swap it with the first element of the unsorted list. The list now becomes [2, 4, 6, 5].
- **Step 4:** Continue this process until the entire list is sorted will be: [2, 4, 5, 6].

## Selection Sort Algorithm C++ Implementation

```cpp
#include <iostream>using namespace std;
void selectionSort(int arr[], int size) {
    for (int i = 0; i < size - 1; i++) {
        // Assume the current index is the smallest
        int minIndex = i;
        // Find the smallest element in the unsorted part
        for (int j = i + 1; j < size; j++) {
            if (arr[j] < arr[minIndex]) {
                minIndex = j;
            }
        }
        // Swap the smallest element with the first unsorted element
        swap(arr[minIndex], arr[i]);
    }
}
int main() {
    int arr[] = {5, 6, 4, 2};
    int size = sizeof(arr) / sizeof(arr[0]);
    cout << "Original Array: ";
    for (int i = 0; i < size; i++) {
        cout << arr[i] << " ";
    }
    cout << endl;
    // Perform Selection Sort
    selectionSort(arr, size);
    cout << "Sorted Array: ";
    for (int i = 0; i < size; i++) {
        cout << arr[i] << " ";
    }
    cout << endl;
    return 0;
}
```

## Explanation of the Code:
- **Outer Loop (i):** This loop runs from the first element to the second-last element. It keeps track of the starting point of the unsorted part of the list.
- **Inner Loop (j):** This loop finds the smallest element in the unsorted part of the list.
- **Swap:** Once the smallest element is found, it is swapped with the first element of the unsorted part.
- **Repeat:** The process repeats until the entire list is sorted.

## Time and Space Complexity
- Time Complexity: O(n²) — This is because the algorithm uses two nested loops. For each element, it scans the entire unsorted part of the list.
- Space Complexity: O(1) — Selection Sort is an in-place sorting algorithm, meaning it doesn’t require extra memory.


## Advantages of Selection Sort
- Simple and Easy to Understand: It’s one of the easiest sorting algorithms to implement.
- Memory Efficient: Since it’s an in-place sorting algorithm, it doesn’t require additional memory.
- Good for Small Datasets: It works well for small lists or when the list is almost sorted.

## When to Use Selection Sort?
- When you’re working with small datasets.
- When memory usage is a concern (since it’s in place).
- When you need a simple algorithm for educational purposes.



# Insertion Sort
Insertion Sort is one of the simplest and most intuitive sorting algorithms. It’s like sorting a hand of playing cards you pick one card at a time and place it in its correct position among the already sorted cards.

## What is Insertion Sort?
A sorting algorithm that works by dividing a list into two parts:

- Sorted Section: Starts with the first element (which is always sorted by itself).
- Unsorted Section: Contains the rest of the elements.
- The algorithm takes one element from the unsorted section at a time and inserts it into its correct position in the sorted section. This process continues until the entire list is sorted.

## How Does Insertion Sort Work?
Let’s understand Insertion Sort with an example. Imagine you have the following array: [13, 12, 18, 2, 5].

## Step-by-Step Process:
1. **Initial Array:** [13, 12, 18, 2, 5]
1. **First Pass:** Compare 12 (second element) with 13 (first element). Since 12 < 13, swap them. Array becomes: [12, 13, 18, 2, 5]
1. **Second Pass:** Compare 18 with 13. No swap is needed as 18 > 13. Array remains: [12, 13, 18, 2, 5]
1. **Third Pass:** Compare 2 with 18, 13, and 12. Swap 2 with 18, then with 13, and finally with 12. Array becomes: [2, 12, 13, 18, 5]
1. **Fourth Pass:** Compare 5 with 18, 13, and 12. Swap 5 with 18, then with 13, and finally with 12. Array becomes: [2, 5, 12, 13, 18]

Now, the array is fully sorted!

## Insertion Sort in C++
```cpp
#include <iostream>using namespace std;
void insertionSort(int arr[], int n) {
    for (int i = 1; i < n; i++) { // Start from the second element
        int currentElement = arr[i]; // Element to be inserted
        int j = i - 1;
        // Move elements greater than currentElement to the right
        while (j >= 0 && arr[j] > currentElement) {
            arr[j + 1] = arr[j];
            j--;
        }
        // Insert currentElement in its correct position
        arr[j + 1] = currentElement;
    }
}
int main() {
    int arr[] = {9, 6, 7, 2, 5, 8};
    int n = sizeof(arr) / sizeof(arr[0]);
    insertionSort(arr, n);
    cout << "Sorted Array: ";
    for (int i = 0; i < n; i++) {
        cout << arr[i] << " ";
    }
    return 0;
}
```
##Output:
```concole
Sorted Array: 2 5 6 7 8 9
```

## Insertion Sort in Python
```python
def insertion_sort(arr):
    for i in range(1, len(arr)):  # Start from the second element
        current_element = arr[i]
        j = i - 1
# Move elements greater than current_element to the right
        while j >= 0 and arr[j] > current_element:
            arr[j + 1] = arr[j]
            j -= 1
        # Insert current_element in its correct position
        arr[j + 1] = current_element
arr = [9, 6, 7, 2, 5, 8]
insertion_sort(arr)
print("Sorted Array:", arr)
```

##Output:
```console
Sorted Array: [2, 5, 6, 7, 8, 9]
```

## Insertion Sort in Java
```java
class InsertionSort {
    static void insertionSort(int arr[]) {
        int n = arr.length;
        for (int i = 1; i < n; i++) { // Start from the second element
            int currentElement = arr[i];
            int j = i - 1;
// Move elements greater than currentElement to the right
            while (j >= 0 && arr[j] > currentElement) {
                arr[j + 1] = arr[j];
                j--;
            }
            // Insert currentElement in its correct position
            arr[j + 1] = currentElement;
        }
    }
    public static void main(String args[]) {
        int arr[] = {9, 6, 7, 2, 5, 8};
        insertionSort(arr);
        System.out.print("Sorted Array: ");
        for (int num : arr) {
            System.out.print(num + " ");
        }
    }
}
```

## Output:
```console
Sorted Array: 2 5 6 7 8 9
```

## Key Points About Insertion Sort
### 1. Time Complexity:
- Best Case: O(N) (when the array is already sorted).
- Worst Case: O(N²) (when the array is sorted in reverse order).
- Average Case: O(N²) (for random data).
## 2. Space Complexity: O(1) (it uses a constant amount of extra space).

## 3. Advantages:

Simple to implement.
Efficient for small datasets or nearly sorted data.
Works well in real-time scenarios where data is continuously added.
## 4. Disadvantages:

Inefficient for large datasets due to its quadratic time complexity.

## When to Use Insertion Sort?
- Small Datasets: It’s perfect for sorting small arrays.
- Nearly Sorted Data: If the data is already close to being sorted, Insertion Sort performs efficiently.
- Real-Time Data: It can sort data as it arrives, making it suitable for real-time applications.

## Applications of Insertion Sort
1. Small Datasets: Ideal for sorting small amounts of data.
1. Nearly Sorted Data: Works efficiently when the data is already partially sorted.
1. Real-Time Data: Great for scenarios where data is continuously added and needs to be sorted on the fly.
1. Stable Sorting: Maintains the order of equal elements, making it useful in specific applications.
1. Space Constraints: Uses minimal extra space, making it suitable for memory-limited environments.

# Quick Sort
Quick Sort is a divide-and-conquer algorithm that breaks a big problem into smaller pieces, solves them, and then combines the results. It’s like organizing a messy pile of books step by step, one small section at a time.

1. **Choose a pivot element:** Pick one element from the array to be the pivot.
1. **Partition the array:** Rearrange the elements so that all items smaller than the pivot go to its left, and all items larger go to its right.
1. **Repeat:** Apply the same steps to the left and right parts of the array until everything is sorted.

## Quick Sort in Action
Imagine you have a pile of numbers: [8, 3, 2, 7, 9, 6, 5]. Let’s sort them using Quick Sort.

### Step 1: Choose a Pivot
We need to pick a pivot element. There are many ways to choose it, but for simplicity, let’s always pick the last element. So, in this case, the pivot is 5.

### Step 2: Partition the Array
Now, we rearrange the numbers around the pivot 5. The goal is:

- All numbers less than or equal to 5 go to the left.
- All numbers greater than 5 go to the right.
Here’s how it looks after partitioning:

- Left side: [3, 2]
- Pivot: 5
- Right side: [8, 7, 9, 6]
After partitioning, the pivot is placed in its correct sorted position in the array. It now looks like this: [3, 2, 5, 8, 7, 9, 6]

### Step 3: Recursively Apply Quick Sort
Next, we repeat the process on the left and right parts of the array:

1. For the left part [3, 2]:
- Pivot: 2
- Partition: [2, 3] (now sorted).

2. For the right part [8, 7, 9, 6]:

- Pivot: 6
- Partition: [6, 7, 8, 9] (now sorted).
3. Finally, combine everything: [2, 3, 5, 6, 7, 8, 9].


## Quick Sort in C++
```cpp
#include <iostream>using namespace std;
// Function to partition the array
int partition(int arr[], int low, int high) {
    int pivot = arr[high]; // Choosing the last element as pivot
    int i = low - 1; // Index for smaller element
    for (int j = low; j < high; j++) {
        if (arr[j] <= pivot) {
            i++;
            swap(arr[i], arr[j]); // Swap if element is smaller than pivot
        }
    }
    swap(arr[i + 1], arr[high]); // Place pivot in its correct position
    return i + 1; // Return partition index
}
// Function to perform Quick Sort
void quickSort(int arr[], int low, int high) {
    if (low < high) {
        int pi = partition(arr, low, high);
        quickSort(arr, low, pi - 1); // Sort left side
        quickSort(arr, pi + 1, high); // Sort right side
    }
}
// Function to print the array
void printArray(int arr[], int size) {
    for (int i = 0; i < size; i++)
        cout << arr[i] << " ";
    cout << endl;
}
int main() {
    int arr[] = {8, 3, 2, 7, 9, 6, 5};
    int n = sizeof(arr) / sizeof(arr[0]);
    cout << "Original Array: ";
    printArray(arr, n);
    quickSort(arr, 0, n - 1);
    cout << "Sorted Array: ";
    printArray(arr, n);
    return 0;
}
```

## Output
```console
Original Array: 8 3 2 7 9 6 5
Sorted Array: 2 3 5 6 7 8 9
```

## Quick Sort in Java
```java
class QuickSort {
    // Function to partition the array
    static int partition(int arr[], int low, int high) {
        int pivot = arr[high]; // Choosing the last element as pivot
        int i = low - 1; // Index for smaller element
for (int j = low; j < high; j++) {
            if (arr[j] <= pivot) {
                i++;
                // Swap if element is smaller than pivot
                int temp = arr[i];
                arr[i] = arr[j];
                arr[j] = temp;
            }
        }
        // Place pivot in its correct position
        int temp = arr[i + 1];
        arr[i + 1] = arr[high];
        arr[high] = temp;
        return i + 1; // Return partition index
    }
    // Function to perform Quick Sort
    static void quickSort(int arr[], int low, int high) {
        if (low < high) {
            int pi = partition(arr, low, high);
            quickSort(arr, low, pi - 1); // Sort left side
            quickSort(arr, pi + 1, high); // Sort right side
        }
    }
    // Function to print the array
    static void printArray(int arr[]) {
        for (int num : arr) {
            System.out.print(num + " ");
        }
        System.out.println();
    }
    public static void main(String args[]) {
        int arr[] = {8, 3, 2, 7, 9, 6, 5};
        System.out.print("Original Array: ");
        printArray(arr);
        quickSort(arr, 0, arr.length - 1);
        System.out.print("Sorted Array: ");
        printArray(arr);
    }
}
```
## Output
```console
Original Array: 8 3 2 7 9 6 5
Sorted Array: 2 3 5 6 7 8 9
```

## Quick Sort in Python
```python
def partition(arr, low, high):
    pivot = arr[high]  # Choosing the last element as pivot
    i = low - 1  # Index for smaller element
for j in range(low, high):
        if arr[j] <= pivot:
            i += 1
            arr[i], arr[j] = arr[j], arr[i]  # Swap if element is smaller than pivot
    arr[i + 1], arr[high] = arr[high], arr[i + 1]  # Place pivot in correct position
    return i + 1  # Return partition index
def quick_sort(arr, low, high):
    if low < high:
        pi = partition(arr, low, high)
        quick_sort(arr, low, pi - 1)  # Sort left side
        quick_sort(arr, pi + 1, high)  # Sort right side
arr = [8, 3, 2, 7, 9, 6, 5]
print("Original Array:", arr)
quick_sort(arr, 0, len(arr) - 1)
print("Sorted Array:", arr)
```

## Output
```console
Original Array: [8, 3, 2, 7, 9, 6, 5]
Sorted Array: [2, 3, 5, 6, 7, 8, 9]
```

## Why is Quick Sort So Powerful?
Quick Sort is fast because it sorts by dividing the array into smaller and smaller parts, making it efficient for large datasets. Here are some key advantages:

1. Efficiency: It’s much faster than simple methods like Bubble Sort.
1. In-Place: It doesn’t need extra space to work, saving memory.
1. Flexibility: It works well for most types of data.










