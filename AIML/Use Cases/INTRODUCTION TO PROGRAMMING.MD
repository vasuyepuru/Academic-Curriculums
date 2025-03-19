
1.Variables and Data Types

Code Example:
python
```
# Storing and printing user details
name = "John Doe"          # String
age = 30                   # Integer
height = 5.8               # Float
is_active = True           # Boolean

print(f"Name: {name}, Age: {age}, Height: {height}, Active: {is_active}")
```
Real-World Use:
•	Application in Projects: Variables and data types form the foundation of any program. For example, in a user management system, you could store user details like names (strings), ages (integers), or activity status (booleans) in a database.

2. Control Structures

Code Example:
python
```
# Determine user's access level based on age
age = int(input("Enter your age: "))

if age < 18:
    print("Access Denied: You must be at least 18 years old.")
else:
    print("Access Granted: Welcome!")
```
Real-World Use:
•	Application in Projects: Decision-making is crucial in applications like access control systems. For example, online platforms can restrict content based on user age (e.g., parental controls).

3. Loops
Code Example:
python
```
# Display numbers from 1 to 10
for i in range(1, 11):
    print(i)

# Print the sum of numbers until user enters 0
total = 0
while True:
    num = int(input("Enter a number (0 to stop): "))
    if num == 0:
        break
    total += num
print(f"Total Sum: {total}")
```
Real-World Use:
•	Application in Projects: Loops are indispensable in report generation or automating repetitive tasks, such as processing user data or transactions.

4. Functions

Code Example:
python
```
# Calculate the square of a number
def square(number):
    return number * number

num = int(input("Enter a number: "))
print(f"Square of {num}: {square(num)}")
```
Real-World Use:
•	Application in Projects: Functions modularize code, enabling reuse across various parts of a project. For example, in financial software, you might use functions to calculate taxes or discounts.

5. Arrays (Using Lists)

Code Example:
python
```
# Find the average of a list of numbers
numbers = [10, 20, 30, 40, 50]
average = sum(numbers) / len(numbers)
print(f"Average: {average}")

# Add a new number to the list
numbers.append(60)
print("Updated List:", numbers)
```
Real-World Use:
•	Application in Projects: Arrays (lists in Python) are essential for storing and manipulating data in inventory systems, like keeping track of product prices or stock levels.

6. Basic Algorithms

Linear Search:
python
```
# Search for an element in a list
def linear_search(array, target):
    for i, value in enumerate(array):
        if value == target:
            return f"Found at index {i}"
    return "Not found"

array = [10, 20, 30, 40, 50]
target = int(input("Enter the number to search for: "))
print(linear_search(array, target))
```
•	Application in Projects: This can be used in small-scale database searches, such as finding a specific product ID in an inventory.
Sorting (Bubble Sort):
python
```
# Bubble Sort Algorithm
def bubble_sort(array):
    n = len(array)
    for i in range(n):
        for j in range(0, n - i - 1):
            if array[j] > array[j + 1]:
                array[j], array[j + 1] = array[j + 1], array[j]
    return array

numbers = [64, 34, 25, 12, 22, 11, 90]
print("Sorted Array:", bubble_sort(numbers))
```
•	Application in Projects: Sorting algorithms can help in real-time ranking systems, such as sorting products by price or relevance in e-commerce platforms.

