# Intro

Intervals are subset of array qs, where you are given an array of two-element arrays ( an interval ) 
and two values represent a start and end value

Intervals are part of array family qs but involve some common techniques hence they are extracted out
to a special section
e.g INTERVAL array : [[1, 2], [4,6]]

Interval qs are tricky if not tried before because of no of cases to consider when intervals overlap


# Things to Look out for during interviews:

  1. Clarfy if [1,2] and [2,3] are considered overlapping intervals as it affects how you write your quality checks
  2. Clarify if interval [a,b] will strictly follow a  < b ( a is smaller than b)


# Corner cases:

  1. No intervals
  2. Single interval
  3. Two intervals
  4. Non-overlapping intervals
  5. An interval totally consumed within another interval
  6. Duplicate intervals ( exactly same start and end)
  7. Intervals which start right where another interval ends [[1,2],[2,3]]


# Techniques


      1. Sort the arrays by its starting point
      2. Check if two intervals overlap
        def is_overlap(a,b):
          return a[0] < b[1] and b[0] < a[1]

          OR

          return b[0] >= a[1]

      3. Merging two intervals:

         def merge_overlapping_intervals(a,b):
           return [ min(a[0],b[0]) , max(a[1],b[1]) ]

      
