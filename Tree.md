# Intro 

A tree is a widely used abstract data type that represents a hierarchical structure with a set of connected nodes

A tree is an undirected and connected acyclic graph. There are no cycles or loops. Each node can be like the root node of its own subtree, making recursion a useful technique for tree traversal.


Trees are commonly used to represent hierarchical data, e.g. file systems, JSON, and HTML documents


# Common terms

  1. Neighbor - Parent or child of a node
  2. Ancestor - A node reachable by traversing its parent chain
  3. Descendent - A node in the node's subtree
  4. Degree - Number of children of a node
  5. Degree of a tree - Max degree of nodes in the tree
  6. Distance - No of edges along the shortest path between two nodes
  7. Level / Depth - No of edges along the unique path between a node and the root node
  8. Width - Number of nodes in a level

# Binary tree
  Binary means TWO so nodes in a binary tree have a maximum of two children.


  Binary tree terms

    Complete binary tree :  A complete binary tree is a binary tree in which every level, except possibly the last,
    is completely filled, and all nodes in the last level are as far left as possible.

    Balanced Binary tree : A BT in which the left and right subtrees of every node differ in height by no more than 1


  # Traversals:
     FOR each node follow the below patterns 

    1. In order    LEFT -> ROOT -> RIGHT
    2. Pre order   ROOT -> LEFT -> RIGHT
    3. Post order  LEFT -> RIGHT -> ROOT

    Note that in-order traversal of a binary tree is insufficient to uniquely serialize (reconstruct OG tree) a tree. Pre-order or post-order traversal is also required. 


  # Binary Search Tree

      In-order traversal of a BST will give you all elements in order.

  It's a binary tree with the following properties:

    1. Each node has at most two children, referred to as the left child and the right child.
    2. For each node:
   
          All nodes in its left subtree have values less than the node's value.
          All nodes in its right subtree have values greater than the node's value.
     3. Both the left and right subtrees must also be binary search trees.


  # TIME Complexity

    Access   O(log(n))
    Search   O(log(n))
    Insert   O(log(n))
    Remove   O(log(n))

   When a question involves a BST, the interviewer is usually looking for a solution which runs faster than O(n).

   # Space

     Space complexity of traversing balanced trees is O(h) where h is the height of the tree,
     while traversing very skewed trees (which is essentially a linked list) will be O(n).


  # THINGS TO LOOK OUT FOR DURING INTERVIEWS:
    You should be very familiar with writing pre-order, in-order, and post-order traversal recursively
      As an extension, challenge yourself by writing them iteratively. 
      Sometimes interviewers ask candidates for the iterative approach, especially if the candidate finishes writing the recursive approach too quickly.

# Corner cases

  1. Empty tree
  2. Single node
  3. Two nodes
  4. Very skewed tree (like a linked list)

# Common routines

  1. Insert value
  2. Delete Value
  3. Count number of nodes in tree
  4. Whether a value is in tree
  5. Calculate height of tree
  6. Binary search tree
  7.     Determine if it is binary search tree
  8.     Get max value
  9.     Get min value


# TECHNIQUES:

  Use Recursion:

    Recursion is the most common approach for traversing trees. When you notice that the subtree problem can be used to solve the entire problem, try using recursion.

    When using recursion, always remember to check for the base case, usually where the node is null.

     Sometimes it is possible that your recursive function needs to return two values.

  Traversing by level - use BFS

  Summation of nodes - In summation of nodes along the way, be sure to check whether nodes can be negative

# Points to remember :
1 . Subtree are also trees
2 . Considering the above point just calling the method over the left subtree and right subtree recursively will solve almost any problem
  
