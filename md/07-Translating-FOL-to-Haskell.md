# Lesson 7: Translating First-Order Logic (FOL) to Haskell

## Representing Constants, Predicates, and Logical Statements in Haskell

Translating First-Order Logic (FOL) into Haskell involves representing logical statements using Haskell's data types, functions, and expressions. This allows us to leverage Haskell's strong type system and functional programming features to model logical reasoning.

### 1. Representing Constants

In FOL, constants represent specific objects in the domain of discourse. In Haskell, we can represent constants using variables or specific values.

**Example:**
- Let’s say we have a constant **a** representing "Alice." In Haskell, we can represent it as:

```haskell
alice :: String
alice = "Alice"
```

### 2. Representing Predicates

Predicates in FOL express properties or relationships between objects. In Haskell, we can represent predicates as functions that return a Boolean value.

**Example:**
- Let’s define a predicate **P(x)** that represents "x is a student." In Haskell, we can implement it as:

```haskell
isStudent :: String -> Bool
isStudent name = name `elem` ["Alice", "Bob", "Charlie"]  -- Example list of students
```

### 3. Representing Logical Statements

Logical statements in FOL can be represented using Haskell's functions and logical operators. We can use standard Haskell operators like `&&` (and), `||` (or), and `not` (negation).

**Example:**
- Consider the FOL statement: "If x is a student, then x is enrolled."

In Haskell, we can represent this as:

```haskell
isEnrolled :: String -> Bool
isEnrolled name = isStudent name  -- For simplicity, assume all students are enrolled
```

## Implementing Logical Expressions and Functions in Code

Now that we understand how to represent constants and predicates, let’s implement some logical expressions and functions in Haskell with hands-on examples.

### Example 1: Simple Logical Expression

**FOL Statement:** "All students are enrolled."

**Haskell Implementation:**

```haskell
allStudentsEnrolled :: [String] -> Bool
allStudentsEnrolled students = all isEnrolled students

-- Example usage
studentsList :: [String]
studentsList = ["Alice", "Bob", "Charlie"]

-- Check if all students are enrolled
result :: Bool
result = allStudentsEnrolled studentsList  -- This will return True
```

### Example 2: Using Quantifiers

**FOL Statement:** "There exists a student who is not enrolled."

**Haskell Implementation:**

```haskell
existsNotEnrolled :: [String] -> Bool
existsNotEnrolled students = any (not . isEnrolled) students

-- Example usage
studentsList2 :: [String]
studentsList2 = ["Alice", "Bob", "David"]  -- Assume David is not a student

-- Check if there exists a student who is not enrolled
result2 :: Bool
result2 = existsNotEnrolled studentsList2  -- This will return True
```

### Example 3: Combining Predicates

**FOL Statement:** "If x is a student and x is enrolled, then x can take the exam."

**Haskell Implementation:**

```haskell
canTakeExam :: String -> Bool
canTakeExam name = isStudent name && isEnrolled name

-- Example usage
result3 :: Bool
result3 = canTakeExam "Alice"  -- This will return True
result4 :: Bool
result4 = canTakeExam "David"  -- This will return False if David is not a student
```

### Example 4: More Complex Logical Expressions

**FOL Statement:** "For all students, if they are enrolled, they can take the exam."

**Haskell Implementation:**

```haskell
canAllTakeExam :: [String] -> Bool
canAllTakeExam students = all canTakeExam students

-- Example usage
result5 :: Bool
result5 = canAllTakeExam studentsList  -- This will return True if all students can take the exam
```

## Summary

In this lesson, we learned how to translate First-Order Logic (FOL) into Haskell by representing constants, predicates, and logical statements. We implemented logical expressions and functions using Haskell’s syntax and functional constructs, allowing us to model logical reasoning effectively. By practicing these translations, you will become more comfortable with both FOL and Haskell, enabling you to apply logical reasoning in programming contexts.