# DSA Using Java Implementation

- Linear Data Structure
	- Array As List
	- Stack Array Implementation
	- Queue Array Implementation
	- Linked List
	- Stack Linked List Implementation
	- Queue Linked List Implementation
- Non-Linear Data Structure
	- Tree
		- Binary Tree
		- Ternary Tree
		- N-ary Tree
		- General Tree
- Graph
	- Graph Representation

# Linear Data Structure
# Array As List
```java
package array;

public class ArrayBasics {
	public static void main(String args[]) {
		//dataType[] arrayName; 
		//dataType arrayName[]; 
		//dataType[] arrayName = {value1, value2, value3, ...};
		//arrayName = new dataType[size];
		
		int[] numbers;
		byte[] byteArray = {10, 20, 30, 40};
		short[] shortArray = {100, 200, 300, 400};
		int[] intArray = {1, 2, 3, 4, 5};
		long[] longArray = {10000000000L, 20000000000L};
		float[] floatArray = {1.2f, 3.4f, 5.6f};
		double[] doubleArray = {1.23, 4.56, 7.89};
		boolean[] booleanArray = {true, false, true};
		char[] charArray = {'a', 'b', 'c', 'd'};
		int firstNumber = intArray[0]; // Accesses the first element (which is 1)
		System.out.println(firstNumber);
	}
}

```

```java
package array;

public class ArrayInit {

	public static void main(String[] args) {
		int arr[] = {0};
		System.out.println(arr[0]+ " "+ arr.length);
		
		int arr1[] = new int[]{0};
		System.out.println(arr1[0]+ " "+ arr1.length);
		
	}

}

```

```java
package array_operations;

public class ArrayCreation {

	public static void main(String[] args) {
		//declare
		int arr[];
		arr = new int[5];
		arr[0] = 10;
		System.out.println(arr);
		
		//traverse
		for(int i=0; i<arr.length; i++) {
			System.out.println(arr[i]);
		}
	}

}

```

```java
package array_operations;
import java.util.ArrayList;
import java.util.Arrays;
import java.util.Scanner;

public class DynamicInputArray {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        // Read the entire line as a string
        String line = scanner.nextLine();
        
        // Split the string by spaces into a String array
        String[] numbersStr = line.split(" ");
        
        // Create a new int array with the correct size
        int[] numbers = new int[numbersStr.length];
        
        // Convert string elements to integer elements
        for (int i = 0; i < numbersStr.length; i++) {
            numbers[i] = Integer.parseInt(numbersStr[i]);
        }
        
        
        // Close the scanner
        scanner.close();
        
        //reverse logic
        int i,j;
        for ( i = 0, j=numbers.length-1; i < numbers.length/2; i++, j--) {
            //System.out.println(numbers[i]);
        	int temp = numbers[i];
        	numbers[i] = numbers[j];
        	numbers[j] = temp;
        	
        }
        
        for (i = 0; i < numbers.length; i++) {
            System.out.print(numbers[i]+ " ");
        }
    }
}

```

```java

```
# Stack Array Implementation
```java

```
# Queue Array Implementation
```java

```
# Linked List
# Stack Linked List Implementation
# Queue Linked List Implementation
# Non-Linear Data Structure
# Tree
# Binary Tree
# Ternary Tree
# N-ary Tree
# General Tree
```java
package tree;

import java.util.ArrayList;

public class Node {
	int data;
	Node parent;
	ArrayList<Node> children;// = new ArrayList<>();
	
	public Node(int data) {
		this.children = new ArrayList<>();
		this.data = data;
	}
	
	//addChild(Node parent, Node child)
	public void addChild(Node child) {
		this.children.add(child);
	}

}

```

```java
package tree;

import java.util.LinkedList;
import java.util.Queue;

public class GeneralTree {
	Node root;
	
	//addChild(Node parent, Node child)
	public void addChild(Node parent, Node child) {
		parent.children.add(child);
		child.parent = parent;
	}
	
	//getNode(int data)
	public Node getNode(int data) {
		if(root == null) return null;
		Queue<Node> q = new LinkedList<>();
		
		q.add(root);
		
		while(!q.isEmpty()) {
			Node temp = q.remove();
			
			//System.out.print(temp.data+ " ");
			if(temp.data == data) return temp;
			
			for(int i = 0; i < temp.children.size(); i++)
				q.add(temp.children.get(i));
		}
		return null;
	}
	
	
	/**
     * Inserts a new node with childData as a child of the node with parentData.
     * If parentData is null or not found, and the tree is empty, sets the new node as the root.
     * 
     * @param parentData The data of the parent node.
     * @param childData The data of the new child node to insert.
     * @return true if the insertion was successful, false otherwise.
     */
    public boolean insert(int parentData, int childData) {
        Node newNode = new Node(childData);

        // Case 1: If the tree is empty and no parent specified, set as root.
        if (root == null) {
            if (parentData == 0) {
                root = newNode;
                return true;
            } else {
                System.out.println("Cannot insert child into an empty tree without specifying parent as null for the first node.");
                return false;
            }
        }

        // Case 2: Find the parent node using a Breadth-First Search (BFS) / Level order traversal
        Node parentNode = findNode(root, parentData);

        if (parentNode != null) {
            parentNode.addChild(newNode);
            return true;
        } else {
            System.out.println("Parent node with data '" + parentData + "' not found.");
            return false;
        }
    }

    /**
     * Helper method to find a node in the tree using BFS.
     */
    private Node findNode(Node startNode, int dataToFind) {
        if (startNode == null) return null;

        java.util.Queue<Node> queue = new java.util.LinkedList<>();
        queue.add(startNode);

        while (!queue.isEmpty()) {
            Node currentNode = queue.poll();

            if (currentNode.data == dataToFind) {
                return currentNode;
            }

            for (Node child : currentNode.children) {
                queue.add(child);
            }
        }
        return null; // Node not found
    }
	
	
	
	
	//traversal
	public void preOrder(Node root) {
		if(root==null) return;
		System.out.print(root.data + " ");
		for(int i=0; i<root.children.size(); i++) {
			preOrder(root.children.get(i));
		}
	}
	
	public void postOrder(Node root) {
		if(root==null) return;
		for(int i=0; i<root.children.size(); i++) {
			postOrder(root.children.get(i));
			}
		System.out.print(root.data+ " ");
		
	}
	
	public void levelOrder(Node root) {
		if(root == null) return;
		Queue<Node> q = new LinkedList<>();
		
		q.add(root);
		
		while(!q.isEmpty()) {
			Node temp = q.remove();
			
			System.out.print(temp.data+ " ");
			
			for(int i = 0; i < temp.children.size(); i++)
				q.add(temp.children.get(i));
		}
		
	}
	
	//delete Node
	
	
	public GeneralTree(int data){
		this.root = new Node(data);
		System.out.println("General Tree Create with Root as "+ root.data);
	}
	

}

```

```java
package tree;

public class GeneralTreeDemo {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		GeneralTree gt = new GeneralTree(12);
		Node n1 = new Node(34);
		Node n2 = new Node(900);
		Node n3 = new Node(55);
		gt.addChild(gt.root, n1);
		gt.addChild(gt.root, n2);
		gt.addChild(gt.root, n3);
		
		gt.addChild(n1, new Node(13));
		gt.addChild(n1, new Node(96));
		gt.addChild(n1, new Node(45));
		gt.addChild(n1, new Node(77));
		
		gt.addChild(n2, new Node(111));
		gt.addChild(n2, new Node(222));
		gt.addChild(n2, new Node(333));
		
		gt.addChild(n3, new Node(555));
		gt.addChild(n3, new Node(666));
		
		System.out.println("Pre Order Traversal: ");
		gt.preOrder(gt.root);
		
		System.out.println("Post Order Traversal: ");
		gt.postOrder(gt.root);
		
		System.out.println("Level Order Traversal: ");
		gt.levelOrder(gt.root);
		
		
		Node p = gt.getNode(900);
		System.out.println("Level Order of "+ p.data);
		gt.levelOrder(p);
		
	

	}

}

```
# Graph
# Graph Representation
