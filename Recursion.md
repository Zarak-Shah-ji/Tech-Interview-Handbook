# Parts of Recursion function

  Base case - when to stop the recursion
  Recursive call -  Breaking problem into smaller subproblem invoking recursive call

  e.g Fibonacci series
    def fib(n):
      if n <= 1:
        return n
      return fib(n-1) + fib(n-2)

# Things to look out for during interviews:
  1. Always define a base case so that recursion will end
  2. Recursion is useful for permutation because it generates all combinations and tree based questions.
  3. Learn how to generate all permutations of a sequence as well as how to handle duplicates
  4. Recursion implicity uses a stack, so all recursive approaches can be rewritten iteratively using a stack
  5. Beware of cases where recursion goes where the recursion level goes too deep and causes a stack overflow (the default limit in Python is 1000)  - BONUS POINTS TO POINT OF THAT
  6. Recursion will never be O(1) space complexity because a stack is involed, unless there is tail-call optimization (TCO)
  7. Number of base cases - Cover all possible invocations of the function within the input range


# Corner cases:
n = 0
n = 1
Make sure you have enough base cases to cover all possible invocations of the recursive function

# Techniques:

Memoization:
  In some cases, you may be computing the result for previously computed inputs. 
    Let's look at the Fibonacci example again. fib(5) calls fib(4) and fib(3),
    and fib(4) calls fib(3) and fib(2). fib(3) is being called twice! 
    If the value for fib(3) is memoized and used again, that greatly improves the efficiency of the algorithm and the time complexity becomes O(n).

     
