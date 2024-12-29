Stacks and Trees are foundational data structures in computer science. 
A brief overview of each:

---

### **Stacks**
- **Definition**: A stack is a linear data structure that follows the **Last In, First Out (LIFO)** principle. The last element added to the stack is the first one to be removed.

- **Key Operations**:
  1. **Push**: Add an element to the top of the stack.
  2. **Pop**: Remove the element from the top of the stack.
  3. **Peek/Top**: Retrieve the top element without removing it.
  4. **IsEmpty**: Check if the stack is empty.
  5. **Size**: Return the number of elements in the stack.

- **Applications**:
  - Undo functionality in text editors.
  - Expression evaluation and syntax parsing.
  - Backtracking algorithms (e.g., maze-solving, recursion).
  - Function call stack in programming.

- **Example in Python**:
  ```python
  class Stack:
      def __init__(self):
          self.items = []
      
      def push(self, item):
          self.items.append(item)
      
      def pop(self):
          return self.items.pop() if not self.is_empty() else None
      
      def peek(self):
          return self.items[-1] if not self.is_empty() else None
      
      def is_empty(self):
          return len(self.items) == 0
  ```

---

### **Trees**
- **Definition**: A tree is a hierarchical data structure consisting of nodes, with a single root node and zero or more child nodes. Each child node can have its own children, forming a tree-like structure.

- **Terminology**:
  1. **Root**: The topmost node in the tree.
  2. **Parent and Child**: Nodes directly connected by an edge, with the upper node being the parent and the lower one the child.
  3. **Leaf**: A node with no children.
  4. **Subtree**: A tree formed by a node and its descendants.
  5. **Height**: The longest path from a node to a leaf.
  6. **Depth**: The path length from the root to a node.

- **Types of Trees**:
  1. **Binary Tree**: Each node has at most two children.
  2. **Binary Search Tree (BST)**: A binary tree with the left child containing smaller values and the right child containing larger values.
  3. **Balanced Trees**: e.g., AVL Tree, Red-Black Tree (ensures height is balanced for efficient operations).
  4. **N-ary Tree**: A tree where nodes can have up to N children.
  5. **Heap**: A complete binary tree used for priority queues.

- **Applications**:
  - Representing hierarchical data (e.g., file systems, organizational charts).
  - Searching and sorting algorithms (e.g., BST, Heap).
  - Syntax trees in compilers.
  - Network routing.

- **Binary Tree Example in Python**:
  ```python
  class TreeNode:
      def __init__(self, value):
          self.value = value
          self.left = None
          self.right = None

  # Example: Creating a binary tree
  root = TreeNode(1)
  root.left = TreeNode(2)
  root.right = TreeNode(3)
  root.left.left = TreeNode(4)
  root.left.right = TreeNode(5)

  ```

---



### **Recursion Algorithm Overview**
Recursion is a technique where a function calls itself to solve smaller instances of the same problem. The key idea is to break the problem into smaller subproblems until reaching a base case, which terminates the recursion.

---

### **Structure of a Recursive Function**
A recursive function generally has:
1. **Base Case**: The condition under which recursion stops.
2. **Recursive Case**: The part where the function calls itself to work on smaller subproblems.

```python
def recursive_function(parameters):
    if base_case_condition:
        return base_case_result
    else:
        return recursive_function(smaller_problem)
```

---

### **Examples of Recursion**

#### **1. Factorial Calculation**
Factorial of \( n \) (\( n! \)) is the product of all positive integers less than or equal to \( n \).

- **Recursive Definition**:
  \( n! = n \times (n-1)! \), with \( 0! = 1 \).

- **Code**:
  ```python
  def factorial(n):
      if n == 0:  # Base case
          return 1
      return n * factorial(n - 1)  # Recursive case

  print(factorial(5))  # Output: 120
  ```

---

#### **2. Fibonacci Sequence**
The Fibonacci sequence is defined as \( F(n) = F(n-1) + F(n-2) \), with \( F(0) = 0 \) and \( F(1) = 1 \).

- **Code**:
  ```python
  def fibonacci(n):
      if n == 0:  # Base case
          return 0
      elif n == 1:  # Base case
          return 1
      return fibonacci(n - 1) + fibonacci(n - 2)  # Recursive case

  print(fibonacci(6))  # Output: 8
  ```

---

#### **3. Sum of Digits**
Find the sum of the digits of a number \( n \).

- **Recursive Definition**:
  \( \text{Sum}(n) = n \% 10 + \text{Sum}(n // 10) \), with \( n = 0 \).

- **Code**:
  ```python
  def sum_of_digits(n):
      if n == 0:  # Base case
          return 0
      return n % 10 + sum_of_digits(n // 10)  # Recursive case

  print(sum_of_digits(123))  # Output: 6
  ```

---

#### **4. Reverse a String**
Reverse a string using recursion.

- **Code**:
  ```python
  def reverse_string(s):
      if len(s) == 0:  # Base case
          return ""
      return s[-1] + reverse_string(s[:-1])  # Recursive case

  print(reverse_string("hello"))  # Output: "olleh"
  ```

---

#### **5. Binary Search (Recursively)**
Search for an element in a sorted list.

- **Code**:
  ```python
  def binary_search(arr, target, low, high):
      if low > high:  # Base case
          return -1
      mid = (low + high) // 2
      if arr[mid] == target:
          return mid
      elif arr[mid] > target:
          return binary_search(arr, target, low, mid - 1)  # Search left
      else:
          return binary_search(arr, target, mid + 1, high)  # Search right

  numbers = [1, 3, 5, 7, 9, 11]
  print(binary_search(numbers, 7, 0, len(numbers) - 1))  # Output: 3
  ```

---

### **Common Pitfalls**
1. **Missing Base Case**: Leads to infinite recursion.
2. **Inefficient Recursive Calls**: Avoid recomputing the same values (e.g., use **memoization** for Fibonacci).
3. **Stack Overflow**: Too deep recursion can exceed the call stack limit.

---


### **Recursion Algorithm Overview**
Recursion is a technique where a function calls itself to solve smaller instances of the same problem. The key idea is to break the problem into smaller subproblems until reaching a base case, which terminates the recursion.

---

### **Structure of a Recursive Function**
A recursive function generally has:
1. **Base Case**: The condition under which recursion stops.
2. **Recursive Case**: The part where the function calls itself to work on smaller subproblems.

```python
def recursive_function(parameters):
    if base_case_condition:
        return base_case_result
    else:
        return recursive_function(smaller_problem)
```

---

### **Examples of Recursion**

#### **1. Factorial Calculation**
Factorial of \( n \) (\( n! \)) is the product of all positive integers less than or equal to \( n \).

- **Recursive Definition**:
  \( n! = n \times (n-1)! \), with \( 0! = 1 \).

- **Code**:
  ```python
  def factorial(n):
      if n == 0:  # Base case
          return 1
      return n * factorial(n - 1)  # Recursive case

  print(factorial(5))  # Output: 120
  ```

---

#### **2. Fibonacci Sequence**
The Fibonacci sequence is defined as \( F(n) = F(n-1) + F(n-2) \), with \( F(0) = 0 \) and \( F(1) = 1 \).

- **Code**:
  ```python
  def fibonacci(n):
      if n == 0:  # Base case
          return 0
      elif n == 1:  # Base case
          return 1
      return fibonacci(n - 1) + fibonacci(n - 2)  # Recursive case

  print(fibonacci(6))  # Output: 8
  ```

---

#### **3. Sum of Digits**
Find the sum of the digits of a number \( n \).

- **Recursive Definition**:
  \( \text{Sum}(n) = n \% 10 + \text{Sum}(n // 10) \), with \( n = 0 \).

- **Code**:
  ```python
  def sum_of_digits(n):
      if n == 0:  # Base case
          return 0
      return n % 10 + sum_of_digits(n // 10)  # Recursive case

  print(sum_of_digits(123))  # Output: 6
  ```

---

#### **4. Reverse a String**
Reverse a string using recursion.

- **Code**:
  ```python
  def reverse_string(s):
      if len(s) == 0:  # Base case
          return ""
      return s[-1] + reverse_string(s[:-1])  # Recursive case

  print(reverse_string("hello"))  # Output: "olleh"
  ```

---

#### **5. Binary Search (Recursively)**
Search for an element in a sorted list.

- **Code**:
  ```python
  def binary_search(arr, target, low, high):
      if low > high:  # Base case
          return -1
      mid = (low + high) // 2
      if arr[mid] == target:
          return mid
      elif arr[mid] > target:
          return binary_search(arr, target, low, mid - 1)  # Search left
      else:
          return binary_search(arr, target, mid + 1, high)  # Search right

  numbers = [1, 3, 5, 7, 9, 11]
  print(binary_search(numbers, 7, 0, len(numbers) - 1))  # Output: 3
  ```

---

### **Common Pitfalls**
1. **Missing Base Case**: Leads to infinite recursion.
2. **Inefficient Recursive Calls**: Avoid recomputing the same values (e.g., use **memoization** for Fibonacci).
3. **Stack Overflow**: Too deep recursion can exceed the call stack limit.

---


### **Tower of Hanoi**

The Tower of Hanoi is a classic problem in recursion that involves moving a set of disks from one peg to another while following specific rules.

---

### **Rules**:
1. Only one disk can be moved at a time.
2. A disk can only be placed on top of a larger disk (or on an empty peg).
3. All disks start on one peg and must end up on another peg, using a third peg as an auxiliary.

---

### **Problem Setup**
- **Input**: \( n \) disks, three pegs named Source (A), Destination (C), and Auxiliary (B).
- **Goal**: Move all disks from \( A \) to \( C \).

#### **Recursive Approach**:
1. Move \( n-1 \) disks from \( A \) to \( B \), using \( C \) as an auxiliary peg.
2. Move the largest disk directly from \( A \) to \( C \).
3. Move \( n-1 \) disks from \( B \) to \( C \), using \( A \) as an auxiliary peg.

---

### **Base Case**:
If \( n = 1 \), move the single disk directly from \( A \) to \( C \).

---

### **Python Implementation**:
```python
def tower_of_hanoi(n, source, destination, auxiliary):
    if n == 1:  # Base case: Only one disk
        print(f"Move disk 1 from {source} to {destination}")
        return
    # Recursive case:
    tower_of_hanoi(n - 1, source, auxiliary, destination)  # Step 1
    print(f"Move disk {n} from {source} to {destination}")  # Step 2
    tower_of_hanoi(n - 1, auxiliary, destination, source)  # Step 3

# Example: Solve Tower of Hanoi for 3 disks
tower_of_hanoi(3, 'A', 'C', 'B')
```

---

### **Steps for 3 Disks**:
#### **Initial State**:
- Peg A: [3, 2, 1] (bottom to top)
- Peg B: []  
- Peg C: []

#### **Steps**:
1. Move disk 1 from A to C.
2. Move disk 2 from A to B.
3. Move disk 1 from C to B.
4. Move disk 3 from A to C.
5. Move disk 1 from B to A.
6. Move disk 2 from B to C.
7. Move disk 1 from A to C.

---

### **Tower of Hanoi for 3 Disks: Textual Representation**

Below is the step-by-step textual representation of the Tower of Hanoi process for 3 disks.

---

#### **Initial State**:
```
Peg A: [3, 2, 1]  (Source)
Peg B: []         (Auxiliary)
Peg C: []         (Destination)
```

---

#### **Steps**:

1. **Move disk 1 from A to C**:
   ```
   Peg A: [3, 2]
   Peg B: []
   Peg C: [1]
   ```

2. **Move disk 2 from A to B**:
   ```
   Peg A: [3]
   Peg B: [2]
   Peg C: [1]
   ```

3. **Move disk 1 from C to B**:
   ```
   Peg A: [3]
   Peg B: [2, 1]
   Peg C: []
   ```

4. **Move disk 3 from A to C**:
   ```
   Peg A: []
   Peg B: [2, 1]
   Peg C: [3]
   ```

5. **Move disk 1 from B to A**:
   ```
   Peg A: [1]
   Peg B: [2]
   Peg C: [3]
   ```

6. **Move disk 2 from B to C**:
   ```
   Peg A: [1]
   Peg B: []
   Peg C: [3, 2]
   ```

7. **Move disk 1 from A to C**:
   ```
   Peg A: []
   Peg B: []
   Peg C: [3, 2, 1]
   ```

---

#### **Final State**:
```
Peg A: []         (Source)
Peg B: []         (Auxiliary)
Peg C: [3, 2, 1]  (Destination)
```

---



```markdown
### Tower of Hanoi for 3 Disks: Textual Representation

#### Initial State:
```
Peg A: [3, 2, 1]  (Source)
Peg B: []         (Auxiliary)
Peg C: []         (Destination)
```

---

#### Steps:

1. **Move disk 1 from A to C**:
   ```
   Peg A: [3, 2]
   Peg B: []
   Peg C: [1]
   ```

2. **Move disk 2 from A to B**:
   ```
   Peg A: [3]
   Peg B: [2]
   Peg C: [1]
   ```

3. **Move disk 1 from C to B**:
   ```
   Peg A: [3]
   Peg B: [2, 1]
   Peg C: []
   ```

4. **Move disk 3 from A to C**:
   ```
   Peg A: []
   Peg B: [2, 1]
   Peg C: [3]
   ```

5. **Move disk 1 from B to A**:
   ```
   Peg A: [1]
   Peg B: [2]
   Peg C: [3]
   ```

6. **Move disk 2 from B to C**:
   ```
   Peg A: [1]
   Peg B: []
   Peg C: [3, 2]
   ```

7. **Move disk 1 from A to C**:
   ```
   Peg A: []
   Peg B: []
   Peg C: [3, 2, 1]
   ```

---

#### Final State:
```
Peg A: []         (Source)
Peg B: []         (Auxiliary)
Peg C: [3, 2, 1]  (Destination)
```
```
