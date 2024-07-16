 # Intro

   Tries are special trees (prefix trees) that make searching and storing strings more efficient.
    Tries have many practical applications, such as conducting searches and providing autocomplete.


  # Time Complexity

  Search O(n)
  Insert O(n)
  Remove O(n)

  # Corner cases

    Searching for a string in an empty trie
    Inserting empty strings into a trie

  # Techniques

      Sometimes preprocessing a dictionary of words ( given in a list) into a trie, will improve the efficiency of 
      searching for a word of length k, among n words.
      Searching becomes O(k) insted of O(n)
