# Lesson 18: Project: Building a Logic-Based Application

## Designing and Implementing a Logic-Based Application in Haskell

In this lesson, we will guide you through the process of designing and implementing a logic-based application using Haskell. The project will involve creating a simple rule-based expert system that can infer conclusions based on a set of rules and facts. This application will demonstrate the principles of logical programming and the power of Haskell's type system.

### Project Overview

**Application:** A simple expert system for diagnosing common ailments based on symptoms.

**Features:**
- Users can input symptoms.
- The system will infer possible ailments based on predefined rules.
- The application will provide recommendations for further action.

### Step 1: Define Requirements

Before we start coding, we need to define the requirements for our expert system:

1. **Input:** A list of symptoms provided by the user.
2. **Output:** A list of possible ailments and recommendations.
3. **Rules:** A set of logical rules that map symptoms to ailments.

### Step 2: Design the System

#### Data Structures

We will define the following data structures:

1. **Symptom:** A data type to represent symptoms.
2. **Ailment:** A data type to represent ailments.
3. **Rule:** A data type to represent the relationship between symptoms and ailments.

**Example:**

```haskell
data Symptom = Cough | Fever | Headache | Fatigue | Nausea deriving (Show, Eq)
data Ailment = Cold | Flu | Migraine | FoodPoisoning deriving (Show, Eq)

type Rule = (Ailment, [Symptom])  -- A rule maps an ailment to a list of symptoms
```

#### Rule Base

We will create a rule base that contains the rules for diagnosing ailments based on symptoms.

**Example:**

```haskell
rules :: [Rule]
rules = [
    (Cold, [Cough, Fatigue]),
    (Flu, [Fever, Cough, Fatigue]),
    (Migraine, [Headache, Nausea]),
    (FoodPoisoning, [Nausea, Fatigue])
]
```

### Step 3: Implement the Logic

Next, we will implement the logic for diagnosing ailments based on the input symptoms. We will create a function that checks the rules against the provided symptoms.

**Example:**

```haskell
diagnose :: [Symptom] -> [Ailment]
diagnose symptoms = [ailment | (ailment, ruleSymptoms) <- rules, all (`elem` symptoms) ruleSymptoms]

-- Function to provide recommendations based on diagnosed ailments
recommend :: [Ailment] -> String
recommend ailments
    | null ailments = "No diagnosis found. Please consult a doctor."
    | otherwise = "Possible ailments: " ++ unwords (map show ailments)
```

### Step 4: User Interaction

We will create a simple command-line interface to interact with the user. The user will input symptoms, and the system will output possible ailments and recommendations.

**Example:**

```haskell
main :: IO ()
main = do
    putStrLn "Enter your symptoms (cough, fever, headache, fatigue, nausea):"
    input <- getLine
    let symptoms = map read (words input)  -- Convert string input to Symptom data type
    let diagnosedAilments = diagnose symptoms
    putStrLn (recommend diagnosedAilments)
```

### Step 5: Testing the Application

After implementing the application, we need to test it with various inputs to ensure it behaves as expected. We can create test cases for different combinations of symptoms and verify that the correct ailments are diagnosed.

**Example Test Cases:**

1. Input: "cough fatigue" → Output: "Possible ailments: Cold"
2. Input: "fever cough fatigue" → Output: "Possible ailments: Flu"
3. Input: "headache nausea" → Output: "Possible ailments: Migraine"
4. Input: "nausea fatigue" → Output: "Possible ailments: FoodPoisoning"

### Challenges Faced

During the development of the logic-based application, several challenges may arise:

1. **Defining Rules:** Creating a comprehensive set of rules that accurately reflects the relationships between symptoms and ailments can be complex. It requires careful consideration of medical knowledge and common symptoms.
2. **User Input Handling:** Ensuring that user input is correctly parsed and mapped to the appropriate data types can be tricky, especially when dealing with various input formats.
3. **Testing and Validation:** Verifying that the application produces correct diagnoses based on the rules requires thorough testing and validation against real-world scenarios.

### Reflecting on Learning Outcomes

Through this project, you will gain valuable insights into the following areas:

1. **Logical Programming:** Understanding how to represent knowledge and reasoning using logical constructs.
2. **Haskell Programming:** Gaining experience with Haskell's type system, data structures, and functional programming paradigms.
3. **Problem-Solving:** Developing skills in designing and implementing systems that require logical reasoning and inference.

In conclusion, building a logic-based application in Haskell provides a practical opportunity to apply the concepts learned throughout the course. By designing and implementing an expert system, you will deepen your understanding of logical programming and its real-world applications.