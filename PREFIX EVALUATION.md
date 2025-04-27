# Exp.No:34  
## PREFIX EVALUATION

---

### AIM  
To write a Python program to evaluate a user-given Prefix expression using a stack. The expression must contain operators such as Multiplication, Addition, and Subtraction.

---

### ALGORITHM

1. **Start the program.**
2. Define a set of valid operators: `*, -, +, %, /, **`.
3. Initialize an empty stack.
4. Traverse the prefix expression from **right to left**:
   - If the character is a **digit**, convert it to an integer and push it onto the stack.
   - If the character is an **operator**, pop two elements from the stack.
     - Apply the operator on the two popped operands.
     - Push the result back onto the stack.
   - If an invalid character is encountered, raise an error.
5. After traversal, the stack should contain only **one element**.
6. Return the **single element** as the evaluation result.
7. **End the program.**

---

### PROGRAM

```
# Define the set of valid operators
OPERATORS = {'+', '-', '*', '/', '%', '**'}

# Function to evaluate prefix expression
def evaluate_prefix(exp):
    stack = []
    # Split the expression and traverse from right to left
    for item in reversed(exp.split()):
        if item not in OPERATORS:
            stack.append(int(item))
        else:
            a = stack.pop()
            b = stack.pop()
            if item == '+':
                result = a + b
            elif item == '-':
                result = a - b
            elif item == '*':
                result = a * b
            elif item == '/':
                result = a / b
            elif item == '%':
                result = a % b
            elif item == '**':
                result = a ** b
            stack.append(result)
    return stack[0]

# Main program
prefix_expr = input("Enter a prefix expression (with spaces between characters): ")
print("Prefix Expression:", prefix_expr)
result = evaluate_prefix(prefix_expr)
print("Evaluation Result:", result)


```


### OUTPUT

![image](https://github.com/user-attachments/assets/1a079b2b-85f5-4f69-9a00-a9cc51ff96ef)


### RESULT
Thus, the program to evaluate a prefix expression using the stack concept was successfully written and executed.

