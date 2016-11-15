# interview-questions
interview questions I have been asked


## General Question

1. Why do you pursue computer science?

## Programming Concept

1. Why do you like Python?

2. What are the advantages of python over other languages?

3. Why do you want to use linked list over array?
  * you need constant-time insertions/deletions from the list (such as in real-time computing where time predictability is absolutely critical)
  * you don't know how many items will be in the list. With arrays, you may need to re-declare and copy memory if the array grows too big
  * you don't need random access to any elements
  * you want to be able to insert items in the middle of the list (such as a priority queue)

4. When do you want to use array?
  * you need indexed/random access to elements
  * you know the number of elements in the array ahead of time so that you can allocate the correct amount of memory for the array
  * you need speed when iterating through all the elements in sequence. You can use pointer math on the array to access each element, whereas you need to lookup the node based on the pointer for each element in linked list, which may result in page faults which may result in performance hits.
  * memory is a concern. Filled arrays take up less memory than linked lists. Each element in the array is just the data. Each linked list node requires the data as well as one (or more) pointers to the other elements in the linked list.
  * Array Lists (like those in .Net) give you the benefits of arrays, but dynamically allocate resources for you so that you don't need to worry too much about list size and you can delete items at any index without any effort or re-shuffling elements around. Performance-wise, arraylists are slower than raw arrays.
  
  
## Technical Question

1. Write a function which takes a string as parameter. The function will return true if there are duplicated characters in the string, otherwise return false.

```python
def dupChar(s):
    
```
