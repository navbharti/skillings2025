# Dynamic Programming

Dynamic Programming is an algorithmic technique with the following properties.

- An optimization over traditional recursion. Wherever we see a recursive solution that has repeated calls for the same inputs, we can optimize it using Dynamic Programming.
- The idea is to store the results of subproblems so that we do not have to re-compute them when needed later. This simple optimization typically reduces time complexities from exponential to polynomial.
- Some popular problems solved using Dynamic Programming are Fibonacci Numbers, Diff Utility (Longest Common Subsequence), Bellman–Ford Shortest Path, Floyd Warshall, Edit Distance and Matrix Chain Multiplication.

Method used to solve complex problems by breaking them into smaller overlapping subproblems and storing their results to avoid recomputation. 

# Why Dynamic Programming?
When we try to solve complex problems, especially those involving choices or sequences, we often notice that the same smaller problems appear again and again. If we solve them every time from scratch, it leads to unnecessary repetition and wasted computation.

Dynamic Programming helps us avoid this. Instead of recomputing results, we remember (or store) the solutions of smaller problems and reuse them when needed.
This simple idea of remembering the past to solve the future in faster forms is the core of DP.


The core idea behind DP is to store solutions to subproblems so that each is solved only once.
To solve DP problems, we first write a recursive solution in a way that there are overlapping subproblems in the recursion tree (the recursive function is called with the same parameters multiple times).
To make sure that a recursive value is computed only once (to improve time taken by algorithm), we store results of the recursive calls.
There are two ways to store the results, one is top down (or memoization) and other is bottom up (or tabulation).


# When to Use Dynamic Programming (DP)?
When the problems consists of the following characteristics:

## 1. Optimal Substructure:
The property Optimal substructure means that we use the optimal results of subproblems to achieve the optimal result of the bigger problem.

Example:

Consider the problem of finding the minimum cost path in a weighted graph from a source node to a destination node. We can break this problem down into smaller subproblems:

Find the minimum cost path from the source node to each intermediate node.
Find the minimum cost path from each intermediate node to the destination node.
The solution to the larger problem (finding the minimum cost path from the source node to the destination node) can be constructed from the solutions to these smaller subproblems.

## 2. Overlapping Subproblems:
The same subproblems are solved repeatedly in different parts of the problem refer to Overlapping Subproblems Property in Dynamic Programming.

Example:

Consider the problem of computing the Fibonacci series. To compute the Fibonacci number at index n, we need to compute the Fibonacci numbers at indices n-1 and n-2. This means that the subproblem of computing the Fibonacci number at index n-2 is used twice (note that the call for n - 1 will make two calls, one for n-2 and other for n-3) in the solution to the larger problem of computing the Fibonacci number at index n. 

You may notice overlapping subproblems highlighted in the second recursion tree for Nth Fibonacci diagram shown below.



# Approaches of Dynamic Programming (DP)
Dynamic programming can be achieved using two approaches:

## 1. Top-Down Approach (Memoization):
In the top-down approach, also known as memoization, we keep the solution recursive and add a memoization table to avoid repeated calls of same subproblems.

Before making any recursive call, we first check if the memoization table already has solution for it.
After the recursive call is over, we store the solution in the memoization table.
## 2. Bottom-Up Approach (Tabulation):
In the bottom-up approach, also known as tabulation, we start with the smallest subproblems and gradually build up to the final solution.

- We write an iterative solution (avoid recursion overhead) and build the solution in bottom-up manner.
- We use a dp table where we first fill the solution for base cases and then fill the remaining entries of the table using recursive formula.
- We only use recursive formula on table entries and do not make recursive calls.


Example of Dynamic Programming (DP)
Example 1: Consider the problem of finding the Fibonacci sequence:

Fibonacci sequence: 0, 1, 1, 2, 3, 5, 8, 13, 21, 34, ...

Brute Force Approach: To find the nth Fibonacci number using a brute force approach, you would simply add the (n-1)th and (n-2)th Fibonacci numbers.





```c++
#include <iostream>
using namespace std;

// Function to find nth fibonacci number
int fib(int n) {
    if (n <= 1) {
        return n;
    }

    return fib(n - 1) + fib(n - 2);
}

int main() {
    int n = 5;
    cout << fib(n);
    return 0;
}
```

```c
#include <stdio.h>

// Function to find nth fibonacci number
int fib(int n) {
    if (n <= 1) {
        return n;
    }
    return fib(n - 1) + fib(n - 2);
}

int main() {
    int n = 5;
    printf("%d", fib(n));
    return 0;
}
```

```java
class Fibonacci {
  
    // Function to find nth fibonacci number
    static int fib(int n) {
        if (n <= 1) {
            return n;
        }
        return fib(n - 1) + fib(n - 2);
    }

    public static void main(String[] args) {
        int n = 5;
        System.out.println(fib(n));
    }
}
```


```python
# Function to find nth fibonacci number
def fib(n):
    if n <= 1:
        return n
    return fib(n - 1) + fib(n - 2)

if __name__ == "__main__":
    n = 5
    print(fib(n))

```


# How will Dynamic Programming (DP) Work?
- Identify Subproblems: Divide the main problem into smaller, independent subproblems, i.e., F(n-1) and F(n-2)
- Store Solutions: Solve each subproblem and store the solution in a table or array so that we do not have to recompute the same again.
- Build Up Solutions: Use the stored solutions to build up the solution to the main problem. For F(n), look up F(n-1) and F(n-2) in the table and add them.
- Avoid Recomputation: By storing solutions, DP ensures that each subproblem (for example, F(2)) is solved only once, reducing computation time.


# Using Memoization Approach - O(n) Time and O(n) Space
To achieve this in our example we simply take an memo array initialized to -1. As we make a recursive call, we first check if the value stored in the memo array corresponding to that position is -1. The value - 1 indicates that we haven't calculated it yet and have to recursively compute it. The output must be stored in the memo array so that, next time, if the same value is encountered, it can be directly used from the memo array.   

```c++
#include <iostream>
#include <vector>
using namespace std;

int fibRec(int n, vector<int> &memo) {
  
    // Base case
    if (n <= 1) {
        return n;
    }

    // To check if output already exists
    if (memo[n] != -1) {
        return memo[n];
    }

    // Calculate and save output for future use
    memo[n] = fibRec(n - 1, memo) + fibRec(n - 2, memo);

    return memo[n];
}

int fib(int n) {
    vector<int> memo(n + 1, -1);
    return fibRec(n, memo);
}

int main() {
    int n = 5;
    cout << fib(n);
    return 0;
}
```

```java
import java.util.Arrays;

class GFG {

    static int fibRec(int n, int[] memo) {

        // Base case
        if (n <= 1) {
            return n;
        }

        // To check if output already exists
        if (memo[n] != -1) {
            return memo[n];
        }

        // Calculate and save output for future use
        memo[n] = fibRec(n - 1, memo) + fibRec(n - 2, memo);

        return memo[n];
    }

    static int fib(int n) {
        int[] memo = new int[n + 1];
        Arrays.fill(memo, -1);
        return fibRec(n, memo);
    }

    public static void main(String[] args) {
        int n = 5;
        System.out.println(fib(n));
    }
}
```

```python
def fibRec(n, memo):
  
    # Base case
    if n <= 1:
        return n

    # To check if output already exists
    if memo[n] != -1:
        return memo[n]

    # Calculate and save output for future use
    memo[n] = fibRec(n - 1, memo) + \
              fibRec(n - 2, memo)
    return memo[n]

def fib(n):
    memo = [-1] * (n + 1)
    return fibRec(n, memo)
    
if __name__ == '__main__':
    n = 5
    print(fib(n))
```

# Using Tabulation Approach - O(n) Time and O(n) Space
In this approach, we use an array of size (n + 1), often called dp[], to store Fibonacci numbers. The array is initialized with base values at the appropriate indices, such as dp[0] = 0 and dp[1] = 1. Then, we iteratively calculate Fibonacci values from dp[2] to dp[n] by using the relation dp[i] = dp[i-1] + dp[i-2]. This allows us to efficiently compute Fibonacci numbers in a loop. Finally, the value at dp[n] gives the Fibonacci number for the input n, as each index holds the answer for its corresponding Fibonacci number.

```c++
#include <iostream>
#include <vector>
using namespace std;

// Function for calculating the nth Fibonacci number
int fibo(int n) {
    vector<int> dp(n + 1);

    // Storing the independent values in dp
    dp[0] = 0;
    dp[1] = 1;

    // Using the bottom-up approach
    for (int i = 2; i <= n; i++) {
        dp[i] = dp[i - 1] + dp[i - 2];
    }
  
    return dp[n];
}

int main() {
    int n = 5;
    cout << fibo(n);
    return 0;
}
```


```c
#include <stdio.h>

// Function for calculating the nth Fibonacci number
int fibo(int n) {
    int dp[n + 1];

    // Storing the independent values in dp
    dp[0] = 0;
    dp[1] = 1;

    // Using the bottom-up approach
    for (int i = 2; i <= n; i++) {
        dp[i] = dp[i - 1] + dp[i - 2];
    }
  
    return dp[n];
}

int main() {
    int n = 5;
    printf("%d", fibo(n));
    return 0;
}
```

```java
import java.util.Arrays;

// Function for calculating the nth Fibonacci number
class GfG {
    static int fibo(int n) {
        int[] dp = new int[n + 1];

        // Storing the independent values in dp
        dp[0] = 0;
        dp[1] = 1;

        // Using the bottom-up approach
        for (int i = 2; i <= n; i++) {
            dp[i] = dp[i - 1] + dp[i - 2];
        }

        return dp[n];
    }

    public static void main(String[] args) {
        int n = 5;
        System.out.println(fibo(n));
    }
}
```

```python
def fibo(n):
    dp = [0] * (n + 1)

    # Storing the independent values in dp
    dp[0] = 0
    dp[1] = 1

    # Using the bottom-up approach
    for i in range(2, n + 1):
        dp[i] = dp[i - 1] + dp[i - 2]
    
    return dp[n]

if __name__ == '__main__':
    n = 5
    print(fibo(n))
```

# Using Space Optimised Approach - O(n) Time and O(1) Space
In the above code, we can see that the current state of any fibonacci number depends only on the previous two values. So we do not need to store the whole table of size n+1 but instead of that we can only store the previous two values. 

```c++
#include <iostream>
using namespace std;

int fibo(int n) {
  
    int prevPrev, prev, curr;

    // Storing the independent values
    prevPrev = 0;
    prev = 1;
    curr = 1;

    // Using the bottom-up approach
    for (int i = 2; i <= n; i++) {
        curr = prev + prevPrev;
        prevPrev = prev;
        prev = curr;
    }

    return curr;
}

int main() {
    int n = 5;
    cout << fibo(n);
    return 0;
}
```

