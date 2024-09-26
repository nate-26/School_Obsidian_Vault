**Identity Table:**

| Identity Name         | AND Form                   | OR Form                     |
| --------------------- | -------------------------- | --------------------------- |
| Identity Law          | $1x = x$                   | $0 + x = x$                 |
| Null law              | $0x = 0$                   | $1 + x = 1$                 |
| Idempotent Law        | $xx = x$                   | $x + x = x$                 |
| Inverse Law           | $x!x = 0$                  | $x + !x = 1$                |
| Commutative Law       | $xy = yx$                  | $x + y = y + x$             |
| Associative Law       | $(xy)z = x(yz)$            | $(x + y) + z = x + (y + z)$ |
| Distributive Law      | $x + yz = (x + y) (x + z)$ | $x(y + z) = xy + xz$        |
| Absorption Law        | $x(x + y) = x$             | $x + xy = x$                |
| DeMorgan's Law        | $(xy)' = x' + y'$          | $(x + y)' = x'y'$           |
| Double Complement Law | $(x')' = x$                | <-- Same as AND             |
- The simpler the Boolean function is made, the smaller the circuit that will result
	- Simpler circuits are cheaper to build, consume less power, and run faster than complex circuits.
- However, there is other criteria involved:
	- How the circuit involved fits with other circuits in the machine, e.g., can common activities be factored out.
	- General criteria such as providing redundancy, a safety margin of error, and others,
	- Consistency with other machines in the same line.
- Generally you want to reduce our Boolean functions to a simpler form.
	- **You can use Boolean identities (equations) for this**. 
	- *In real world situations, this would be accomplished with the help of a hardware compiler that would also enforce standards.*
- Most Boolean identities have an AND (product) form as well as an OR (sum) form.
- The first group contains identities involving only one variable. They enable you to reduce the number of terms in an expression, and sometimes also the number of variables.
- The AND form and the OR form are *duals*. 
- The dual of a law is created as follows:
	- Switch AND and OR
	- Switch 0 and 1
	- Check out the laws on the previous and following slides to make sure you can calculate the duals.
- If a Boolean statement is valid (its truth table contains all TRUEs), its dual is valid also
	- *Different from ordinary arithmetic, characteristic of Boolean algebra.*
- Laws are good for variables and expressions.
	- Laws are expressed in terms of variables like x, y and z
	- **You can substitute any Boolean expression in place of a variable.**
	- Example:
		- The AND form of the identity law is $1x = x$
		- That means that $1(x + y) = x + y, 1(x') = x'$, etc.
---
**The Identity Law** 
- States that performing an operation with its identity does not affect the result.
	- That is the definition of identity
- AND form: $1x = x$
	- The identity for AND is 1.
	- Just as the identity for * in arithmetic is 1.
- OR form: $0 + x = x$ 
	- The identity for OR is 0.
	- Just as the identity for + in arithmetic is 0.
- The identity law is the same as in arithmetic.
- Identity law, AND form: $1x + x$
	- Explanation: 
		- Since 1 = true, this means that: if x is true, then the value of "x and a true statement" is the same as the value of x.
		- In other words, if x is true, then "x and a true statement" is true; if x is false, then "x and a statement" is false.
		- This works because both inputs must be true to make the result of "and" true.
- Identity law, OR form: $0 + x = x$
	- Explanation: 
		- Since 0 = false, this means that: if x is true, then the value of "x or a false statement" is the same as the value of x.
		- In other words:
			- If x is true, then "x or a false statement" is true.
			- If x is false, then "x or a false statement" is false.
		- This works because only one statement needs to be true to make the result of "or" true.
---
**The Null Law** 
- States that use of opposite operations' identity "nullifies" a value.
- AND form: $0x = 0$
	- Note that x no longer appears on the right hand side.
- OR form: $1 + x = 1$
	- Again, the x no longer appears on the right hand side.
- The AND form is the same as in arithmetic. The OR form is different.
- Null law, AND form: $0x = 0$
	- Explanation:
		- Since 0 = false, this means that if there is one false statement in a conjunction (series of ANDs), the result is false.
- Null law, OR form: $1 + x = 1$
	- Explanation:
		- Since 1 = true, this means that: if there is one true statement is a disjunction (series of ORs), the result is true.
---
**The Idempotent Law** 
- States that if the two input values are the same, the output is the same as the input
	- The term comes from the Latin words "idem" meaning same, and "potent" meaning value.
	- Note that the word is "idem" and not "item"
	- Note that the idempotent law does not have a carryover in arithmetic.
- AND form: $xx = x$
- OR form: $x + x = x$
- Idempotent law, AND form: $xx = x$
	- Explanation:
		- If you "and" a variable with itself, you are not adding any new information, so the result (true or false) is the same as the input.
- Idempotent law, OR form: $x + x = x$
	- Explanation: 
		- Similarly, if you "or" a variable with itself, you are not adding any new information, so the result (true or false) is the same as the input.
---
**The Inverse Law** 
- States that if you perform an operation with a value and its complement, the result is the identity for the opposite operation

	- AND form $xx' = 0$
	- OR form: $x + x' = 1$
	- This is different from arithmetic because in arithmetic we have different complements for + and *.
- Inverse law, AND form: $xx' = 0$
	- Explanation: 
		- The left hand side states "x and not x". Those cannot both be true, so the result is false.
- Inverse law, OR form: $x + x' = 1$
	- Explanation:
		- The left hand side states "x or not x". One of those is always true, so the result is the same.
---
- The Commutative Law, Associative Law and the Distributive Law are mostly parallel to the laws of arithmetic, except the *Distributive law, AND form*.
---
**The Commutative Law** 
- The same as in arithmetic, it states that the order of operands is immaterial.
	- AND form: $xy = yx$
	- OR form: $x + y = y + x$
---
**The Associative Law** 
- The same as in arithmetic, it states that the grouping of operands with the same operator is immaterial.
	- AND form: $(xy)z = x(yz)$
	- OR form: $(x + y) + z = x + (y + z)$
---
**The Distributive Law** 
- Explains how one operation can be "distributed" over the other.
-  In arithmetic we only have one distributive law, but in Boolean algebra we have two.
-  The distributive laws are named after the *inner* operation
- OR form: $x(y + z) = xy + xz$
	- This form resembles ordinary arithmetic.
	- Example:
		- If you have to take course X and either Y or Z to get you degree, then you take either X and Y, or X and Z.
- AND form: $x + yz = (x + y)(x + z)$
	- This from does not resemble ordinary arithmetic.
	- Example:
		- If you have to take course X or both Y and Z, then it's possible to say the following two things of every student:
			- That person took X or Y.
			- That person took X or Z.
---
- The last group: Absorption Law, DeMorgan's Law, and Double Complement Law are extremely useful in **simplifying Boolean functions**.
---
**Absorption Law**
- AND form: $x(x + y) = x$
- Explanation:
	- "x is true" is a stronger statement than "x or y is true". So if both the stronger and the weaker statements are true, then we only need to state the stronger one.
- OR form: $x + xy = x$
- Explanation:
	- The cases where "x and y" is true are a subset of the cases where x is true. Therefore the "x and y" term doesn't add anything to the disjunction of the two terms. Adding a subset of x to x just gives x again.
---
**DeMorgan's Law**
- And form: $-(xy) = -x + -y$
- Explanation:
	- If "x and y" is false, then one or the other must be false.
	This truth table shows the validity of the AND version of DeMorgan's Law. The shaded columns show the values of the left- and right-hand sides, and they are identical.
	

| **x** | **y** | **(xy)** | **(xy)'** | **x'** | **y'** | **x' + y'** |
|:-----:|:-----:|:--------:|:---------:|:------:|:------:|:-----------:|
|   0   |   0   |    0     |     1     |   1    |   1    |      1      |
|   0   |   1   |    0     |     1     |   1    |   0    |      1      |
|   1   |   0   |    0     |     1     |   0    |   1    |      1      |
|   1   |   1   |    1     |     0     |   0    |   0    |      0      |

- OR form: $-(x + y) = (-x)(-y)$
- Explanation:
	- If "x or y" is false, then the only way that can happen is if both x is false and y is false. 
---
**Double Complement Law**
- Both AND and OR form: $x'' = x$
- Explanation:
	- If the complement of an expression is true, the expression must be false. So if $x''$ is true, then $x'$ is false, which means $x$ is true. Similarly if $x''$ is false.
- This law is useful because we can use DeMorgan's Laws to **take the complement of an expression.**
---
- Sometimes it is more economical to build a circuit using the complement of a function (and complementing its result) that it is to implement the function directly.
- DeMorgan's law is an easy way to find the complement of a Boolean function. You may have to apply them multiple times.
- Like many laws, DeMorgan's laws can be extended to any number of variables.
- To do so, replace each variable by its complement and change all ANDs to ORs and all ORs to ANDs.
- Thus the complement of: $F (x, y, z) = (xy) + (x'z) + (yz')$ is:
	- $F'(x,y,z) = ((xy) + (x'z) + yz')' = (xy)'(x'z)'(yz')' = (x' + y')(x + z')(y' + z)$
---
	This truth table gives and example showing that a function and its complement have opposite values.
	

| **x** | **y** | **z** | **yz'** | **x' + yz'** | **y' + z** | **x(y' + z)** |
|:-----:|:-----:|:-----:|:-------:|:------------:|:----------:|:-------------:|
|   0   |   0   |   0   |    0    |      1       |     1      |       0       |
|   0   |   0   |   1   |    0    |      1       |     1      |       0       |
|   0   |   1   |   0   |    1    |      1       |     0      |       0       |
|   0   |   1   |   1   |    0    |      1       |     1      |       0       |
|   1   |   0   |   0   |    0    |      0       |     1      |       1       |
|   1   |   0   |   1   |    0    |      0       |     1      |       1       |
|   1   |   1   |   0   |    1    |      1       |     0      |       0       |
|   1   |   1   |   1   |    0    |      0       |     1      |       1       |







