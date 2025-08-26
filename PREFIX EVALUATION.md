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
# 212223060073
# Gowri Sankari R
OPERATORS=set(['*','-','+','%','/','**']) 
def evaluate(expression):
	stack = []
	for c in expression[::-1]:
	    if c not in OPERATORS:
	        stack.append(int(c))
	    else:
	        a=stack.pop()
	        b=stack.pop()
	        if c=='+':
	            stack.append(a+b)
	        elif c=='-':
	            stack.append(a-b)
	        elif c=='*':
	            stack.append(a*b)
	        elif c=='/':
	            stack.append(a/b)
	return stack.pop()
test_expression = input()
print("Prefix Expression :",test_expression)
print("Evaluation result :",evaluate(test_expression))
```


### OUTPUT
<img width="1173" height="208" alt="13D" src="https://github.com/user-attachments/assets/bec35e70-01ac-4539-8c79-31bf5dc9c483" />

### RESULT
The program evaluates the given prefix expression using stack operations and displays the final result.
