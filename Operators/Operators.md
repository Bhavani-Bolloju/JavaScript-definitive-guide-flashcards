## Operators in JavaScript

### Operators overview

<details>
<br/>
  <summary>what is an Arity? how are operators catergorized?</summary>

- Arity refers to number of operands an operator expects to perform its operation.
- Operators are catergorized based on their arity:
  - **Unary** operator that accepts single operand.
  - **Binary** operator that accepts two operands
  - **Ternary** operator with three operands
  - unary - !(not), binary(+,-), ternary(?: )

</details>
<details>
<br/>
  <summary>what is an <kbd>lvalue</kbd> expression?</summary>

- Expression that can exists on the left side of assignment operator, lValue refers to left value.
- It refers to the memory location that can hold a value, it means we can assign a value to an lvalue.
- lvalue designates a location where data can be stored or modified.
- Example of ivalue are variable name, array elements, object properties.

</details>

<details>
<br/>
  <summary>what are the operators that cause side effects in javascript?</summary>

- Side effects refer to change in the state of a program caused by the operation itself not just the returned value.
- Example of such operators are
  - assignment operator, increment, decrement operators , delete, directly modify the variable values.
  - all the expression using this variable also change.
- Function call and object creation expression also have side effects, we need to be cautious when dealing with mutable state
</details>

<details>
<br/>
  <summary>what is an operator precedence and how can it be overridden?</summary>

  - The order in which javascript evaluates the operations within an expression.
  - The operator with higher precedence value is evaluated first.
  - We can group parts of the expression in a parentheses and force them to evaluate first.
  - Wrapping in parentheses only affect the precedence value not the associativity.
</details>

<details>
<br/>
  <summary>what is associativity, give example of operators that have right to left associativity?</summary>

  - Associativity refers to the order in which operators of the same precedence are evaluated.
  - Assignment ,exponentiation, unary(++, - -) and ternary conditional operator all these have right to left associativity
</details>

<details>
<br/>
  <summary>when does order of evaluation makes sense?</summary>

  - Order of evaluation makes sense when expression being evaluated has some side effects.
  - Helps in predicting the outcome and ensures program behaves as expected.
</details>

### Arithmetic Expressions

<details>
<br/>
  <summary>when does an operation results in <kbd>NaN</kbd> using arithmetic operators?</summary>

  - Arithmetic operators convert operands to numeric values if needed.
  - If any operand is NaN or cannot be converted to a number, the result is NaN.
    #### Specifically:
    - If an operand is NaN, the entire expression evaluates to NaN.
    - Strings that cannot be converted to numbers result in NaN.
    - undefined converts to NaN, so operations involving undefined result in NaN
    - null converts to 0, so operations involving null do not result in NaN unless combined with NaN or non-numeric values.
    - null+1 = 1
    - undefined + 1 = NaN.
</details>

<details>
<br/>
  <summary>why is it important to wrap expression what contains unary operator with exponentiation in parentheses?</summary>

  - new operators like exponentiation have some specific precedence rule that can lead to confusion especially when combined with unary operators.
  - Wrapping the unary operator and its operand in parentheses ensures the correct order of operations and avoids ambiguity.
  - !(2**3) / !(2)**3
</details>

<details>
<br/>
  <summary>Explain unary arithmetic operator and what they do?</summary>

  - unary operators accept single operand as its value, they have higher precedence value, they convert their operand to numeric value if needed.
  - Some of the unary operators are plus(+), minus(-), increment(++), decrement(- -).
  - unary plus and minus are often used to perform type coercion, increment and decrement are used to explicitly modify the variable value.
  - commonly used in expressions, loops and control flow structures.
  - Wrapping the unary operator and its operand in parentheses ensures the correct order of operations and avoids ambiguity.
</details>

<details>
<br/>
  <summary>what’s the difference between unary pre and post-increment\decrement operators?</summary>

  - Post-increment/decrement
    - returns the current value before modifying it, Useful when the original value is needed before updating.
  - pre-increment/decrement
    - returns the modified value after the increment/decrement operation, Useful when the updated value is needed immediately.
  - In both the cases the variable will be updated as intended, difference lies in the value they return.
</details>

<details>
<br/>
  <summary>Explain how +(<kbd>plus</kbd>) operator works when dealing with different values as it operand?</summary>

  - The + operator gives preference to concatenation. If either operand is a string, it converts the other operand to a string and performs concatenation.
  - If neither operand is a string, it attempts numeric conversion if possible and performs the addition operation.
  - If either operand is an object, it uses the object-to-primitive conversion algorithm. If the resultant primitive value is a string, it converts the other operand to a string (to concatenate). Otherwise, it tries to convert to a numeric value (for a numeric operation or resulting in NaN).
</details>

### Bitwise Operator

<details>
<br/>
  <summary>what do bitwise operators do?</summary>

  - Bitwise operators deal with numeric values at binary level, manipulating individual bits of a numeric value.
  - Providing way to perform operations at a low level.
</details>


