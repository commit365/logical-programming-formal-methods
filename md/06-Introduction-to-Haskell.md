# Lesson 6: Introduction to Haskell

## Overview of Haskell and Its Functional Programming Paradigm

Haskell is a purely functional programming language known for its strong static typing, lazy evaluation, and expressive syntax. It was named after the mathematician Haskell Curry and has gained popularity for its ability to handle complex problems with concise and elegant code.

### Functional Programming Paradigm

Functional programming is a programming paradigm that treats computation as the evaluation of mathematical functions and avoids changing state and mutable data. Key characteristics of functional programming include:

1. **First-Class Functions:** Functions are treated as first-class citizens, meaning they can be passed as arguments, returned from other functions, and assigned to variables.

2. **Higher-Order Functions:** Functions that can take other functions as parameters or return them as results.

3. **Immutability:** Data is immutable by default, meaning that once a value is assigned, it cannot be changed. This leads to safer and more predictable code.

4. **Pure Functions:** Functions that have no side effects; the output depends only on the input values. This makes reasoning about code easier.

5. **Lazy Evaluation:** Haskell evaluates expressions only when they are needed, which can improve performance and allow for the creation of infinite data structures.

## Basic Syntax

Haskell's syntax is designed to be clear and concise. Here are some fundamental aspects of Haskell syntax:

### 1. Comments

Comments in Haskell can be single-line or multi-line:
- **Single-line comment:** Starts with `--`
- **Multi-line comment:** Enclosed in `{-` and `-}`

```haskell
-- This is a single-line comment
{- This is a
   multi-line comment -}
```

### 2. Functions

Functions are defined using the following syntax:

```haskell
functionName :: Type1 -> Type2 -> ReturnType
functionName parameter1 parameter2 = expression
```

**Example:**
```haskell
add :: Int -> Int -> Int
add x y = x + y
```

### 3. Let Bindings

You can create local bindings using the `let` keyword:

```haskell
let x = 5
let y = 10
let z = x + y
```

### 4. Conditionals

Conditionals in Haskell are expressed using `if`, `then`, and `else`:

```haskell
isEven :: Int -> String
isEven n = if n `mod` 2 == 0 then "Even" else "Odd"
```

### 5. Case Expressions

`case` expressions allow for pattern matching:

```haskell
describeNumber :: Int -> String
describeNumber n = case n of
    0 -> "Zero"
    1 -> "One"
    _ -> "Another number"
```

## Data Types

Haskell has a rich type system that includes several built-in data types:

### 1. Basic Data Types

- **Int:** Integer numbers (fixed size)
- **Integer:** Arbitrary-precision integers
- **Float:** Floating-point numbers
- **Double:** Double-precision floating-point numbers
- **Char:** Single characters
- **String:** A list of characters

### 2. Lists

Lists are a fundamental data structure in Haskell, denoted by square brackets:

```haskell
numbers :: [Int]
numbers = [1, 2, 3, 4, 5]
```

### 3. Tuples

Tuples are fixed-size collections of elements that can be of different types:

```haskell
pair :: (Int, String)
pair = (1, "One")
```

### 4. Custom Data Types

You can define your own data types using the `data` keyword:

```haskell
data Shape = Circle Float | Rectangle Float Float
```

## Functional Constructs

Haskell supports several functional constructs that enhance its expressiveness:

### 1. Higher-Order Functions

Haskell allows you to create and use higher-order functions easily. For example, the `map` function applies a function to each element of a list:

```haskell
doubleList :: [Int] -> [Int]
doubleList xs = map (*2) xs
```

### 2. List Comprehensions

List comprehensions provide a concise way to create lists:

```haskell
squares :: [Int] -> [Int]
squares xs = [x^2 | x <- xs]
```

### 3. Lambda Functions

Lambda functions are anonymous functions defined using the `\` syntax:

```haskell
addTwo :: Int -> Int
addTwo = \x -> x + 2
```

## The Type System in Haskell

Haskell has a strong static type system, meaning that types are checked at compile time. This helps catch errors early and ensures that functions are used correctly.

### 1. Type Inference

Haskell can often infer the types of expressions automatically, reducing the need for explicit type annotations. For example, the following function will have its type inferred:

```haskell
multiply x y = x * y  -- Type inferred as Num a => a -> a -> a
```

### 2. Type Annotations

You can explicitly specify types using type annotations:

```haskell
divide :: Float -> Float -> Float
divide x y = x / y
```

### 3. Polymorphism

Haskell supports polymorphism, allowing functions to operate on different types:

```haskell
identity :: a -> a
identity x = x
```

This function can take any type and return a value of the same type.

## Conclusion

Haskell is a powerful functional programming language that emphasizes clear and concise code through its unique syntax and strong type system. By understanding its basic constructs, data types, and functional programming principles, you will be well-equipped to write effective Haskell programs and explore more advanced topics in functional programming.