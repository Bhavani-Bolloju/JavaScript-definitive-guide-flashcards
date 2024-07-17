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
  <summary>Explain Bitwise operators in JavaScript?</summary>

  - Bitwise operators deal with numeric values at binary level, manipulating individual bits of a numeric value.
  - Providing way to perform operations at a low level.
</details>

<details>
<br/>
  <summary>Purpose of bitwise operators?</summary>

  - They are used in low level programming, where direct manipulation of bits is required.
  - Example includes system programming, device drivers, where direct control over memory and hardware is required.
  - Bitwise operators can be used for memory management, creating data structure and using memory in constrained environment.
  
</details>

<details>
<br/>
  <summary>Two catergories of bitwise operators and what are they?</summary>
  
  #### Logical Bitwise operators:
  - perform boolean algebra on the operands,means they perform boolean logic on each bit of the numeric value.
  - &(AND), |(OR), ^(XOR), ~(NOT).
  #### Shift operators:
  - These operators shift bits to the right and left;
  - <kbd>>></kbd>(right shift), <kbd><<</kbd>(left shift), <kbd>>>></kbd> (shift right with zero fill).
</details>

<details>
<br/>
  <summary>How do bitwise Logical operators works?</summary>

  - <kbd>&</kbd>(AND): Returns a bit set to 1 if both corresponding bits are 1
    <br/>
    **Example**: 0101 & 0011 = 0001
  - <kbd>|</kbd>(OR): Returns a bit set to 1 if at least one of the corresponding bits is 1
    <br/>
    **Example**: 0101 | 0011 = 0111
  - <kbd>^</kbd>(XOR): Returns a bit set to 1 if one (but not both) of the corresponding bits is 1
    <br/>
    **Example**: 0101 ^ 0011 = 0110
  - <kbd>~</kbd>(NOT): Inverts all the bits of the operand
    <br/>
    **Example**: ~0101 = 1010 
  
</details>
<details>
<br/>
  <summary>Left and right shift operators equivalent to mathematical operations in javascript?</summary>

  - Left shifting a number by "n" positions is equivalent to multiplying the number by <kbd>2**n</kbd>.
    <br/>
    **Example:** 5 << 3 ⇒ 5* 2^3
  - Right shifting a number by "n" positions is equivalent to dividing the number by <kbd>2^n</kbd> and discarding any remainder (floor division).
    <br/>
    **Example:** 5 >> 3 ⇒ 5 / 2 ^ 3
  
</details>

<details>
<br/>
  <summary>How to Perform base conversions in javascript (from decimal to binary / hexa or vice versa)?</summary>
  
  - Numeric values in javascript are represented using <kbd>base 10</kbd> by default, but we can convert numeric value to different base.
    -  call **toString()** method on any number and pass the desired base(2-base,8-octal,16-hexadecimal) as an argument.
      <br/>
</details>

<details>
<br/>
  <summary>How to convert the numbers of any base to the decimal number( base 10)?</summary>
  
  - we can convert binary(base 2), hexa(base 16) and octal(base 8) or any base representation to a decimal value(base 10) using **parseIn** function.
  - It takes two arguments, the string representation of the number and the current base value.

</details>

### Relational Expression and comparison operators

<details>
<br/>
  <summary>What are the two operators that we use to check if both the values are equal?</summary>
  
  - we have strict equality and relaxed equality to check if both the values are same, based on different definition of sameness:

  - **Strict equality(===)** - It doesn’t perform type conversion and returns true only of both the operands are of same type and value.

  - **Relaxed equality(==)** - It does perform type conversion and try to convert the operands to same type before making the comparison.

</details>

<details>
<br/>
  <summary>Method to make local comparison of strings in alphabetical order and what’s the use of the method?</summary>
  
  - **String.localCompare()** — is a string comparing algorithm, that performs local-sensitive string comparison, based on rules defined by a particular language.
  - **Useful:** when comparing strings that respect language specific sorting rules, such as handling accented characters correctly.
  - sorting strings in a way that is sensitive to user’s locale.
</details>

<details>
<br/>
  <summary>Explain the possible values the local comparison method returns?</summary>
  
  - <kbd>-ve</kbd> number indicates that the reference string comes before compare string.
  - <kbd>+ve</kbd> number indicates that the reference string comes after compare string.
  - <kbd>0</kbd> indicates that both the reference and compare strings are equivalent.
</details>

<details>
<br/>
  <summary>what type of values does comparison operator expect?</summary>
  
  - Comparison operator can accept operands of any type, but comparison can be done only between string and number type, so operand of neither type are     converted to either number or string.
  - It also allows to mix operands of different types like numeric and BigInt values, unlike arithmetic operator that doesn’t support mixed operands.
</details>

<details>
<br/>
  <summary>How are string compared in javascript?</summary>
  
  - String comparison is done character by character, using unicode value of the character at that corresponding position
  - The comparison is lexicographic, means it follows the order of characters in a dictionary,characters are also case-sensitive, uppercase characters have low   value than to the lowercase characters.
</details>

<details>
<br/>
  <summary>Explain <kbd>in</kbd> operator</summary>
  
  - <kbd>in</kbd> operator checks if particular property name in the form of a string exists in the object.
  - If the left operand is a number, it checks if that particular index exists in the array,not the value itself.
</details>

<details>
<br/>
  <summary>Explain <kbd>instanceOf</kbd> operator</summary>
  
  - This operator is used to check if the object is an instance of particular class or a constructor function.
  - check the objects prototype chain to find constructor’s prototype.
  - The right side operand needs to be a class or a function otherwise typeError is thrown
  - If the left side operand is not an object, false is returned.
</details>

<details>
<br/>
  <summary>Explain Prototype Chain</summary>
  
  - Every object has [[prototype]] internal property, also can refer to as <kbd>_ _proto_ _</kbd> , this proto points to another object, which is objects prototype.
  - when object is creates it’s prototype value is set to the prototype value of the class/constuctor function that been used to create the object.
  - the creates a chain of objects linked by their prototype forming “prototype chain”. ****
  - the top of the chain is the Object.prototype.
</details>


### Logical Expressions

<details>
<br/>
  <summary>Explain three levels of understanding of <kbd>&&(AND)</kbd>operator</summary>
  
  - **basic level** - AND operator returns true if and only if two values are true otherwise false.
  - **second level** -any value in javascript can be either truthy or falsy, AND opertor doesn’t expect it operands to be boolean, if both the operands are truthy the, truthy value is returned.
  - **third level** - JavaScript takes multiple values, evaluate the operands from left to right and if the value evaluates to false, it short-circuites and returns the value without evaluating any further, otherwise evaluates the right operand and returns the value.
</details>

<details>
<br/>
  <summary>what is short circuiting?</summary>
  
  - It is the behaviour of boolean operands to stop evaluating the expression as soon as the final result is determined.
  - Result of operation become the value of entire expression.
</details>

<details>
<br/>
  <summary>what is the main purpose of the <kbd>OR(||)</kbd> logic operator?</summary>
  
  - The purpose is to return the first truthy value found from the set of alternate options.
  - It was also used to set default values for the parameters and properties that don’t have values.
</details>

<details>
<br/>
  <summary>What is a <kbd>not not (!!)</kbd> operator and what does it do?</summary>
  
  - Every value in javascript is either a truthy or a falsy value, we can use <kbd>not not (!!)</kbd> operator to convert any value into its corresponding boolean representation.
  - First negates to the truthiness or falsiness of the value, then negates again, the result is the boolean value.
</details>


### Assignment expressions and Evaluation expression
will add soon.....










