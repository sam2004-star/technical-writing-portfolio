Python lists are another one of the most basic and useful data structures in the Python programming language, which are ordered sequences of elements. Beyond this simplicity is a powerful system that makes them easy to store collections of items, but they are also easy to provide for dynamic storage, iteration, slicing, and integrating into the larger Python system.

We explore lists in this tutorial, learning more about this type of data than the name implies, how to use lists effectively and how to use lists in real scenarios for programming.

1. Learn about Python Lists and their use as dynamic array.

The Python list is dynamically implemented as an array. This means:

Elements of data structure are stored in adjacent memory locations.Adjacent memory locations (Data structures: Items stored in adjacent memory locations.)
The list can be added to or shortened as per the content.
Memory reallocation is taken care of by the dynamic type system of Python.

Example:

scores = [78, 85, 90, 66, 92]

C and other lower level languages are array based and the size of the array is fixed, but in Python, the list expands or shrinks as elements are added or removed.

2. Creating Lists

List items may be of various types of…:

user_profile = [‘Sammy’, 21, ‘Nairobi’, True]

This flexibility is great with lists, and can be confusing to implement in larger programs.

3. Indexing and working with indexes in memory.Develop and use indexes in memory.

The numbers stored in the list are stored at index 0...n-1.

shopping_cart = ['milk', 'bread', 'eggs']

print(shopping_cart[0])  # milk
print(shopping_cart[2])  # eggs
Negative Indexing

Python: supports backwards indexing:

print(shopping_cart[-1])  # eggs
print(shopping_cart[-2])  # bread

This can come in handy when you don't know the number of items in the list.

Slice a list (Important Concept)

One of the ways to obtain a subset of a list is slicing.

marks = [45, 67, 89, 72, 91, 56, 80]

print(marks[1:4])

Output:

[67, 89, 72]
Slicing Syntax
list[start:stop:step]

Examples:

print(marks[:3])     # First 3 elements
print(list(reversed(marks))   # Reverse the list through iteration
print(marks[::-1])   # Reverse list
5. Modifying Lists

Lists have the ability to be modified after they have been created (they are mutable).

tasks = ["study", "code", "exercise"]
tasks[1] = "practice coding"

Now:

A continuous rapid-fire battery of questions.A stream of quick-fire questions.

The mutability of Python is one aspect of its great strengths.

6. Common List Methods
append()

Adds an item to the end:

tasks.append("read documentation")
insert()

Appends an element to a certain index:

tasks.insert(1, "attend lecture")
remove()

Uses a value to delete the value:

tasks.remove("study")
pop()

Removes an element from a list, specified at an index. Removes the last element (default).

tasks.pop()
tasks.pop(0)
7. List Looping Efficiently

Loops are commonly used to work with lists.

Basic loop:
tasks = ["study", "code", "sleep"]

for task in tasks:
    print(f"Task: {task}")
With index:
For i in range of length of tasks:
    print(i, tasks[i])

A more Pythonic way (preferred):

for task, index in enumerate(tasks):
    print(index, task)
List comprehensions (Advanced Feature)

List comprehensions are a short method of creating a list.

Example:

numbers = [1, 2, 3, 4, 5, 6]
squares is the square of each number in numbers.squares will be numbers squared.

Equivalent to:

squares = []
for n in numbers:
    squares.append(n * n)
With condition:
numbers = list(range(20))
even_numbers = [n for n in numbers if n % 2 == 0]

Extremely popular in the world of professional Python programming.

9. Performance Considerations

Lists are an example of a dynamic array:

Appending is generally very fast (O(1) amortized)
- Inserting at the beginning is slower (O(n))
Loop through a list - O(n)

In some cases for large-scale applications, developers use:

collections.deque for queues
10. Real-World Use Cases

Python lists are employed to:

Collecting user information from users.

The list users contains the email addresses of the users that will be able to access the system.
Managing API responses
Processing files line-by-line
Machine learning preprocessing
Conclusion

Almost every Python program has lists and they are one of the most fundamental elements of Python. Knowing how to use them to be the most effective, and understanding how to take advantage of their more advanced features (slicing, list comprehensions) is a useful trick for every programmer who wants to make the best of python.

Efficient, scalable, and well-written Python programs can be achieved with the knowledge of using lists.
