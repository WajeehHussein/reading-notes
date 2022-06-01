# Reading Day3

## [Home Page](/README.md) 

## Big O: Analysis of Algorithm Efficiency

### efficiency is evaluated based on 2 factors:

1. Running Time (also known as time efficiency / complexity)
    >The amount of time a function needs to complete.

2. Memory Space (also known as space efficiency / complexity)
    >The amount of memory resources a function uses to store data and instructions.

Big O: calculate the efficiency to describe the Worst Case

### we should consider 4 Key Areas for analysis:
1. Input Size
2. Units of Measurement
3. Orders of Growth
4. Best Case, Worst Case, and Average Case

## Conclusion

1. Big O: The worst case analysis of algorithm efficiency.
2. Running Time: The amount of time required for an algorithm to complete.
3. Memory Space: The amount of memory resources required for an algorithm to complete.
4. Input Size: Represented by the variable n, the total size of values used as parameters in an algorithm.
5. Big Omega: The best case analysis of algorithm efficiency.
6. Big Theta: The typical or random case used for analysis of algorithm efficiency.

# Linked List

A Linked List is a sequence of `Nodes` that are connected/linked to each other


When traversing a linked list, you are not able to use a foreach or for loop. We depend on the Next value in each node to guide us where the next reference is pointing.

    >Head is always the first node in a Linked List

### The best way to approach a traversal is through the use of a while() loop. This allows us to continually check that the Next node in the list is not null.


Traversal Big O
The Big O of time for Includes would be O(n). This is because, at its worse case, the node we are looking for will be the very last node in the linked list. n represents the number of nodes in the linked list.

The Big O of space for Includes would be O(1). This is because there is no additional space being used than what is already given to us with the linked list input.

### Lists for all shapes and sizes
- Singly linked lists.
- Double linked lists.
- circular linked list

### different  between arrays and linked lists:
- Memory management
-  arrays are static data structures, while linked lists are dynamic data structures. 


