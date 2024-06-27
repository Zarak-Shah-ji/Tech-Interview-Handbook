
 # Advantages of LL

Insertion and deletion of a node in the list (given its location) is O(1) whereas in arrays the following elements will have to be shifted.

# Disadvantages

Access time is linear because directly accessing elements by its position in the list is not possible (in arrays you can do arr[4] for example). You have to traverse from the start.
  
# Types of Linked Lists

Singly Linked Lists,
Doubly Linked Lists,
Circular Linked Lists


# Time Complexity

Access O (n)

Search O (n)

Insert  O (1) Assumes you have traversed to insertion position

Remove O (1)  Assumes you have traversed to node to be removed


# Common routines

Be familiar with the following routines because many linked list questions make use of one or more of these routines in the solution:

 1. Counting the number of nodes in linked list
 2. Reversing a linked list
 3. Finding the middle node of the linked list using two pointers (fast/slow)
 4. Merging two linked lists together

# Corner cases

  1. Empty linked list (head is Null)
  2. Single Node
  3. Two Nodes
  4. Linked list has cycles. Tip: Clarify beforehand if there is cycle in list with interviewer, usually no cycle

# Techniques

 1. Sentinel / dummy nodes
   
    Adding a sentinel/dummy node at the head and/or tail might help to handle many edge cases where operations have to be performed at the head or the tail.
    The presence of dummy nodes essentially ensures that operations will never be done on the head or the tail,
    thereby removing a lot of headache in writing conditional checks to dealing with null pointers. Be sure to remember to remove them at the end of the operation.
2.  Two Pointers

     Used for:
    
     Getting kth from last node: - Have two pointers, where one is k nodes ahead of the other. When the node ahead reaches the end, the other node is k nodes behind
    
     Detecting cycles:  Have two pointers, where one pointer increments twice as much as the other, if the two pointers meet, means that there is a cycle
    
     Middle Node: - Have two pointers, where one pointer increments twice as much as the other. When the faster node reaches the end of the list, the slower node will be at the middle
    
    
 4. Using Space

    Many linked list problems can be easily solved by creating a new linked list and adding nodes to the new linked list with the final result.
    However, this takes up extra space and makes the question much less challenging.
    The interviewer will usually request that you modify the linked list in-place and solve the problem without additional storage.

5. Elegant modifications

    Unlike arrays where you can only modify the value at a position, for linked lists you can also modify the next pointer in addition to the value.

   Some operations to do that:

    Truncate a list : Set the next pointer to null at the last element
   
    Swapping values of nodes: Similar to array swap the values of two nodes, no need to swap the next ptr
   
    Combining two lists : attach the tail of the first list to the head of the second list








