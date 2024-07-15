
 # INTRO 

   Heap is a specialized tree based data structure which is complete tree that satisfies heap property

     MAX HEAP: Value of Node must be greatest among the node values in its entire subtree. Same property must be recursively true for all nodes in the tree

     MIN HEAP: Value of Node must be smallest among the node values in its entire subtree. Same property must be recursively true for all nodes in the tree

      In the context of algorithm interviews, heaps and priority queues can be treated as the same data structure.

      A heap is a useful data structure when it is necessary to repeatedly remove the object with the highest (or lowest) priority

        OR

      when insertions need to be interspersed with removals of the root node.

 

  # Implementations

  Language	API
  C++	            std::priority_queue
  Java	         java.util.PriorityQueue
  Python	       heapq
  JavaScript	   N/A


  # Time Complexity

  Find max /min           O(1)
  Insert                  O(log(n))
  Remove                  O(log(n))
  Heapify (create heap out of given array)    O (n)


  # TECHNIQUES

    MENTION OF K

      If you see a top or lowest k being mentioned in the question, it is usually a signal that a heap can be used to solve the problem

      If you require the top k elements use a Min Heap of size k
        1. Iterate through each element, pushing it into the heap (for python heapq, invert the value before pushing to find the max)
        2.  Whenever the heap size exceeds k, remove the minimum element, that will guarantee that you have the k largest elements.
     
