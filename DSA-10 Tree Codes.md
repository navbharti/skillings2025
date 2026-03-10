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

# Binary Data Structure

# Binary Search Tree (BST)

# AVL Tree 
