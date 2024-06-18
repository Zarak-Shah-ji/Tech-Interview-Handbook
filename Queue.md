# Intro


As an abstract data type, queues can be implemented using arrays or singly linked lists.
Breadth-first search is commonly implemented using queues.

# Implementations



Language	API
C++	std::queue
Java	java.util.Queue.Use java.util.ArrayDeque
Python	queue
JavaScript	N/A

# Time Complexity


Enqueue / Offer O(1)
Dequeue / Poll  O(1)
Front O(1)
Back O(1)
isEmpty O(1)

# Imp interview tips 

Often in Python list is used as Queue during interview, However, note that the dequeue operation (assuming the front of the queue is on the left) in such a scenario will be O(n) because it requires shifting of all other elements left by one

# Corner Cases:

  1. Empty queue
  2. Queue with one item
  3. Queue with two item

# Imp:

    1. Stacks push similar to queue's enqueue function
    2. Stacks pop  similar to queue's dequeue function
    3. Both of them can be implemented as array or linked list
