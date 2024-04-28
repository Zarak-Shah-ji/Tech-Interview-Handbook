# Commom Data structures for looking up  strings

1. Trie/ Prefix Tree
2. Suffix Tree


# Common String Algorithms:

1. Rabin Karp : for efficient searching of substring using a rolling hash
2. KMP : for efficient searching of subtring


# Time Complexity

  1. Access O(1)
  2. Search O(n)
  3. Insert O(n)
  4. Remove O(n)

  1. Find Substring O (n.m)
  2. Concatenating Strings  O (n+m)
  3. Slice  O(m)
  4. Split (by token) O(n+m)
  5. Strip (remove leading and trailig whitespaces O(n)
  
  # Things to look out for during interviews

  Ask about input character set and case sensitivity. Usually characters are limited to lowercase latin characters, e.g a to z

# Corner cases
  1. Empty string
  2. String with  1 or 2 characters
  3. String with repeated char
  4. String with only distinct char

# Techniques 

  1. Counting characters: Frequency of char, use Hash table / map or counter class in Python. Counter space is O(1) as fixed size of 26 char
  2. String of unique Characters: use 26-bit bitmask
 # Code 

     mask = 0
     for c in word:
     mask |= (1 << (ord(c) - ord ('a')))
  3. Determine two strings have common char: Perform & on 2 bitmasks, if mask_a & mask_b > 0 then common char present
  4. Anagram: rearrange letters of word/phrase to produce new word/phrase
         #Code
             
               1. Sorting both strings produce same string O(n.logn time and O(log n) space
               2. Map each char to a prime num and we multiply each mapped number, anagrams should have same multiple. O(n) time and O(1) space e.g group anagrams
               3. Frequency counting of characters determine if anagram or not O(n) time and O(1)
  5. Word /phrase / number reads same backwards and forward:
      #Code

           1. Reverse string and it should be equal to itself
           2. 2 pointers at start and end of string , move pointers inward till they meet , check at very point if char at both pointers are matching

     Note: Order of characters matter, so hash table not useful
       Question of counting number of palindromes: 2 ptrs moving outard from middle, 
                                                   For each middle pivot pos, check twice, once with the char and once without e.g Longest Palindromic subtstring
  
