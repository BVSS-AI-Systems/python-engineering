
# Expressions & Operators

This notebook introduces Python expressions and operators, the fundamental building blocks used to perform calculations, comparisons, logical evaluations, and data manipulations. A strong understanding of operators is essential for writing efficient and readable Python programs.

## Topics Covered

- Expressions and their evaluation
- Operands and operators
- Arithmetic operators
- Comparison operators
- Logical operators
- Assignment operators
- Walrus operator (`:=`)
- Bitwise operators
- Membership operators
- Identity operators
- Operator precedence
- Associativity
- Short-circuit evaluation

## Learning Outcomes

By the end of this notebook, you will be able to:

- Create and evaluate Python expressions.
- Perform mathematical operations using arithmetic operators.
- Compare values using relational operators.
- Combine conditions using logical operators.
- Use assignment and augmented assignment operators.
- Understand and apply the walrus operator.
- Work with binary and bitwise operations.
- Check object identity and membership.
- Predict outcomes using operator precedence and associativity rules.

## Operator Categories

### Arithmetic Operators

Used for mathematical calculations.

```text
+   Addition
-   Subtraction
*   Multiplication
/   Division
//  Floor Division
%   Modulus
**  Exponentiation
```

### Comparison Operators

Used to compare values.

```text
==
!=
>
<
>=
<=
```

### Logical Operators

Used for combining multiple conditions.

```text
and
or
not
```

### Assignment Operators

Used to assign and update values.

```text
=
+=
-=
*=
/=
%=
//=
**=
***

### Bitwise Operators

Operate***rectly on binary representations***```text
&
|
***
<<
>>
```

### Membership Opera***s

Check whether a value exists *****collection.

```text
in***t in
```

### Identity Operators***ompare object identity.

```text***
is***t
```

## Important Concepts

##***xpressions

An expression is any***mbination of values, variables***unction calls, and operators tha***roduces a result***Examples:

```python
10***20
x * y
len(name*** > b
```

---

*** Operator Precedence

Python***llows a specific order when***aluating expressions.

Example:
***`python
10***5 * 2
```

Multip***ation occurs before addition.

-***
*** Associativity

Defines the dire***on in which operators are evalua*** when precedence is the same.

E***ples:

```python
10 - *** 2
```

```python
**** 3 ** 2
```

***

### Short-Circuit Evaluation

***hon avoids unnecessary evaluatio***hen the result is already determ***d***Examples:

```python
True or som***unction()
```

```python
False a***some_function()
```

---

### Wa***s Operator

Introduced in Python***8.

Allows assignment and evalua***n in a single expression.

Examp***

```python
if (n := len(data***> 5:
    print(n)
***

---

### Bitwise Shift***erators

Left Shift (`<<`)

***text
Multiply by powers of 2
```*****ht Shift (`>>`)

```***t
Divide by powers of 2
``***Examples:

```python
8 <<***  # 16
***>> 1  # 8
``***---

###***uality vs Identity

Value***uality:

```python
a == b
``***Checks whether values***e equal.

Object Identity:

```p***on
***s b
```

Checks whether both***ferences point to the same objec***
## Key Takeaways

- Expressions***ways produce a value.
- Operator***erform actions on operands.
- Py***n provides multiple categories o***perators for different use cases*** Bitwise operators work directly***th binary data.
- `==***hecks value equality, while `is`***ecks object identity.
- Understa***ng precedence prevents***expected results*** Short-circuiting improves effic***cy and safety.
- The walrus oper***r***ables assignment within***pressions.

## Prerequisites

- ***iables and Identifiers
- Python***ta Types
- Type Conversions

## ***t***pic

After mastering operators***d expressions, move on to:

- Co***tional Statements
- Control Flow***Loops***Functions
- Python Memory Model
***
