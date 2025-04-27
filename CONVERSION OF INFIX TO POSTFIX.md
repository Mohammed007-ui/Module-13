# Exp.No:32  
## CONVERSION OF INFIX TO POSTFIX

---

### AIM  
To write a Python program to convert a given Infix expression to Postfix expression by following the precedence and associative rules. The input expression contains only Division, Subtraction, and Bitwise AND operators. A dictionary is used to set the priority for operators, and a set is used to hold the operators used in the given expression.

---

### ALGORITHM

1. **Start the program.**
2. **Initialize an empty stack** and an empty output string.
3. **Iterate through each character** in the infix expression:
   - If the character is **not an operator**, append it directly to the output string.
   - If the character is an **open parenthesis '('**, push it onto the stack.
   - If the character is a **close parenthesis ')'**, pop from the stack and append to the output until encountering a left parenthesis '('.
   - If the character is an **operator**, handle it based on precedence:
     - While there’s an operator at the top of the stack with higher or equal precedence, pop the stack and append those operators to the output.
     - Push the current operator onto the stack.
4. **Use a priority dictionary** to define operator precedence, ensuring higher precedence operators are placed before lower precedence ones.
5. Once the expression is fully processed, continue popping any remaining operators from the stack and append them to the output.
6. **Return the final postfix expression.**
7. **Print the result.**
8. **End the program.**

---

### PROGRAM

```
# Function to convert infix to postfix
def infix_to_postfix(expression):
    # Define precedence of operators
    precedence = {'/': 3, '-': 2, '&': 1}
    operators = {'/', '-', '&'}
    stack = []
    output = []

    for char in expression:
        if char not in operators and char not in {'(', ')'}:
            output.append(char)
        elif char == '(':
            stack.append(char)
        elif char == ')':
            while stack and stack[-1] != '(':
                output.append(stack.pop())
            stack.pop()  # Remove '(' from stack
        else:
            while (stack and stack[-1] != '(' and
                   precedence.get(char, 0) <= precedence.get(stack[-1], 0)):
                output.append(stack.pop())
            stack.append(char)

    # Pop all remaining operators in stack
    while stack:
        output.append(stack.pop())

    return ''.join(output)

# Example usage
infix_expr = "A/B-(C&D)"
postfix_expr = infix_to_postfix(infix_expr)
print("Infix Expression:", infix_expr)
print("Postfix Expression:", postfix_expr)


```

### OUTPUT
![image](https://github.com/user-attachments/assets/3e1c3758-40c3-47bb-9c03-ac469f554383)


### RESULT
The program successfully converts the given Infix expression to a Postfix expression following the precedence and associative rules for Division (/), Subtraction (-), and Bitwise AND (&) operators.


