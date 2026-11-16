
# Datatypes & Type Conversions

## Overview

This notebook provides a detailed introduction to Python's built-in data types and type conversion mechanisms. Understanding data types is fundamental to Python programming because every value in Python is an object associated with a specific type. The notebook explores how Python categorizes data, stores values, and allows conversion between different data types.

---

## Learning Objectives

After completing this notebook, you will be able to:

- Understand Python's dynamic typing system.
- Identify built-in data types.
- Determine the type of any object.
- Perform explicit type conversions.
- Understand implicit type conversions.
- Distinguish between mutable and immutable data types.
- Handle conversion-related errors effectively.

---

## Topics Covered

### 1. Introduction to Data Types

- What is a data type?
- Why data types are important.
- Python's dynamic typing mechanism.
- Objects, values, and types.

### 2. Numeric Data Types

#### Integer (`int`)

- Arbitrary precision integers.
- Internal storage using `PyLongObject`.
- Binary representation of integers.

#### Floating Point (`float`)

- IEEE 754 double-precision format.
- Sign bit, exponent, and mantissa.
- Floating-point precision limitations.

#### Complex Numbers (`complex`)

- Real and imaginary components.
- Mathematical operations.

---

### 3. Boolean Data Type (`bool`)

- `True` and `False`
- Relationship between `bool` and `int`
- Truthy and falsy values
- Boolean expressions

---

### 4. String Data Type (`str`)

- String creation and representation
- String immutability
- Escape sequences
- Unicode support
- Raw strings

---

### 5. Collection Data Types

#### List (`list`)

- Ordered collection
- Mutable nature
- Dynamic resizing

#### Tuple (`tuple`)

- Ordered collection
- Immutable structure
- Mutable objects inside tuples

#### Set (`set`)

- Unordered collection
- Unique elements
- Hashability requirements

#### Dictionary (`dict`)

- Key-value storage
- Hash table implementation
- Key constraints

---

### 6. NoneType (`None`)

- Meaning of `None`
- Usage scenarios
- Difference between `None` and other empty values

---

### 7. Type Inspection

Understanding object types using:

```python
type()
```

Topics include:

- Runtime type identification
- Class relationships
- Object hierarchy basics

---

### 8. Explicit Type Conversion

Converting values using:

```python
int()
float()
str()
bool()
list()
tuple()
set()
dict()
```

Examples include:

- String to integer conversion
- Integer to float conversion
- Numeric to string conversion
- Collection conversions

---

### 9. Implicit Type Conversion

Automatic conversions performed by Python:

Examples:

```python
10 + 5.5
```

Concepts covered:

- Type promotion
- Numeric coercion
- Safe conversions

---

### 10. Conversion Errors

Common exceptions:

```python
ValueError
TypeError
```

Understanding:

- Why conversions fail
- Error handling best practices
- Data validation techniques

---

### 11. Floating Point Precision

Special discussion on:

```python
0.1 + 0.2
```

Topics include:

- Binary representation of decimal fractions
- IEEE 754 limitations
- Precision errors
- Rounding techniques

---

### 12. String Representations

Understanding:

```python
str()
repr()
```

Differences between:

- User-friendly representation
- Developer-friendly representation
- Debugging use cases

---

### 13. Mutability and Immutability

Mutable types:

- list
- set
- dict

Immutable types:

- int
- float
- bool
- str
- tuple

Discussion of:

- Object identity
- Memory behavior
- Reference semantics

---

## Key Takeaways

- Everything in Python is an object.
- Every object has a type.
- Python is dynamically typed.
- Integers have arbitrary precision.
- Floats use IEEE 754 representation.
- Explicit and implicit conversions are common in Python.
- Mutable and immutable types behave differently.
- `repr()` and `str()` serve different purposes.
- Understanding data types improves debugging, memory management, and program design.

---

## Prerequisites

- Python Installation
- Basic Python Syntax
- Variables and Identifiers
- Input and Output Operations

---

## Next Steps

After completing this notebook, continue with:

- Operators and Expressions
- Memory Management
- Object Model
- Mutability and References
- Internals of Built-in Data Structures
