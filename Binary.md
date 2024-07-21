# Intro

Less asked to SWE more used for low level programmers.
Still atleast need to know to convert decimal to binary and vice versa


# Corner Cases

    1. Be aware and check for overflow / underflow
    2. Negative numbers



# Techniques

  Binary represntations and Bitwise operations
  
             TRICK                                CODE

     1.      Test kth bit is set                 num  & (1 << k) != 0
     2.      Set kth bit                         num |= (1 << k)
     3.      Turn off kth bit                    num &= ~(1 << k)
     4.      Toggle kth bit                      num ^= (1 << k)
     5.      Multiply by 2K                      num << k
     6.      Divide by 2k                        num >> k
     7.      Check if no is power of 2           (num & num -1) == 0  or (num & (-num)) == num
     8.      Swapping two variables              num1 ^= num2; num2 ^= num1; num1 ^= num2
    
