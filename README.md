# interview-questions
interview questions I have been asked

## Tips

1. **Take a deep breath and relax.** Interviews are stressful for everyone, and there's a time pressure that you don't normally have when you're working, and it's natural to be anxious. Anxiety makes it hard to think clearly, so make an effort to calm yourself, so you can tackle the problem with a clear mind.
2. **Understand the problem.** Don't jump into the solution immediately. Take a moment to make sure you fully understand the problem and restate the problem to the interviewer to make sure you've understood it correctly. Many of the more complex problems are deliberately ambiguous for edge cases, and the interviewer is looking for your ability to analyze the problem.
3. **Create test cases.** Before moving on to implementation, create test cases, and write them on the whiteboard. Start with simple test cases before getting into edge cases. Write down at least 5 test cases before moving on. After you finish your solution, your final step will be to run your solution through the test cases. This also helps you confirm that you've successfully understood the problem.
4. **Overview strategy before pseudocoding.** It's easy to get bogged down in coding or pseudocoding. Discuss your basic plan before you write anything down.
5. **Start with a simple strategy before optimizing.** It's often better to warm up with a more naive strategy first, even it's not as efficient. Once you have that, you can work on creating a better strategy.
6. **Consider sorting or indexing first.** The trick for many problems is to organize your data first, either by sorting it or putting the data in a dictionary. This will often make your implementation strategy simpler as well as more efficient.
7. **Pseudocode before coding.** It's often better to start with pseudocode, so you can work through your strategy quicker. You can mingle code with pseudocode if you don't remember the exact syntax, and make a final pass at the end to fix syntax. Often, your interviewer cares the least about your ability to get correct language syntax, so don't waste too much time on it, so you can spend more time optimizing your solution.
8. **Evaluate your correctness.** After completing your solution, step through the test cases that you defined earlier and evaluate if they pass. Try to spot any additional test cases that could trip up your solution.
9. **Evaluate your efficiency.** Evaluate the big O efficiency of your solution, as well as its memory usage.

### When you get stuck....

1. **Take a moment.** Once you get stuck, it's easy to start panicking, which guarantees that you're not going to be at your best. If you find yourself going in circles, take a step back, stop thinking about the problem, and try to relax before jumping back into it.
2. **Don't stop talking.** Try to avoid being silent at all times in the interview. Be as chatty as you can about everything you're observing about the problem as you're working toward a solution. Talk aloud about approaches that you're thinking about, even if you think it's not correct. The interviewer generally wants to help you, but it's hard to help someone who's not talking. They can usually give you a good hint if they know exactly what you're thinking. Also, even if you don't solve the problem in the end, you'll be able to showcase your problem solving skills.

## Behavioral Question

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

2. Find all subsequences

```python
arr = [1, 2, 3, 4]

def all_subsequence(arr):
    result = []
    mylist = []
    length = len(arr)
    for count in xrange(length*length):
        for j in xrange(length):
            if count & (1<<j):
                mylist.append(arr[j])
        result.append(mylist)
        mylist = []

    return result

print all_subsequence(arr)
# [[], [1], [2], [1, 2], [3], [1, 3], [2, 3], [1, 2, 3], [4], [1, 4], [2, 4], [1, 2, 4], [3, 4], [1, 3, 4], [2, 3, 4], [1, 2, 3, 4]]
```
