- Boolean operators can be described using a truth table
- Truth table has one row for each possible value of the set of variables in the expression
- If expression has 2 variables, truth table will have 2^2 rows.
- If expression has 3 variables, truth table will have 2^3 rows.
X AND Y:

|  X  |  Y  | XY  |
|:---:|:---:|:---:|
|  0  |  0  |  0  |
|  0  |  1  |  0  |
|  1  |  0  |  0  |
|  1  |  1  |  1  |
X OR Y:

|  X  |  Y  | X + Y |
|:---:|:---:|:-----:|
|  0  |  0  |   0   |
|  0  |  1  |   1   |
|  1  |  0  |   1   |
|  1  |  1  |   1   |
NOT X:

|  X  | X'  |
|:---:|:---:|
|  0  |  1  |
|  1  |  0  |
- A Boolean function is a function of zero or more Boolean variables
- The output of a Boolean function is also a Boolean value, i.e., 0 or 1
- Truth table for the Boolean function:
$$F(x,y,z) = x!z + y$$

|  x  |  y  |  z  | z'  | xz' | xz' + y |
|:---:|:---:|:---:|:---:|:---:|:-------:|
|  0  |  0  |  0  |  1  |  0  |    0    |
|  0  |  0  |  1  |  0  |  0  |    0    |
|  0  |  1  |  0  |  1  |  0  |    1    |
|  0  |  1  |  1  |  0  |  0  |    1    |
|  1  |  0  |  0  |  1  |  1  |    1    |
|  1  |  0  |  1  |  0  |  0  |    0    |
|  1  |  1  |  0  |  1  |  1  |    1    |
|  1  |  1  |  1  |  0  |  0  |    1    |
*Table includes two work columns for simplicity*
- To evaluate functions, go by highest priority; NOT has highest, followed by AND and then OR.
- Evaluate x(!z) first.
- To do that, evaluate !z
- Then OR the result with y.