# Exp.No:31  
## IMPLEMENTATION OF STACK

---

### AIM  
To write a Python program to implement a stack using a list and its built-in methods (`append()`, `pop()`).

---

### ALGORITHM

1. **Start the program.**
2. **Define a class `st`** with the following methods:
   - `push(self, num)`: Adds the number `num` to the stack.
   - `pop(self)`: Removes and returns the top element from the stack.
3. **Create a stack object `s`** using the class `st`.
4. **Input the stack size**: Take an integer input `size` to define the size of the stack.
5. **Loop through numbers from 1 to size**: Add only the odd numbers to the stack using the `push()` method.
6. **Display the elements** in the stack after the loop completes.
7. **Call `pop()`** to remove the top element from the stack and display the popped element.
8. **Display the stack again** to show the remaining elements.
9. **End the program.**

---
### PROGRAM
# Define the stack class
class st:
    def __init__(self):
        self.stack = []

    # Method to push an element to stack
    def push(self, num):
        self.stack.append(num)

    # Method to pop an element from stack
    def pop(self):
        if not self.stack:
            return "Stack is empty"
        return self.stack.pop()

    # Method to display the stack
    def display(self):
        return self.stack

# Create a stack object
s = st()

# Input the size
size = int(input("Enter the size of stack: "))

# Pushing only odd numbers into the stack
for i in range(1, size + 1):
    if i % 2 != 0:
        s.push(i)

# Display the stack after insertion
print("Stack elements after pushing odd numbers:", s.display())

# Pop the top element
popped_element = s.pop()
print("Popped element:", popped_element)

# Display the stack after popping
print("Stack elements after popping:", s.display())

### OUTPUT
![image](https://github.com/user-attachments/assets/42023667-127f-4b90-968a-76d92a326ba5)

### RESULT
The program successfully implements a stack using list methods (append() and pop()) and performs stack operations based on odd numbers.




