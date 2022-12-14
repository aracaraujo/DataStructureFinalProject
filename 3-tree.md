# Tree

## Introduction

You can think of a tree like a real tree but upside down. Instead of the branches going up they go down. Each node
of the tree is connected to another nodes like branches of a tree. There's several types of tress but we will look
more in three types of trees: binary trees, binary search trees, and balanced binary search trees.


## 1. Binary Trees

A Binary tree is a tree that each node is linked to no more than two nodes. The top node is called root node and is
from where the tree grows. In the relationship between two nodes the top node is called parent and the bottom node
is called child. 

The picture bellow illustrates a binary tree.

![Binary Tree example](Assets/TreePics/binaryTree.png)

## 2. Binary Search Trees

Binary trees are are a very common used of tress. A binary search tree (BST) follow a rule to insert data inside its
structure. The value to be inserted will follows the pattern that if is greater than the node it will go to the right
side of the node and if is smaller it will go to the left side of the node. If duplicates are allowed they can be added
in either sides of the root. Following this rule the data is stored in a sorted manner.

The picture bellow illustrates a binary search tree (BST).


![Binary Tree example](Assets/TreePics/binarySearchTree.png)

### Big O efficiency

The ability of adding values to a tree in a sorted manner using the the root node as the reference allows the search
efficiency to be O(log n). This efficiency comes from the ability of comparing a value and then splitting half of the
tree and repeating the process recursively. Yeah recursion is an essential part of working with trees.

## 3. Balanced Binary Search Trees

A balanced binary search tree (balanced BST) is a BST that is organized in a way that none of the subtrees are
dramatically higher than the other. It is also hard to keep track of these when the data is being added to the tree
so algorithms have been written to check if a tree is balanced and if not to fix it.

The following picture represents what would it be an unbalanced binary search tree.

![Binary Tree example](Assets/TreePics/unbalancedBinarySearchTree.png)

After applying one of the many options of algorithms that check and fix trees to make them balanced the following
picture would represent the same tree but now balanced.

![Binary Tree example](Assets/TreePics/balancedBinarySearchTree.png)

## Common Operations

We will be looking into two operations with trees. Insert, Traversing, and Contain.

### Insert

Because there's no data structure for trees in C#, trees are made through linking node objects in a way that represents
a tree. Each node contains a pointer to the left and right node attached to them and its one value. The root node also
is has a value to indicate that is the root.

The insert process uses two insert functions. A insert function for the tree and another one for the nodes. The node
insert function will them be called recursively until the insert operation is done.

The code below represent both functions:

```csharp
public class BinarySearchTree {
    private Node? root;
    
    public void Insert(int value) {
        // Check if root exist. In case the tree is empty the first value will be
        // assigned as root. If root exists it will call the insert function in 
        // root which is the node Insert function mentioned above.
        if (root is null){
            root = new Node(value);
        }else{
            root.Insert(value);
        }
    }
}

public class Node {
    // The function below represents the insert function of the node object
    // This node object isn't complete. The purpose here is only displays
    // how the insert function works
    public void  Insert(int value){
        if (value < data) {
            if (Left is null){
                Left = new Node(value);
            }else{
                Left.Insert(value);
            }
        }else{
            if (Right is null){
                Right = new Node(value);
            }else{
                Right.Insert(value);
            }
        }
    }
}   
```

### Traversing A BST

The traversing method is used when you want to display the data in the tree. Like we said because the tree isn't a data
structure itself it doesn't have a method to print the values, so we need to create one.

```csharp
public class BinarySearchTree {
    private Node? root;
    
    public void Traverse(Node parent){
        if (parent != null){
            Traverse(parent.Left);
            Console.Write(parent.Data + " ");
            Traverse(parent.Right);
        }
    }
}
```

### Contain

Contain is another frequent method used in trees. The contain method will help us check if a value exists or not inside
the tree. Again we will have a contain method inside the tree class and another one for the node class. The code below
presents both contain methods:

```csharp
public class BinarySearchTree {
    private Node? root;
    // Check if root is the value being searched. If is not root it will call the node contain method.
    // It will use recursion again inside the nodes to search for the value.
    public void Contain(int value) {
        return root != null && root.Contain(value);
    }
}

public class Node {
    public void Contain(int value){
        //Check if the node value is the value being searched.
        bool result = value == Data;
        // If not it will check if the value is bigger or small to decide if it will look Left or Right.
        if (value < Data && Left != null) {
            result = Left.Contains(value);
        }
        if (value > Data && Right != null){
            result = Right.Contains(value);
        }
        // When reaches the point that the value of the node is the values being searched it won't go into
        // any of the if statements then it will return and stop the recurstion. If never finds it will
        // return false when reaches the end of the tree.
        return result;
    }
}  
```

## Student Record Tree Example

The example that we will use for trees will be a student record. Each student that is registered for the school receives
a four digits identification number. To make have a quick access to the records the school will stored them using a tree.
The school has a random generator that gives the student their identification number.

The code below represents how the student records works:

```csharp
// Creates the student record out of the BST
BinarySearchTree studentRecord = new BinarySearchTree;
// Add the student identification numbers to the tree
studentRecord.Insert(5428);
studentRecord.Insert(2947);
studentRecord.Insert(0937);
studentRecord.Insert(9834);

// check if a number is being used already
Console.WriteLine(studentRecord.Contain(5428);
Console.WriteLine(studentRecord.Contain(5420);
```
Output
```
true
false
```

## Student Record Tree Problem

When the new Student Record system was being implemented in the school the math teacher realized that even though trees
are great in storing data in a efficient way the tree being implemented in their system had a problem. In the process of 
migrating from the old system to the new system the record number are not sorted and adding them would create an unbalanced
tree. Write a program that will take any list of numbers and will create a balanced out of it. Traverse the tree to sort
the values in a sorted manner too.

Below is an example of the output:

```
// Provide the list of numbers
Provide a record number (enter 0 when finish): 6150
Provide a record number (enter 0 when finish): 4915
Provide a record number (enter 0 when finish): 3369
Provide a record number (enter 0 when finish): 7863
Provide a record number (enter 0 when finish): 2689 
Provide a record number (enter 0 when finish): 5538
Provide a record number (enter 0 when finish): 8413 
Provide a record number (enter 0 when finish): 0
Your balanced tree has been created!
The identification numbers were sorted:
2689
3369
4915
5538
6150
7863
8413
```

You can check the solution here: [Solution](Tree-solution)




 