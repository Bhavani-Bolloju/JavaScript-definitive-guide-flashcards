## Expressions in JavaScript

<!-- 1 -->
<details>
  <summary>What is an expression in JavaScript, give an example</summary>
  An expression is a phrase, when evaluated produces a value in JavaScript.
<br/>
  Examples:
  
- Variable names that evaluate to whatever value that been assigned.
- Array access expression.
- Function invocation expression etc.
</details>

<!-- 2 -->
<details>
<summary>Purpose of expressions in JavaScript?</summary>
  
  - Programming involves manipulating data to achieve desired outcome.
  - This can be done by making decision, performing calculations, storing values and using operators to create expression.
  - Expression are important as they allow to handle and process data.
</details>

<!-- 3 -->
<details>
<summary>How are complex expressions built?</summary>

  - Complex expressions are built using operators.
  - This expression is then evaluated to return a “value”.
</details>

<!-- 4 -->

<details>
<summary>What is a primary expression and it's three types?</summary>

  - Primary expressions are simplest form of expressions in Javascript.
  - They directly represent values in a code.
  - The three types of primary expressions are:
    - constants and literal values (numbers, strings, regular expression literals)
    - language keywords (this, null, true, false - reserved words of the JS)
    - variable references (name of the variable or a constant, global object that refer to some value)
</details>

<!-- 5 -->
<details>
<summary>Purpose of conditional access property expression?</summary>

  - The conditional access property expression (<kbd>?.</kbd> or <kbd>[]?.</kbd>) is a new ES6 feature.
  - Trying to access property of null or undefined results in JS throwing typeError.
  - The purpose is to prevent Javascript from throwing such error.
  
</details>

<!-- 6 -->
<details>
<summary>Explain invocation expression and how functions are executed?</summary>

  - Invocation expression is used to call/invoke functions.
  - The left hand operand of the invocation expression must be a function value, otherwise JS throws typeError.
  - Arguments passed to the invocation expression are assigned to the function’s parameters.
  - The function body is then executed.
  - The result of the invocation expression is the return value of the function, or undefined if there's no return statement present in the function body.
  
</details>

<!-- 7 -->
<details>
<summary>how is function invocation different from method invocation?</summary>

  - Function invocation is when we call/invoke a standalone function using invocation expression.
    - It is not tied to any object or context.
  - Method invocation occurs when we call a property of the object which is a function value.
    - the function being invoked is associated with an object, and it may operate on the object.
  
</details>



















