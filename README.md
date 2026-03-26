## MODULE - 10
# EXP 46 Queue-Queue Values in Descending Order Using Python 

This Python program simulates a queue using a list, removes the first two elements (FIFO order), and displays the remaining values in descending order.

##  Aim

To write a Python program to:
- Accept user inputs into a list (queue)
- Remove the first two elements (simulating dequeue)
- Display the remaining values in **descending order**

##  Algorithm

1. Create an empty list `q`.
2. Read an integer `n` to determine how many elements will be added.
3. Loop `n` times:
   - Read an input value.
   - Append it to the list `q`.
4. Remove the first element using `pop(0)`.
5. Remove the second element using `pop(0)` again.
6. Sort the list in descending order.
7. Print the updated list.

##  Program: 
```
q = []
n = int(input())
for _ in range(n):
    val = int(input())
    q.append(val)

q.pop(0)  
q.pop(0)  

q.sort(reverse=True)
print(*q)
```
### Output:
![image](https://github.com/user-attachments/assets/cf686b24-d64e-4bcb-a664-7315af08d0fb)

## Result:
Thus, the program is verified successfully.

---

# EXP 47: Queue-Remove Two String Values from the Rear End in Python 

This Python program demonstrates how to manage a list of strings and remove the last two elements (i.e., from the rear of the list).

##  Aim

To write a Python program to:
- Accept `n` string values from the user
- Remove the last two values (rear end of the list)
- Display the updated list

##  Algorithm

1. Create an empty list `q`.
2. Read an integer `n` from the user (number of strings).
3. Loop `n` times:
   - Read a string input.
   - Append it to the list `q`.
4. Remove the last element using `pop()`.
5. Remove the next last element using `pop()` again.
6. Display the updated list.

##  Program:
```
q = []
n = int(input())
for _ in range(n):
    s = input()
    q.append(s)

q.pop()  
q.pop() 

print(q)
```
## Output:
![image](https://github.com/user-attachments/assets/28a4bb3d-cb2f-4333-bd0a-a23f70ce72c9)

## Result:
Thus, the program is verified successfully.

---

# EXP 48: Stack Implementation Using `LifoQueue` (Max Size 7) 

This Python program demonstrates a stack implemented using the `LifoQueue` class from the `queue` module. It allows up to 7 elements, checks if the stack is full, and then prints the elements in reverse (LIFO) order.

##  Aim

To create a Python program that:
- Implements a stack using `LifoQueue` with a maximum size of 7
- Adds user-inputted values to the stack
- Checks whether the stack is full
- Prints the stack elements in reverse order (LIFO)

##  Algorithm

1. Import the `LifoQueue` class from the `queue` module.
2. Create a stack with a maximum size of 7.
3. Read the number of elements (`n`) to be added to the stack.
4. Loop `n` times:
   - Read a value from the user.
   - Use `put()` to push it onto the stack if it's not full.
5. Use `full()` to check if the stack is full and print the result.
6. Use `get()` repeatedly to pop and print elements in reverse order.

## Program
```
from queue import LifoQueue
stack=LifoQueue(maxsize=7)

n=int(input())
for i in range(n):
    stack.put(input())
print(stack.full())
for i in range(n):
    print(stack.get())
```
##  Sample Input and Output
![image](https://github.com/user-attachments/assets/8d592eb5-56ac-401e-9fda-c44c7aa2cea6)

## Result:
Thus, the program is verified successfully.

---

# EXP 49: Stack-Stack Reversal Program 

This Python program demonstrates how to reverse the values in a stack using basic stack operations like push and pop.

##  Aim

To write a Python program that reverses the values in a stack using standard stack operations.

## Algorithm

1. Create an empty stack.
2. Read an integer `n` from the user (number of elements to push).
3. Loop `n` times:
   - Read an integer from the user.
   - Push it onto the stack.
4. Create an empty list called `reverse`.
5. While the stack is not empty:
   - Pop the top element.
   - Append it to `reverse`.
6. Print the reversed list.


## Program:
```
stack = []
n = int(input())
for _ in range(n):
    val = int(input())
    stack.append(val)

reverse = []
while stack:
    reverse.append(stack.pop())

print(reverse)
```
##  Sample Input and Output
![image](https://github.com/user-attachments/assets/da841453-4d17-45b6-b152-9c9ccc726439)

## Result
Thus, the program is verified successfully.

---

# EXP 50: Types of Queue-Circular Queue in Python

This project demonstrates the implementation of a **Circular Queue** in Python. The queue accepts 3 user values, performs enqueue and dequeue operations, and displays the removed values.



##  Aim

To develop a Python program that implements a Circular Queue:
- Accepts 3 values from the user
- Removes the 3 values from the queue
- Displays the removed values


##  Algorithm

1. **Initialize** a circular queue of fixed size (e.g., 5).
2. **Define the following functions**:
   - `enqueue()`: Inserts an element into the queue.
   - `dequeue()`: Removes an element from the queue.
   - `display()`: Shows the queue contents.
3. Accept 3 values from the user using the `enqueue()` method.
4. Remove 3 values using the `dequeue()` method.
5. Print the removed values.


##  Program:
```
class CircularQueue:
    def __init__(self, size=5):
        self.size = size
        self.queue = [None] * size
        self.front = -1
        self.rear = -1
    
    def enqueue(self, value):
        if (self.rear + 1) % self.size == self.front:
            return False  
        
        if self.front == -1:  
            self.front = 0
        
        self.rear = (self.rear + 1) % self.size
        self.queue[self.rear] = value
        return True
    
    def dequeue(self):
        if self.front == -1:
            return None
        
        value = self.queue[self.front]
        self.queue[self.front] = None
        
        if self.front == self.rear:
            self.front = -1
            self.rear = -1
        else:
            self.front = (self.front + 1) % self.size
        
        return value
    
    def display(self):
        if self.front == -1:
            return []
        elements = []
        i = self.front
        while True:
            elements.append(self.queue[i])
            if i == self.rear:
                break
            i = (i + 1) % self.size
        return elements

cq = CircularQueue()

for _ in range(3):
    val = int(input())
    cq.enqueue(val)

removed = []
for _ in range(3):
    removed.append(cq.dequeue())

print(*removed)
```
## Output:
![image](https://github.com/user-attachments/assets/0f087c24-97de-4ba3-bbcb-765204d73be3)

## Result:
Thus, the program is verified successfully.
