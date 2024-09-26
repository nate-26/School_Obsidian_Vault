- As there are numerous ways to write Boolean expressions, we use a standardized form called canonical forms.
- Most useful canonical form for Boolean expressions: sum-of-products form.
	- In sum-of-products form, terms are connected by OR
	- Each term is made of variables (or their negations) combined with AND
	- Each term contains all the variables used in the original expression, either in their base form or their negated form.
	- Example: $f(x,y) = x(!y) + xy$
- Terms used to make up sum-of-products form are called *minterms*
	- For a function of *n* variables, each minterm contains exactly *n* items AND'ed together.
	- I.e., $(-x)(-y), (-x)y, x(-y), xy$
	- Some or all terms are OR'd together to create sum-of-products form for any function of two variables.
- To make results unique, we use a way to ensure that terms always come in same order.
- **We use the following rule:**
	1. Alphabetize the variables in each term.
	2. Alphabetize the terms, considering the negative form of a variable to precede the positive one, i.e., -x before x.
- So whichever of the four minterms are used, they will remain the that order:
	- $(-x)(-y), (-x)y, x(-y), xy$
- Purpose of unique representation is to make it easy to compare two expressions
	- Convert to sum-of-products form, then compare.
- Sum-of-products form for 3-variable expression: 
	- $F(x,y,z) = x(!y)(!z) + x(!y)z + xyz$
	- *These minterms were chosen from the 8 possible minterms of 3 variables*
- To show that every function can be expressed in sum-of-products form, an algorithm is given:
$$
F(x,y,z) = x!z + y
$$

| $x$ | $y$ | $z$ | $x!z + y$ |
| --- | --- | --- | --------- |
| 0   | 0   | 0   | 0         |
| 0   | 0   | 1   | 0         |
| 0   | 1   | 0   | 1         |
| 0   | 1   | 1   | 1         |
| 1   | 0   | 0   | 1         |
| 1   | 0   | 1   | 0         |
| 1   | 1   | 0   | 1         |
| 1   | 1   | 1   | 1         |
- To convert a function to sum-of-products form, start with truth table (above)
- Every row that results in a 1 contains a combination of values of variables that makes the function true.
- So we AND together that set of values
- The function is true if any one of those set of values occurs, so we OR the sets together.
- The function has 5 rows that return true, so the sum-of-products representation will have 5 terms.
- Each term will show the values of x, y and z that are needed to make that term true. 
	- *If x is false (0) then !x is true.*
- $F(x,y,z) = !xy!z + !xyz + x!y!z + xy!z + xyz$
- If sum-of-products is built from a truth table, the terms will always come out in correct order.
