# Time Complexity:

Algorithm	Time	Space

Bubble sort	O(n2)	O(1)

Insertion sort	O(n2)	O(1)

Selection sort	O(n2)	O(1)

Quicksort	O(nlog(n))	O(log(n))

Mergesort	O(nlog(n))	O(n)

Heapsort	O(nlog(n))	O(1)

Counting sort	O(n + k)	O(k)

Radix sort	O(nk)	O(n + k)

Algorithm	Big-O

Binary search	O(log(n))

Learning trick:
B _ I _ S --- O(n2)
Q _ M _ H ---- O(nlog(n)) 


# Interview tips

The time complexity is almost definitely O(nlog(n))). Bonus points if you can name the sort. In Python, it's Timsort. time O(nlog(n)) spae O(n)

 
# Corner cases
 
Empty sequences
Sequence with one element
Sequence wit 2 elements
Sequence containing duplicate elements

#Techniques 

Sorted Inputs : 
When sequence sorted any order asc or desc , try using binary search first

Sorting input with limited range :
Counting sort is a non-comparison based sort , can use on numbers where you know the range of values beforehand, e.g H-INDEX
