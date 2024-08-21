# Lesson 2: First-Order Logic (FOL) Basics

## Understanding Constants, Variables, Predicates, and Functions

First-Order Logic (FOL), also known as predicate logic, extends propositional logic by incorporating quantifiers and allowing the use of variables, constants, predicates, and functions. This enables more expressive statements about objects and their relationships.

### Constants

Constants are symbols that represent specific objects or entities in the domain of discourse. For example:
- **a** could represent "Alice."
- **b** could represent "Bob."
- **3** could represent the number three.

Constants are used to refer to particular individuals within a logical framework.

### Variables

Variables are symbols that can represent any object in the domain of discourse. They are often used in predicates to express general statements. For example:
- **x**, **y**, and **z** are common variables that can stand for any object.

### Predicates

Predicates are functions that return a truth value (true or false) based on the input they receive. They express properties of objects or relationships between objects. A predicate can be thought of as a statement that contains one or more variables. For example:
- **P(x)** might represent "x is a student."
- **Loves(x, y)** might represent "x loves y," where both x and y are variables.

### Functions

Functions in FOL are used to map objects to other objects. They can take one or more arguments and return a single object. For example:
- **f(x)** could represent "the father of x."
- **g(x, y)** could represent "the sum of x and y."

Functions allow for more complex relationships and operations within FOL.

## Translating Simple Statements into FOL

To effectively use FOL, we need to translate natural language statements into FOL expressions. Here are some steps and examples to illustrate this process.

### Example 1: Simple Predicate

**Natural Language Statement:** "Alice is a student."

**FOL Translation:**
- Let **S(x)** represent "x is a student."
- The translation would be: **S(a)**, where **a** is the constant representing Alice.

### Example 2: Predicate with Variables

**Natural Language Statement:** "Everyone loves Bob."

**FOL Translation:**
- Let **Loves(x, b)** represent "x loves Bob," where **b** is the constant representing Bob.
- The translation would be: **∀x Loves(x, b)**, meaning "for all x, x loves Bob."

### Example 3: Existential Quantifier

**Natural Language Statement:** "There exists a student who loves Alice."

**FOL Translation:**
- Let **S(x)** represent "x is a student" and **Loves(x, a)** represent "x loves Alice."
- The translation would be: **∃x (S(x) ∧ Loves(x, a))**, meaning "there exists an x such that x is a student and x loves Alice."

### Example 4: Combining Predicates and Functions

**Natural Language Statement:** "Every student has a father."

**FOL Translation:**
- Let **S(x)** represent "x is a student" and **f(x)** represent "the father of x."
- The translation would be: **∀x (S(x) → ∃y (y = f(x)))**, meaning "for all x, if x is a student, then there exists a y such that y is the father of x."

## Exercises

### Exercise 1: Translate the following statements into FOL.

1. "All cats are animals."
2. "There is a dog that barks."
3. "If it rains, then the ground is wet."

### Exercise 2: Identify the constants, variables, predicates, and functions in the following FOL expressions.

1. **∀x (Cat(x) → Animal(x))**
2. **∃y (Dog(y) ∧ Barks(y))**
3. **Loves(a, f(b))**

### Answers

1. **Exercise 1:**
   - "All cats are animals." → **∀x (Cat(x) → Animal(x))**
   - "There is a dog that barks." → **∃y (Dog(y) ∧ Barks(y))**
   - "If it rains, then the ground is wet." → **Rains → Wet(Ground)**

2. **Exercise 2:**
   - For **∀x (Cat(x) → Animal(x))**: 
     - Constants: None
     - Variables: x
     - Predicates: Cat(x), Animal(x)
     - Functions: None
   - For **∃y (Dog(y) ∧ Barks(y))**: 
     - Constants: None
     - Variables: y
     - Predicates: Dog(y), Barks(y)
     - Functions: None
   - For **Loves(a, f(b))**: 
     - Constants: a, b
     - Variables: None
     - Predicates: Loves(a, f(b))
     - Functions: f(b)

By understanding and practicing these concepts, you will build a strong foundation in First-Order Logic, which is essential for more advanced logical reasoning and formal methods.