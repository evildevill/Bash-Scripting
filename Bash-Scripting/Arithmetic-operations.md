# 

# **Bash Arithmetic Operators**

| Arithmetic Operator | Description |
| --- | --- |
| +, - | Addition and  subtraction |
| *, /, % | Multiplication, division,  and the remainder (modulo) |
| ** | Exponentiation |
| <=, >=, <, > | Less than or equal, greater than or equal, less than, and greater than. |
| ==, != | Equality (equal to) and  inequality (not equal to) |
| =, *=, /=, %=, +=, -=, «=, »=, &=, ^=, |= | Assignment operators |
| id++, id -- | Variable post-increment and  post-decrement |
| ++id, --id | Variable pre-increment and pre-decrement |
| && | Logical AND |
| || | Logical OR |
| -, + | Unary minus, plus |
| !, ~ | Logical and bitwise negation |
| «, » | Left and right bitwise shifts |
| & | Bitwise AND |
| ^ | Bitwise XOR |
| | | Bitwise OR |
| expression ? expression : expression | conditional  ternary operator |

# Using `expr` to perform arithmetic operations

```bash
#!/bin/bash

# Basic arithmetic using expr
:"
Because expr is a binary rather than a shell built-in, this method may be slow. In a large for-loop, 
it will fork a new process, which is undesirable. Furthermore, depending on the implementation, the behavior 
of expr may differ between systems.

In contrast, to let, you do not need to enclose the expression in quotes. There must also be spaces between 
the expression's items. To save the output to a variable, like any other command you can use command 
substitution to capture the output of expr into a variable.
"

# expr syntax
expr item1 operator item2

# Note that there must be spaces between the items and no quotes.
expr 7 + 5 #=> 13

expr "6 + 3" #=> 6 + 3

# If you put quotes the expression will not be evaluated but printed instead.
expr 3+2 #=> 3+2

# The asterisk has a special meaning in bash so we must escape it using \ to remove its special meaning.
expr 5 \* 3

# modulus operator demonstration
expr 15 % 2 #=> 1

# using command substitution to save the output to a variable
result=$( expr 15 - 2 )
echo $result #=> 13
```

<aside>
💡 The square brackets `$[...]` can also do Arithmetic Expansion in Bash, though this notation has been deprecated and should be avoided. Instead, prefer the use of `$((...))` instead.

Like let you can also use the `declare` builtin with the  `-i` option to do arithmetic operations

</aside>

# Using `let` to perform arithmetic operations

```bash
#!/bin/bash

# Basic arithmetic using let
:"
let is a Bash built-in function that allows us to perform simple arithmetic. 

The arithmetic expression can take several forms, which we'll go over below. However, the first part is 
always a variable into which the result is saved.
"

# The let has the following syntax:
let <arithmetic expression>

# It is important to note that if we do not use quotes around the expression, it must be written without
# spaces.
let result=6+4
echo $result #=> 10

# This time, we used quotes to space out the expression and make it more readable.
let "result = 4 + 4"
echo $result #=> 8

# incremeting the result same as let result =result+1 or let result+=1
let result++
echo $result #=> 9

# doing some multiplication
let "result = 4 * 5"
echo $result # 20

# We can also use variables in expressions
let "result = $1 + 30"
echo $result # 30 + first command line argument
```

# Using `d****ouble parentheses` for arithmetic operations**

```bash
#!/bin/bash

# Basic arithmetic using double parenthesis

:"
The Arithmetic Expansion capability of the shell is the recommended way for evaluating arithmetic expressions 
with integers in Bash. The built-in shell expansion allows you to perform math calculations by using
 parentheses ((...)).
"

# The Bash arithmetic expansion is written in the format:
$((arithmetic expression))

# You can space out without the need for quotations to improve readability
result=$(( 6 + 5 ))
echo $result #=> 11

# This works the same
result=$((3+7))
echo $result #=> 10

# You can include other variables without the need of using $ on them, notice the **result** variable below.
result2=$(( result + 3 ))
echo $result2 #=> 11

# You can include variables with $ if you prefer.
result2=$(( $result + 4 ))
echo $result2 #=> 14

# when incrementing the variable you don't include the $ sign
(( result2++ ))
echo $result2 #=> 15

# incrementing the value by 3 this is the shorthand for result2 = result2 + 4.
(( result2 += 4 ))
echo $result2 #=> 19

# Unlike other methods, when we do multiplication we don't need to escape the * sign. This is what makes this
# method so powerful and versatile.
result=$(( 4 * 5 ))
echo $result #=> 20
```
