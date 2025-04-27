# Exp.No:35  
## TOWER OF HANOI

---

### AIM  
To write a Python program to implement **Tower of Hanoi** and display all the moves of the disks using a recursive function.  
Consider the names of the tower pegs as A, B, C. Get the number of disks value from the user.

---

### ALGORITHM  

1. **Start the program.**
2. **Input** the number of disks `n`.
3. **Print** the number of disks.
4. Define a **recursive function** `TowerOfHanoi(n, source, destination, auxiliary)`:
   - If `n == 1`:
     - Print: "Move disk from source to destination".
   - Else:
     - Call `TowerOfHanoi(n - 1, source, auxiliary, destination)`  
       → Move `n-1` disks from source to auxiliary using destination as helper.
     - Print: "Move disk from source to destination"  
       → Move the largest disk to the destination.
     - Call `TowerOfHanoi(n - 1, auxiliary, destination, source)`  
       → Move `n-1` disks from auxiliary to destination using source as helper.
5. Call `TowerOfHanoi(n, 'A', 'C', 'B')` to start the process.
6. **End the program.**

---

### PROGRAM  

```
# Recursive function to solve Tower of Hanoi
def TowerOfHanoi(n, source, destination, auxiliary):
    if n == 1:
        print(f"Move disk 1 from {source} to {destination}")
        return
    TowerOfHanoi(n - 1, source, auxiliary, destination)
    print(f"Move disk {n} from {source} to {destination}")
    TowerOfHanoi(n - 1, auxiliary, destination, source)

# Main program
n = int(input("Enter the number of disks: "))
print(f"\nNumber of disks = {n}\n")
print("The sequence of moves involved are:\n")
TowerOfHanoi(n, 'A', 'C', 'B')

```

### OUTPUT
```
![image](https://github.com/user-attachments/assets/41bf71b6-8f86-473d-b05f-555384e86872)
```

### RESULT
```
Thus, the program for solving the Tower of Hanoi problem using recursion was successfully written and executed, displaying all moves correctly.
```

