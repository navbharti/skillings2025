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

# Binary Data Structure

# Binary Search Tree (BST)

# AVL Tree 
