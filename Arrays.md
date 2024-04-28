# Arrays -  Mastery of array is essential for interviews!

Advantages:

        1. Store multiple elements of the same type with one single variable name
        2. Accessing elements is fast if we have the index as in linked list we need to traverse from head
        3. Constant time access to read and write

Disadvantages:

        1. Addition / Removal from middle is slow as all elements need to be shifted
        2. In C++ or other langs array size is fixed and need to create new array if array increases which takes O(n) time

 
Common Terms

        1. Subarray: A range of contiguous values within an array e.g [2,3,6,1,5,4] [3,6,1] is a subarray while [3,1,5] is not
        2. Subsequence: A sequence that can be derived from the given sequence by deleting some or no elements 
           without changing the order of the remaining elements e.g  [2,3,6,1,5,4] [3,1,5] is a subsequence and [3, 5, 1] is not

Time Complexity

        Access - O(1)
        Search  - O(n)
        Search sorted array - O(log(n))
  ![image](https://github.com/Zarak-Shah-ji/Tech-Interview-Handbook/assets/47606946/6139cc07-da1f-4f80-b949-e59ef8d1b0f2)

Things to Look out during interviews

        1. Clarify if there are duplicate values in the array. Would the presence of duplicate values affect the answer?
           Does it make the question simpler or harder ?
        2. When using an index to iterate through the array, be careful not to go out of bounds
        3. Be mindful about slicing or concatenating arrays in your code. Slicing and concatenating arr takes O(n) time. 
           Use start and end indices to demarcate a subbarray/ range where possible

Corner cases

        1. Empty Sequence
        2. Sequence with 1 or 2 elements only
        3. Sequence with repeated elements
        4. Duplicated values in the sequence

         String is an array of characters, thus most techniques below will apply to string problems

Patterns  
        <b> 
1. Sliding window: 
                Def: In a sliding window, the two pointers usually move in the same direction will never overtake each other. 
                This ensures that each value is only visited at most twice and the time complexity is still O(n).
                Type of qs: Subarray/ substring
                
                Template:
                
                             def findSubstring(s: str) -> int:
                                    map = [0] * 128
                                    counter = 0  # check whether the substring is valid
                                    begin, end = 0, 0  # two pointers, length of sliding window
                                    d = 0  # the length of substring

                                    while end < len(s): to expand the window 
                                       // if curr char already encountered
                                        if map[ord(s[end])]  > 0 or some :
                                            counter +/- = 1 
                                        map[ord(s[end])] +/-= 1
                                        end += 1
                                
                                        while counter  > 0: means we have duplicates in curr window 
                                            # Update d here if finding minimum
                                            # increase begin to make curr window invalid/valid again
                                            if map[ord(s[begin])] > 1: if true we have dups in curr window so decrement counter 
                                                counter + / - = 1
                                            map[ord(s[begin])] += 1
                                            begin += 1 // moved forward to shrink the window until there are no more 
                                            d=max(d, end-begin)  # or cond given in qs
                                
                                        # Update d here outside inner while if finding maximum
                                
                                    return d
 </b>
    2. Two Pointers : 
                Def: General version of sliding window where the pointers can cross each other and can be on different arrays.
                Qs Type: 2 arrays etc
                questions : Container with most water, Merge two sorted arrays
                
3. Traversing from the right:
   
                Def: traverse the array starting from the right instead of the conventional approach of from the left.
                Examples: Daily Temperatures, Number of Visible People in a Queue

5. Sorting the array:
                Is the array sorted or partially sorted? If it is, some form of binary search should be possible.
                This also usually means that the interviewer is looking for a solution that is faster than O(n).
                Can you sort the array? Sometimes sorting the array first may significantly simplify the problem.
                e.g Non-overlapping Intervals
<b>
                General pattern for greedy approach based Interval questions, where you sort the array first:
   
                        Arr.sort() # sorts array in-place
                        Prev = 0
                        for i in range(1,arr.len()):
                        	Curr = arr[i]
                        	If overlap(prev,curr):
                        		//do business logic
                        	Prev = curr	
                        Return res

                        def overlap(i2, i1):
                           //if the start of the second interval is greater or equal than the end of the first interval they dont overlap
                           // > or >= depends on the exact problem//
                           for example in some cases [4,6] [6,10] are considered overlapping, in some not
                        	if i2[0] >= i1[1]:
                                     Return false
                                Return True

   Obviously this would not work if the order of array elements need to be preserved. 
  </b>              

   6.  Precomputation:

                    For questions where summation or multiplication of a subarray is involved, pre-computation
                    using hashing or a prefix/suffix sum/product might be useful.
                    Examples: Product of Array Except Self, Minimum Size Subarray Sum, LeetCode questions tagged "prefix-sum"
          
      
   8. Index as a hash key:

                      If you are given a sequence and the interviewer asks for O(1) space,
                      it might be possible to use the array itself as a hash table.
                      For example, if the array only has values from 1 to N, where N is the length of the array,
                      negate the value at that index (minus one) to indicate presence of that number.
                      Examples: First Missing Positive, Daily Temperatures
   10. Traversing the array more than once:
      
                      This might be obvious, but traversing the array twice/thrice (as long as fewer than n times) is still O(n).
                      Sometimes traversing the array more than once can help you solve the problem while keeping the time complexity to O(n).
                      
