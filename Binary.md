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



# Convert a number from Decimal to Binary form in Python


    def decimal_to_binary(decimal_number):
        # If the number is 0, return '0'
        if decimal_number == 0:
            return '0'
        
        binary_number = ''
        
        # Continue to divide the number by 2 and store the remainder
        while decimal_number > 0:
            remainder = decimal_number % 2
            binary_number = str(remainder) + binary_number
            decimal_number = decimal_number // 2
        
        return binary_number
