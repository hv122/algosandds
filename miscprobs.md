# Algorithms and Data Structures

NeetCode video to watch: https://www.youtube.com/watch?v=0K_eZGS5NsU
## Contains Duplicate

**Given an integer array nums, return true if any value appears at least twice, and return false if every element is distinct**

Initial thought process:

Create a second array of boolean values, and after checking every value in the array, if true is present in the second array, return true.

We can actually just break from the for loop when a repeat is found and return true, else if the entire for loop is completed for all iterations, return false.

Notes for future:

Main methods to solve this problem is to either sort the array into ascending order, so that we can just check neighbouring values for matches and return if identical.

Alternatively, we can utilise a hashset, where we check whether a certain value in the array exists in it, then add the value if not.

Syntax:
```
hashset = set()
hashset.add(x)
```

## Valid Anagram 

**Given two strings s and t, return true if t is an anagram of s, and false otherwise.**

Initial thought process:

This is similar to the previous question, and seems to require the use of hashmaps.

Notes for future:

This uses a hashmap, to store the letters present in each of the words and the number of occurences. 


Syntax:
```
hashmap.keys() // returns a list of all keys
hashmap.values() // returns a list of all values
hashmap.items() // returns a list of all key value pairs



countS = {} // initialises hashmap
countS.get(s[i], 0) // this 'gets' the value of the key s[i] - the ith character in a string s
sorted(s) // just returning the equation of these is a valid solution

```

## Two Sum

**Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.**

Initial thought process:

At first I thought of using a hashmap, but then realised that it would be difficult to keep track of the indices of the numbers - considered using tuples as the key, which would have the indices of the two numbers summed.


Notes for future:

The solution is to use a one pass solution, where for each number in the array, we search for the complement, being the target minus the number. We step through each value in the list provided, and check if `target-nums[i]` is present in the hashmap, returning the index at which it is, and the index of the current number if so, otherwise we add the current number to the hashmap. This question states that the two values will definitely be present in the hashmap, so we do not need to return anything if no pairs are present.







