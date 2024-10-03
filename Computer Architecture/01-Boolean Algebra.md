Computer Circuits are implementations of **Boole's Laws of Thought**
### Boolean Algebra 
- A mathematical system for the manipulation of variables that can have only two values
- In formal logic these values are "true" and "false".
- In digital systems, these values are "on" and "off", 1 and 0, or "high" and "low".
---
### Boolean expressions
- Built by using Boolean operators to combine Boolean variables
	- Fundamental operators: AND, OR and NOT
---
### NOT 
- unary operator
- e.g., `NOT A`
- NOT is "negation", can be written with any symbol for negation
	- Can be written with a minus sign `-`
	- Can also be written with an overbar, or with the prime mark, the elbow, or the exclamation point.
	- Parenthesis can be used to avoid confusion
		- `(A)(-B) = A(!B) = A AND NOT B`
		- `!AB = (!A)B = NOT A AND B`
```
` <- Prime Mark
```
---
### AND & OR 
- Binary operators
- e.g.: `A AND B & A OR B`
- AND is "multiply" in Boolean algebra, can be written using any symbol for "times".
	- Called the Boolean product
	- Commonly written as concatenation, i.e., `AB = A AND B`
	- Can also be written as `*` or `x`, raised dot, or an upside down V
- OR is "add" in Boolean algebra, can be written using any symbol for "plus". 
	- Called the Boolean sum
	- Commonly written as `+`
	- Can also be written as `V`
---
### Order of Operations

``Parenthesis -> NOT -> AND -> OR``

- Parenthesis has top
- NOT next
- AND next
- OR has lowest
- AND binds tighter than OR
	- Way of saying that AND has priority over OR.
	- This is parallel to * having priority over +
- Better to use parenthesis with complex expressions
	- I.e., `A AND B OR C = (A AND B) OR C`
	- `AB + C` is another way to write the expression