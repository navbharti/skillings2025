# Tree Data Structure
## Node class
```java
package binarytree;

public class Node {
	int data;
	Node leftChild;
	Node rightChild;
	
	Node(int data){
		this.data = data;
	}
}
	

```

## Demo class
```java
package binarytree;

public class Demo {

	static void inorder(Node root) {
		if(root == null) return;
		inorder(root.leftChild);
		System.out.print(root.data+ " ");
		inorder(root.rightChild);
	}
	
	static void preorder(Node root) {
		if(root == null) return;
		System.out.print(root.data+ " ");
		preorder(root.leftChild);
		
		preorder(root.rightChild);
	}
	
	static void postorder(Node root) {
		if(root == null) return;
		
		postorder(root.leftChild);
		
		postorder(root.rightChild);
		System.out.print(root.data+ " ");
	}
	
	public static void main(String[] args) {
		// TODO Auto-generated method stub
		Node root;
		Node n1 = new Node(10);
		root = n1;
		Node n2 = new Node(20);
		Node n3 = new Node(30);
		Node n4 = new Node(40);
		Node n5 = new Node(50);
		
		n1.leftChild = n2;
		n1.rightChild = n3;
		n3.leftChild = n4;
		n3.rightChild = n5;
		System.out.println("Inorder: ");
		inorder(root);
		
		System.out.println("\nPreorder: ");
		preorder(root);
		
		System.out.println("\nPostorder: ");
		postorder(root);
		
	}

}

```

# General Binary Tree Data Structure
## Insert Operation in General Binary Tree
```java
import java.util.LinkedList;
import java.util.Queue;

class GeneralBinaryTree {
  
    static Node insert(Node root, int data) {
        // check for empty case
        if (root == null)
            return new Node(data);
      
        //create a queue for level order traversal
        Queue<Node> q = new LinkedList<>();
        //enqueue root in the queue
        q.add(root);

      //traverse till queue is not empty
        while (!q.isEmpty()) {
            // deqeue a front element from queue
            Node curr = q.poll();

            //check for left child if left is null insert new node
          	//otherwise  enqueue left child to queue
            if (curr.left != null)
                q.add(curr.left);
            else {
                curr.left = new Node(data);
                return root;
            }

          //check for right child if right is null insert new node
          	//otherwise  enqueue right child to queue
            if (curr.right != null)
                q.add(curr.right);
            else {
                curr.right = new Node(data);
                return root;
            }
        }
        return root;
    }

    
}
```
## Delete Operation in General Binary Tree

```java
Node delete(Node root, int key) {
		if(root == null) return null;
		
		if(root.data == key && root.leftChild == null && root.rightChild == null) return null;
		
		Queue<Node> q = new LinkedList<>();
		q.add(root);
		
		Node keyNode=null;
		Node temp = null;
		Node deepestParent = null;
		
		while(!q.isEmpty()) {
			temp = q.poll();
			if(temp.data == key)
				keyNode = temp;
			
			if(temp.leftChild!=null) {
				q.add(temp.leftChild);
				deepestParent = temp;
			}
			if(temp.rightChild!=null) {
				q.add(temp.rightChild);
				deepestParent = temp;
			}
		}
		
		if(keyNode!=null)
			keyNode.data = temp.data;
		if(deepestParent.rightChild == temp)
			deepestParent.rightChild = null;
		if(deepestParent.leftChild==temp)
			deepestParent.leftChild = null;
		
		return root;
	}
```









```java
import java.util.LinkedList;
import java.util.Queue;
class GeneralBinaryTree {
  
    static void deletDeepest(Node root, Node dNode) {
        Queue<Node> q = new LinkedList<>();
        q.add(root);

        Node curr;
        while (!q.isEmpty()) {
            curr = q.poll();

            // If current node is the deepest node, delete it
            if (curr == dNode) {
                curr = null;
                dNode = null;
                return;
            }

            // Check the right child first
            if (curr.right != null) {
              
                // If right child is the deepest node, delete it
                if (curr.right == dNode) {
                    curr.right = null;
                    dNode = null;
                    return;
                }
                q.add(curr.right);
            }

            // Check the left child
            if (curr.left != null) {
              
                // If left child is the deepest node, delete it
                if (curr.left == dNode) {
                    curr.left = null;
                    dNode = null;
                    return;
                }
                q.add(curr.left);
            }
        }
    }

    // Function to delete the node with the given key
    static Node deletion(Node root, int key) {
      
        if (root == null)
            return null;

        // If the tree has only one node
        if (root.left == null && root.right == null) {
          
            // If the root node is the key, delete it
            if (root.data == key)
                return null;
            else
                return root;
        }

        Queue<Node> q = new LinkedList<>();
        q.add(root);

        Node curr = null;
        Node keyNode = null;

        // Level order traversal to find the deepest node and the key node
        while (!q.isEmpty()) {
            curr = q.poll();

            // If current node is the key node
            if (curr.data == key)
                keyNode = curr;

            if (curr.left != null)
                q.add(curr.left);

            if (curr.right != null)
                q.add(curr.right);
        }

        // If key node is found, replace its data with the deepest node
        if (keyNode != null) {
          
          	 // Store the data of the deepest node
            int x = curr.data; 
          
          	 // Replace key node data with  deepest node's data
            keyNode.data = x; 
          
          	 // Delete the deepest node
            deletDeepest(root, curr); 
        }
        return root;
    }
}
```
# Ternary Tree Data Structure

# N-ary Tree Data Structure

Here are the notes summarized from the text:

### **Introduction to Generic Trees (N-ary Trees)**

A Generic Tree is a collection of nodes where each node contains data and a list of references to its children. Unlike a linked list, each node can store the addresses of multiple nodes.

#### **Key Properties**

1. **Many Children:** Each node can have multiple children.
2. **Unknown Count:** The exact number of children for a specific node is not known in advance.
3. **Root:** A separate pointer that stores the address of the very first node.

![generictree](/images/generic-tree_1.png)
---

### **Representation Approaches**

#### **1. Fixed Pointer Approach (Naive)**

This method involves allocating pointers based on the "worst-case" scenario (the node with the maximum possible children).

* **Structure:** `Node` contains `data` and fixed pointers like `child1`, `child2`, ..., `childN`.
* **Disadvantages:**
* **Memory Wastage:** Significant memory is lost because most nodes will not use all allocated pointers.
* **Inflexibility:** Fails if a node needs more children than the pre-defined maximum.



#### **2. Dynamic Array Approach (Better)**

Instead of fixed pointers, a dynamic array (like `ArrayList` in Java) is used to store child references.

* **Pros:** Supports random access to children and the size is not fixed.
* **Code Example:**
```java
import java.util.ArrayList;
class Node {
    int data;
    ArrayList<Node> children;
    Node(int data) {
        this.data = data;
        this.children = new ArrayList<Node>();
    }
}

```



#### **3. First Child / Next Sibling Representation (Efficient)**

This is the most memory-efficient way to represent a generic tree by using only two pointers per node.

* **Logic:**
1. Link siblings (children of the same parent) from left to right.
2. The parent points only to its **first child**.
3. Each child points to its **next sibling**.

![generictree2](/images/generictree_2.png)

* **Node Declaration:**
```java
class Node {
    int data;
    Node firstChild;
    Node nextSibling;
}

```


* **Advantages:**
* **Memory Efficient:** No extra links or auxiliary arrays are required.
* **Binary Tree Compatibility:** Any generic tree can be treated and traversed like a binary tree using these pointers.
* **Fixed Size:** Every node has a constant, fixed size.


## Level Order Traversal of Generic (N-ary Tree)


## **1. Concept: Level Order Traversal**

Level Order Traversal (also known as **Breadth-First Search**) involves visiting all the nodes of a tree level by level, starting from the root, then moving to all its children (Level 1), then to all the children's children (Level 2), and so on.

### **Key Characteristics**

* Nodes at the same depth are processed before moving to the next depth.
* In a Generic Tree, since each node can have an **arbitrary number of children**, we typically store child references in a collection like an `ArrayList` or `Vector`.

---

## **2. The Algorithm**

The approach is identical to the Level Order Traversal of a binary tree, but instead of just checking "left" and "right" children, we iterate through the **entire list of children**.

### **Step-by-Step Process:**

1. **Initialize a Queue:** Create an empty queue and enqueue the `root` node into it.
2. **Iterate while Queue is not empty:**
* **Determine Level Size:** Capture the current size of the queue `n`. This represents the number of nodes at the current level.
* **Process Level:** Run a loop `n` times:
* **Dequeue:** Remove the front node from the queue.
* **Print:** Output the data of the dequeued node.
* **Enqueue Children:** Add all the children of the current node into the queue.


* **Level Break:** (Optional) Print a newline after the inner loop finishes to visually separate levels.



---

## **3. Java Implementation**

```java
import java.util.*;

class Node {
    int key;
    List<Node> children;

    Node(int key) {
        this.key = key;
        this.children = new ArrayList<>();
    }
}

public class GenericTreeTraversal {
    public static void levelOrderTraversal(Node root) {
        if (root == null) return;

        Queue<Node> queue = new LinkedList<>();
        queue.add(root);

        while (!queue.isEmpty()) {
            int levelSize = queue.size(); // Number of nodes at current level

            while (levelSize > 0) {
                // Dequeue and print
                Node current = queue.poll();
                System.out.print(current.key + " ");

                // Enqueue all children of the current node
                for (Node child : current.children) {
                    queue.add(child);
                }
                levelSize--;
            }
            // New line after each level
            System.out.println();
        }
    }

    public static void main(String[] args) {
        // Creating the example tree from the text
        Node root = new Node(10);
        root.children.add(new Node(2));
        root.children.add(new Node(34));
        root.children.add(new Node(56));
        root.children.add(new Node(100));

        root.children.get(0).children.add(new Node(77));
        root.children.get(0).children.add(new Node(88));
        root.children.get(2).children.add(new Node(1));
        root.children.get(3).children.add(new Node(7));
        root.children.get(3).children.add(new Node(8));
        root.children.get(3).children.add(new Node(9));

        System.out.println("Level Order Traversal:");
        levelOrderTraversal(root);
    }
}

```

---

## **4. Complexity Analysis**

* **Time Complexity:** $O(n)$
* Each node in the tree is visited exactly once.


* **Auxiliary Space:** $O(n)$
* In the worst case (a "star" tree where the root has $n-1$ children), the queue will store $n-1$ nodes at once.



---

## **5. Example Trace**

**Input Tree:**

```text
        10
      / | \
     2 34 56

```

1. **Queue:** `[10]` -> Pop `10`, Print `10`. Enqueue `2, 34, 56`.
2. **Queue:** `[2, 34, 56]` -> Pop `2`, Print `2`; Pop `34`, Print `34`; Pop `56`, Print `56`.
3. **Output:** 
```text
10
2 34 56
```

## Height of Generic Tree

## **1. Understanding the Problem**

In a parent array `parent[]`, each index `i` represents a node, and the value `parent[i]` represents its direct parent.

* **Root Node:** The index where `parent[i] == -1`.
* **Height:** The maximum number of edges from the root to any leaf node.

---

## **2. Approach 1: Using BFS (Building a Graph)**

Since the input is a parent array, we can't easily traverse "down" the tree. This approach converts the array into a more traversal-friendly format (Adjacency List).

### **Steps:**

1. **Build an Adjacency List:** Iterate through the `parent[]` array. For every `parent[i]`, add an edge between `i` and `parent[i]`.
2. **Find the Root:** Locate the index `i` where `parent[i] == -1`.
3. **Perform BFS:** Use a queue to traverse level by level, keeping track of the `level` count. The maximum level reached is the height.

### **Java Snippet (BFS Logic)**

```java
static int getTreeHeight(int root, List<List<Integer>> adj) {
    Queue<int[]> q = new LinkedList<>();
    int maxHeight = 0;
    q.add(new int[] { root, 0 }); // Node and its current level

    while (!q.isEmpty()) {
        int[] current = q.poll();
        int node = current[0];
        int level = current[1];

        maxHeight = Math.max(maxHeight, level);

        for (int neighbor : adj.get(node)) {
            // In a tree, we only move to children (not parent)
            // If using a general graph BFS, use a visited array
            q.add(new int[] { neighbor, level + 1 });
        }
    }
    return maxHeight;
}

```

---

## **3. Approach 2: Recursive Memoization (Most Efficient)**

This approach avoids building a graph. Instead, we calculate the height of each node by moving "up" to its parent. We use a **visited/height array** to store results and avoid redundant calculations.

### **The Logic:**

* To find the height of node `i`: `Height(i) = 1 + Height(parent[i])`.
* **Base Case:** If `parent[i] == -1`, height is 0.
* **Memoization:** If we already calculated the height of a node, return it immediately.

### **Java Implementation**

```java
static int fillHeight(int[] parent, int i, int[] heights) {
    // If root, height is 0
    if (parent[i] == -1) return 0;

    // If already calculated, return stored value
    if (heights[i] != 0) return heights[i];

    // Recursive step: 1 + height of parent
    heights[i] = 1 + fillHeight(parent, parent[i], heights);
    return heights[i];
}

```

---

## **4. Complexity Comparison**

| Feature | Naive Approach | BFS Approach | Memoization Approach |
| --- | --- | --- | --- |
| **Time Complexity** | O(n^2) | O(n) | O(n) |
| **Space Complexity** | O(1) | O(n) (Adjacency List) | O(n) (Recursion stack/array) |
| **Strategy** | Traverse up for every node | Build graph, then BFS | Recursive depth tracking |

---

> **Key Takeaway:** While BFS is more intuitive if you are used to graph traversals, the **Memoization** approach is often preferred in coding interviews because it is cleaner to implement and handles the "parent-only" data structure more naturally.





# Binary Search Tree (BST)

# AVL Tree 
