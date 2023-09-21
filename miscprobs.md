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

Review:

1 - I can now do this problem by reading my notes for the future.

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


## Group Anagrams

**Given an array of strings strs, group the anagrams together. You can return the answer in any order.**

Initial thought process:

This will use a similar ideology to the valid anagram problem, however requires you to check every value in the list/array strs. Take the algorithm from the initial solution, and wrap it in an iterator to move through each value in the list. Add the first value to a list, then compare it to each value in strs, using a set .

Notes for future:

Use the fact that the character will all be lowercase, so there are only 26 possible characters (a-z). This means we can use a hashmap called count, which stores the number of occurrences of each character in each string. Now we know that if the keys of the maps match, the strings can be made the values corresponding to the keys.

The hashmap:

```
    res =  defaultdict(list) # mapping charCount to a list of anagrams

    ord(c) # this takes the ASCII value of the character input

```

Remember that lists cannot be keys as they are mutable, so when assiging the list 'count' to a key, convert it to a tuple.

## Top K Frequent Elements

**Given an integer array nums, and an integer k, return the k most frequent elements. You may return the answer in any order.**

Initial thought process:

Use a hashmap to store the integer in the array nums as the key, and the number of occurrences as it's value. Sort the map by values (in descending order) and return the top k most frequent using a loop.

Notes for future:

Use a max heap, then pop k number of values from the heap. We use a bucket sort, and reverse the logic of the hashmap as I initally thought, where the key is used as the count, and the value is the integer that occurs *key* times. The hashmap is the same length as the input array, as that is the maximum number of times a value can occur. When constructing the output array, just iterate throught the count hashmap in reverse, in order to take the top k values.

```
    freq = [[] for i in range(len(nums) + 1)] # construct an array that is the same length as the input array, that stores an array in each index, which is a list of the integers that occur i (index) number of times.

```

## Product of Array Except Self

Initial thought process:

Use a hashmap, with keys being the index of the array, and the value being the product of all the values, except the index.

Notes for future:

We take the product of every value before the index chosen, and every value after it, then take their products. To do this, we make an output array, which includes the product of everything ahead of the index multiplied by the product of everything ahead of the index.




