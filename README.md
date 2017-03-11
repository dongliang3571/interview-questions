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

2. Where else are you applying/interviewing/considering offers?

  There is absolutely no obligation for you to have to tell a company where else you are applying/interviewing/considering offers. Some companies/HR departments will ask this question, and a nice fallback answer is simply, **"I'm not comfortable sharing that information at this time."** Do not feel bad or uncomfortable for pushing back on this!

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
  
5. Singly linked list and doubly linked list.

  | Singly Linked List | Doubly Linked List |
  | ------------------ |--------------------|
  | Singly linked list allows you to go one way direction, if you want to reversely read a singly linked list, we have to change the list struture | Doubly linked list has two way directions next and previous, if you want to reversly read a doublly linked list just read from ending node to beginning node |
  | Singly linked list uses less memory per node (one pointer) | Doubly linked list uses More memory per node than Singly Linked list (two pointers) |
  | There is a little-known trick that lets you delete from a singly-linked list in O(1), but the list must be circular for it to work (move the content of next into the current, and delete next). | Doubly-linked lists can be used in places where singly-linked lists would not work (a doubly-ended queue), but they require slightly more "housekeeping", and are slightly less efficient on insertions as the result |
  | If we know in advance that element to be searched is found near the end of the list(for example name 'Yogesh' in a telephone directory), even then singly linked list is traversed sequentially from beginning.	| In doubly linked list If we know in advance that element to be searched is found near the end of the list(for example name 'Yogesh' in a telephone directory), then the list can traversed from the end thereby saving time |
  | If we need to save memory in need to update node values frequently and searching is not required, we can use Singly Linked list.| If we need faster performance in searching and memory is not a limitation we use Doubly Linked List |
  | | The first and last nodes of a doubly linked list are immediately accessible (i.e., accessible without traversal, and usually called head and tail) and therefore allow traversal of the list from the beginning or end of the list, respectively: e.g., traversing the list from beginning to end, or from end to beginning, in a search of the list for a node with specific data value. Any node of a doubly linked list, once obtained, can be used to begin a new traversal of the list, in either direction (towards beginning or end), from the given node. |
  | **In a singly linked list, one must have the address of the pointer to that node, which is either the handle for the whole list (in case of the first node) or the link field in the previous node.** | **In a doubly linked list, one can insert or delete a node in a constant number of operations given only that node's address** |

  
  
## Technical Question

- **Write a function which takes a string as parameter. The function will return true if there are duplicated characters in the string, otherwise return false.**

```python
# good
def dupChar(s):
    myset = set()
    for c in s:
        if c in myset:  # do 'if..in..' with set only O(1), because set is implemented with hash. 
            return True
        myset.add(c)
    return False

# Time complexity
# Best case: O(1)
# Worest case: O(n)
# Average case: O(n)


# another good one
def dupChar(s):
    mydic = {}
    for c in s:
        if mydic.get(c) == None:
            mydic[c] = 1;
        else:
            return True
    return False


# Time complexity
# Best case: O(1)
# Worest case: O(n)
# Average case: O(n)

# ok
def dupChar(s):
    myset = set()
    for c in s:
        myset.add(c)
    return len(myset) == len(s)

# problem with this is that if input is lots repeated characters,
# it won't catch it right away, for example: "aaaaaaaaaaaaaaaaaaaaaaa"
# program will still need to iterate through entire string to get result.
# with best approach, it figures it out on the second character.

# Time complexity
# Best case: O(n)
# Worest case: O(n)
# Average case: O(n)


# bad one
def dupChar(s):
    length = len(s)
    for i in xrange(length):
        for j in xrange(i+1, length):
            if s[i] == s[j]:
                return True
    return False
    
# Time complexity
# Best case: O(1)
# Worest case: O(n^2)
# Average case: O(n^2)

```


- **Find all subsequences**

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

- **Find the first repeated word in a sentence, characters are delimiters between words: space, tab, comma(,), colon(:), semicolon(;), dash(-) and period(.)**

```python
# Sample input:
# He had had quite enough of this nonsense.

# Sample output:
# had

```

- **Longest subsequence of string X that is also a substring of Y(find length of longest subsequence)**

```python
# Sample input:
# abc
# aedace

# Sample output:
# 2

```

- **Anagram, minimum number of character need to be changed in X so that it's an anagram of string Y**

```python
# Sample input:
# aaabbb
# ab
# abc
# mnop
# xyyx

# Sample output:
# 3  (all 3 a's need to be changed to b, so it's 3)
# 1  (a needs to be changed to b, so it's 1)
# -1  (string X and Y have different length, so impossible, -1.)
# 2
# 0
```

- **Lowest conmmon multiple of n numbers**

```python
# Sample input:
# 10

# Sample output:
# lcm(10) = 2520

Explaination: 2520 is lowest common multiple of 1, 2, 3, 4, 5, 6, 7, 7, 9, 10


# Solution:

# To calculate lowest comoon multiple of two integers a and b
# we do a*b/gcd(a, b), so we can define a function called lcm(a, b)
# if you want to calculate more than two integers, you do lcm(lcm(a, b), c)


from faction import gcd
def lcm(a, b):
  return a*b/gcd(a, b) # In Python 3, use `//` to get integer instead of floating point

reduce(lcm, range(n))
```

- **remove node with value greater than x**

```java
static LinkedListNode removeNodes(LinkedListNode list, int x) {
        LinkedListNode cur;

        // Check if we have to update the head of the list. We do this
        //  when the first item in the list is greater than x.
        while(list != null && list.val > x) {
            list = list.next;
        }

        // If the list is empty, or we removed all items, then return
        //  the empty list
        if( list == null )
            return list;

        // Use cur to traverse the list
        cur = list;

        // At this point, cur.val is valid. So I need to check cur.next.val
        while(cur.next != null) {
            if (cur.next.val > x) {
                cur.next = cur.next.next; // skip the node
            } else {
                cur = cur.next; // don't skip, just update cur
            }
        }

        return list; // return the head of the list
    }

```

- write an iterator for a binary tree, in pre-order, in-order and post-order

```java
// updated needed
```


## Questions for the interviewer

- How large is your team?
- What does your dev cycle look like? Do you do waterfall/sprints/agile?
- Are rushes to deadlines common? Or is there flexibility?
- How are decisions made in your team?
- How many meetings do you have per week?
- Do you feel your work environment helps you concentrate?
- What are you working on?
- What do you like about it?
- What is the work life like?
