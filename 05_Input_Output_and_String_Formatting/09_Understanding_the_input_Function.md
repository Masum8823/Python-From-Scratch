# 09. Understanding the `input()` Function

## 1. Introduction

Python-এ `input()` function ব্যবহার করে user-এর কাছ থেকে keyboard-এর মাধ্যমে তথ্য নেওয়া যায়।

যেমন, একটি program user-এর নাম জানতে চাইতে পারে। User নাম লিখলে program সেটি গ্রহণ করে পরবর্তী কাজে ব্যবহার করতে পারে।

### Example

```python
name = input("Enter your name: ")

print("Hello,", name)
```

Sample Output:

```text
Enter your name: Masum
Hello, Masum
```

এখানে:

1. `input()` user-এর কাছ থেকে নাম নিয়েছে।
2. User `Masum` লিখে Enter চাপ দিয়েছে।
3. নামটি `name` variable-এ সংরক্ষিত হয়েছে।
4. `print()` ব্যবহার করে নামটি দেখানো হয়েছে।

**মূল ধারণা:** `input()` দিয়ে তথ্য নেওয়া হয়, আর `print()` দিয়ে তথ্য দেখানো হয়।

## 2. What Is the `input()` Function?

`input()` হলো Python-এর একটি built-in function, যা user-এর কাছ থেকে input গ্রহণ করে।

Built-in function বলতে এমন function বোঝায়, যা Python-এ আগে থেকেই তৈরি করা আছে। এগুলো ব্যবহার করার জন্য আলাদাভাবে import করতে হয় না।

### Syntax

```python
input()
```

অথবা:

```python
input("Prompt message")
```

এখানে `Prompt message` হলো user-কে দেখানো নির্দেশনা বা প্রশ্ন।

### Example 1: Simple Input

```python
name = input()

print(name)
```

Sample Input:

```text
Masum
```

Output:

```text
Masum
```

এখানে `input()`-এর মধ্যে কোনো prompt দেওয়া হয়নি। তাই program input নেওয়ার সময় কোনো নির্দেশনামূলক text দেখায়নি।

### Example 2: Input with a Prompt

```python
name = input("Enter your name: ")

print(name)
```

Sample Output:

```text
Enter your name: Masum
Masum
```

এখানে `"Enter your name: "` হলো prompt। এটি user-কে জানায় কী input দিতে হবে।

## 3. Why Do We Need `input()`?

Input ছাড়া অনেক program শুধু আগে থেকে নির্ধারিত তথ্য নিয়ে কাজ করে। `input()` ব্যবহার করলে user নিজের প্রয়োজন অনুযায়ী তথ্য দিতে পারে।

### Example 1: Fixed Information

```python
name = "Masum"

print("Hello,", name)
```

Output:

```text
Hello, Masum
```

এখানে নাম আগে থেকেই code-এ লেখা আছে।

### Example 2: User-Provided Information

```python
name = input("Enter your name: ")

print("Hello,", name)
```

Sample Output:

```text
Enter your name: Rahim
Hello, Rahim
```

এখানে user নিজের নাম দিতে পারে। অন্য user চাইলে `Karim`, `Nadia` বা অন্য নামও দিতে পারবে।

### Input-এর ব্যবহার

- User-এর নাম, ঠিকানা বা অন্যান্য তথ্য নেওয়া।
- Program-এর জন্য প্রয়োজনীয় data সংগ্রহ করা।
- User-এর পছন্দ অনুযায়ী কাজ করা।
- Interactive application তৈরি করা।
- User-provided information variable-এ রেখে পরবর্তী কাজে ব্যবহার করা।

## 4. How Does `input()` Work?

`input()` function কীভাবে কাজ করে, তা ধাপে ধাপে বোঝা যাক।

### Example

```python
name = input("Enter your name: ")

print("Welcome,", name)
```

Sample Interaction:

```text
Enter your name: Masum
Welcome, Masum
```

### Working Steps

**Step 1: Prompt Display**

```python
input("Enter your name: ")
```

Python user-কে `Enter your name: ` দেখায়।

**Step 2: Wait for User Input**

Program user-এর input-এর জন্য অপেক্ষা করে। User keyboard দিয়ে তথ্য লিখে Enter চাপ দেয়।

**Step 3: Receive Input**

User যদি `Masum` লেখে, তাহলে `input()` string `"Masum"` return করে।

**Step 4: Store the Value**

```python
name = input("Enter your name: ")
```

`=` operator-এর মাধ্যমে পাওয়া value `name` variable-এ রাখা হয়।

**Step 5: Display the Result**

```python
print("Welcome,", name)
```

এখানে program user-এর দেওয়া নাম ব্যবহার করে greeting দেখায়।

## 5. Understanding the Prompt Message

`input()`-এর ভেতরে দেওয়া prompt user-কে input সম্পর্কে নির্দেশনা দেয়।

### Example 1: Name

```python
name = input("Enter your name: ")
print(name)
```

Sample Interaction:

```text
Enter your name: Masum
Masum
```

### Example 2: Age

```python
age = input("Enter your age: ")
print("Your age is", age)
```

Sample Interaction:

```text
Enter your age: 22
Your age is 22
```

### Example 3: Department

```python
department = input("Enter your department: ")
print("Department:", department)
```

Sample Interaction:

```text
Enter your department: CSE
Department: CSE
```

Prompt message-এর শেষে colon (`:`) এবং space ব্যবহার করা একটি সাধারণ convention। তবে এটি বাধ্যতামূলক নয়।

## 6. `input()` Returns a Value

`input()` function শুধু user-এর লেখা গ্রহণ করে না; এটি সেই input-কে একটি value হিসেবে return করে।

### Example

```python
name = input("Enter your name: ")
```

User যদি `Masum` লেখে, তাহলে কার্যত পাওয়া value হবে:

```python
"Masum"
```

এই value `name` variable-এ সংরক্ষিত হবে।

আরেকটি উদাহরণ:

```python
city = input("Enter your city: ")
```

User যদি `Dhaka` লেখে, তাহলে:

```python
city = "Dhaka"
```

এখানে `"Dhaka"` একটি string।

**মনে রাখবে:** User input দেওয়ার সময় যে text লিখেছে, `input()` সাধারণত সেই text-কে string হিসেবে return করে। User সংখ্যা লিখলেও তা স্বয়ংক্রিয়ভাবে integer বা float হয়ে যায় না।

এই বিষয়টি পরবর্তী ফাইল `10_Input_Returns_a_String.md`-এ বিস্তারিত আলোচনা করা হবে।

## 7. Using `input()` Without Storing the Value

`input()`-এর return value variable-এ না রেখেও ব্যবহার করা যায়।

### Example

```python
print("You entered:", input("Enter something: "))
```

Sample Interaction:

```text
Enter something: Hello
You entered: Hello
```

এখানে user-এর input সরাসরি `print()`-এর মধ্যে ব্যবহার করা হয়েছে।

তবে beginner হিসেবে input আলাদা variable-এ রাখলে code পড়া এবং বোঝা সহজ হয়।

### Recommended Style

```python
message = input("Enter something: ")

print("You entered:", message)
```

এভাবে code-এর প্রতিটি ধাপ স্পষ্ট থাকে।

## 8. Taking Multiple Inputs

একটি program-এ একাধিক `input()` ব্যবহার করে একাধিক তথ্য নেওয়া যায়।

### Example

```python
name = input("Enter your name: ")
department = input("Enter your department: ")
university = input("Enter your university: ")

print("Name:", name)
print("Department:", department)
print("University:", university)
```

Sample Interaction:

```text
Enter your name: Masum
Enter your department: CSE
Enter your university: NUB
Name: Masum
Department: CSE
University: NUB
```

এখানে তিনটি আলাদা input নেওয়া হয়েছে এবং প্রতিটি value আলাদা variable-এ রাখা হয়েছে।

### Working Principle

| Statement | কাজ |
|---|---|
| `name = input(...)` | নাম গ্রহণ করে |
| `department = input(...)` | Department গ্রহণ করে |
| `university = input(...)` | University-এর নাম গ্রহণ করে |
| `print(...)` | তথ্যগুলো দেখায় |

## 9. Using Input in a Simple Program

এবার input ব্যবহার করে একটি সম্পূর্ণ ছোট program তৈরি করা যাক।

### Program: Greeting Application

```python
name = input("Enter your name: ")
city = input("Enter your city: ")

print("Hello,", name)
print("You live in", city)
```

Sample Interaction:

```text
Enter your name: Masum
Enter your city: Dhaka
Hello, Masum
You live in Dhaka
```

এখানে user-এর কাছ থেকে দুটি তথ্য নিয়ে output তৈরি করা হয়েছে।

### Program: Personal Introduction

```python
name = input("Enter your name: ")
department = input("Enter your department: ")
university = input("Enter your university: ")

print("\n--- Introduction ---")
print("My name is", name)
print("I study", department)
print("My university is", university)
```

Sample Interaction:

```text
Enter your name: Masum
Enter your department: CSE
Enter your university: NUB

--- Introduction ---
My name is Masum
I study CSE
My university is NUB
```

এখানে `\n` ব্যবহার করে heading-এর আগে একটি blank line তৈরি করা হয়েছে।

## 10. Understanding the Difference Between `input()` and `print()`

`input()` এবং `print()` দুটিই Python-এর গুরুত্বপূর্ণ built-in function, কিন্তু এদের কাজ আলাদা।

| বিষয় | `input()` | `print()` |
|---|---|---|
| প্রধান কাজ | User-এর কাছ থেকে তথ্য নেওয়া | Output দেখানো |
| তথ্যের প্রবাহ | User → Program | Program → Screen |
| Return value | User-এর input হিসেবে string | `None` |
| Prompt ব্যবহার | করতে পারে | প্রয়োজন অনুযায়ী text দেখায় |
| উদাহরণ | `name = input("Name: ")` | `print(name)` |

### Example

```python
name = input("Enter your name: ")
print("Hello,", name)
```

এখানে প্রথম statement তথ্য গ্রহণ করে এবং দ্বিতীয় statement সেই তথ্য ব্যবহার করে output দেখায়।

## 11. Input and the Program Execution Flow

`input()` function-এর একটি গুরুত্বপূর্ণ বৈশিষ্ট্য হলো এটি user-এর input না পাওয়া পর্যন্ত program-এর execution থামিয়ে রাখে।

### Example

```python
print("Program started")

name = input("Enter your name: ")

print("Program finished")
print("Hello,", name)
```

Sample Interaction:

```text
Program started
Enter your name: Masum
Program finished
Hello, Masum
```

এখানে:

1. প্রথমে `Program started` দেখানো হয়।
2. এরপর program input-এর জন্য অপেক্ষা করে।
3. User input দিয়ে Enter চাপলে execution পরবর্তী statement-এ যায়।
4. শেষে বাকি output দেখানো হয়।

এই আচরণকে synchronous input বলা যায়: input গ্রহণ সম্পন্ন হওয়ার পর পরবর্তী statement চলে।

## 12. Common Mistakes When Using `input()`

### Mistake 1: Input-এর Value Store না করা

```python
input("Enter your name: ")
print(name)
```

এখানে `name` আগে define করা না থাকলে `NameError` হবে। Input নেওয়া হয়েছে, কিন্তু value-টি `name` variable-এ রাখা হয়নি।

সঠিক code:

```python
name = input("Enter your name: ")
print(name)
```

### Mistake 2: Variable-এর নাম ভুল লেখা

```python
name = input("Enter your name: ")
print(nam)
```

এখানে `nam` এবং `name` আলাদা identifier। `nam` define করা না থাকলে `NameError` হবে।

সঠিক code:

```python
name = input("Enter your name: ")
print(name)
```

### Mistake 3: Prompt-কে User Input মনে করা

```python
name = input("Enter your name: ")
```

এখানে `"Enter your name: "` হলো prompt, user-এর দেওয়া input নয়।

User যদি `Masum` লেখে, তাহলে `name`-এর value হবে `"Masum"`।

### Mistake 4: Input স্বয়ংক্রিয়ভাবে Number হয়ে যায় মনে করা

```python
age = input("Enter your age: ")
print(age)
```

User যদি `22` লেখে, তাহলে `age`-এর value হবে string `"22"`; integer `22` নয়।

এই কারণে পরবর্তীতে arithmetic করতে চাইলে type conversion প্রয়োজন হতে পারে। সেটি পরের ফাইলগুলোতে শেখা হবে।

### Mistake 5: Enter না চাপা

```python
name = input("Enter your name: ")
```

Prompt দেখানোর পর user input লিখে Enter না চাপলে program সাধারণত input গ্রহণ সম্পন্ন করতে অপেক্ষা করবে।

## 13. Practical Programs

### Program 1: Name and Greeting

```python
name = input("Enter your name: ")

print("Welcome to Python,", name)
```

Sample Interaction:

```text
Enter your name: Masum
Welcome to Python, Masum
```

### Program 2: Collecting Student Information

```python
name = input("Enter your name: ")
student_id = input("Enter your student ID: ")
department = input("Enter your department: ")

print("\n--- Student Information ---")
print("Name:", name)
print("Student ID:", student_id)
print("Department:", department)
```

Sample Interaction:

```text
Enter your name: Masum
Enter your student ID: 1350
Enter your department: CSE

--- Student Information ---
Name: Masum
Student ID: 1350
Department: CSE
```

এখানে student ID-ও string হিসেবে নেওয়া হয়েছে। এটি অনেক ক্ষেত্রে উপযুক্ত, কারণ ID-তে শুরুতে zero থাকতে পারে এবং ID সাধারণত arithmetic করার জন্য নয়।

### Program 3: Simple Question and Answer

```python
favorite_language = input("What is your favorite programming language? ")

print("Your favorite language is", favorite_language)
```

Sample Interaction:

```text
What is your favorite programming language? Python
Your favorite language is Python
```

এখানে user-এর উত্তর program-এর output-এ ব্যবহার করা হয়েছে।

## 14. Practice Exercises

প্রতিটি exercise নিজে সমাধান করার চেষ্টা করো।

### Exercise 1: Take a Name

User-এর কাছ থেকে নাম নাও এবং নামটি print করো।

### Exercise 2: Greeting Program

User-এর নাম নিয়ে নিচের মতো output দেখাও:

```text
Enter your name: Masum
Hello, Masum!
```

### Exercise 3: Collect Two Details

User-এর নাম এবং department নাও। এরপর দুটি তথ্য আলাদা লাইনে দেখাও।

### Exercise 4: Personal Introduction

User-এর নাম, city এবং university-এর নাম নিয়ে একটি ছোট introduction দেখাও।

### Exercise 5: Output Prediction

নিচের code-এ user যদি `Python` লেখে, তাহলে output কী হবে?

```python
language = input("Language: ")
print("Learning", language)
```

### Exercise 6: Find the Error

নিচের code-এর সমস্যাটি খুঁজে বের করো:

```python
name = input("Enter your name: ")
print(nam)
```

### Exercise 7: Multiple Inputs

User-এর নাম, student ID এবং department নিয়ে একটি student information report তৈরি করো।

### Exercise 8: Explain the Difference

`input()` এবং `print()`-এর কাজের মধ্যে দুটি পার্থক্য লেখো।

### Exercise 9: Input Flow

নিচের program-এর execution order ব্যাখ্যা করো:

```python
print("Start")
name = input("Name: ")
print("End")
```

### Exercise 10: Challenge Program

User-এর নাম, favourite programming language এবং learning goal নাও। এরপর সুন্দরভাবে একটি report print করো।

## 15. Practice Answer Key

### Answer 1

```python
name = input("Enter your name: ")
print(name)
```

### Answer 2

```python
name = input("Enter your name: ")
print("Hello,", name + "!")
```

Sample Interaction:

```text
Enter your name: Masum
Hello, Masum!
```

এখানে `name + "!"` দুটি string concatenate করেছে।

### Answer 3

```python
name = input("Enter your name: ")
department = input("Enter your department: ")

print("Name:", name)
print("Department:", department)
```

### Answer 4

```python
name = input("Enter your name: ")
city = input("Enter your city: ")
university = input("Enter your university: ")

print("\n--- Introduction ---")
print("Name:", name)
print("City:", city)
print("University:", university)
```

### Answer 5

User `Python` লিখলে:

```text
Language: Python
Learning Python
```

### Answer 6

সমস্যা হলো variable-এর নাম ভুল লেখা হয়েছে। `name` define করা হয়েছে, কিন্তু `nam` ব্যবহার করা হয়েছে।

সঠিক code:

```python
name = input("Enter your name: ")
print(name)
```

### Answer 7

```python
name = input("Enter your name: ")
student_id = input("Enter your student ID: ")
department = input("Enter your department: ")

print("\n--- Student Report ---")
print("Name:", name)
print("Student ID:", student_id)
print("Department:", department)
```

### Answer 8

1. `input()` user-এর কাছ থেকে তথ্য গ্রহণ করে; `print()` screen-এ তথ্য দেখায়।
2. `input()` সাধারণত user-এর দেওয়া text হিসেবে string return করে; `print()` নিজে `None` return করে।

### Answer 9

1. প্রথমে `Start` print হবে।
2. এরপর `Name: ` prompt দেখিয়ে program input-এর জন্য অপেক্ষা করবে।
3. User input দিয়ে Enter চাপলে পরবর্তী statement চলবে।
4. শেষে `End` print হবে।

### Answer 10

```python
name = input("Enter your name: ")
language = input("Favorite programming language: ")
goal = input("Your learning goal: ")

print("\n--- Learning Profile ---")
print("Name:", name)
print("Favorite Language:", language)
print("Learning Goal:", goal)
```

## 16. Chapter Summary

এই topic-এ আমরা শিখেছি:

1. `input()` হলো Python-এর built-in function।
2. এটি keyboard থেকে user-এর input গ্রহণ করে।
3. `input("Prompt")` ব্যবহার করে user-কে নির্দেশনা দেখানো যায়।
4. `input()`-এর return value variable-এ সংরক্ষণ করা যায়।
5. User input না দেওয়া পর্যন্ত program অপেক্ষা করে।
6. একটি program-এ একাধিক `input()` ব্যবহার করা যায়।
7. `input()` সাধারণত string return করে, user সংখ্যা লিখলেও।
8. Input-এর value variable-এ store না করলে পরে সেটি ব্যবহার করা যাবে না।
9. `input()` এবং `print()`-এর কাজ আলাদা।
10. User-provided data দিয়ে interactive program তৈরি করা যায়।

## 17. Self-Assessment Checklist

- [ ] `input()` function-এর কাজ বুঝি।
- [ ] Prompt message ব্যবহার করতে পারি।
- [ ] Input variable-এ store করতে পারি।
- [ ] একাধিক input নিতে পারি।
- [ ] Input ব্যবহার করে greeting ও report তৈরি করতে পারি।
- [ ] `input()` এবং `print()`-এর পার্থক্য বুঝি।
- [ ] Variable-এর নামের ভুল শনাক্ত করতে পারি।
- [ ] বুঝি যে `input()` সাধারণত string return করে।

**Next Topic:** `10_Input_Returns_a_String.md` — এখানে আমরা বিস্তারিত শিখব কেন `input()`-এ সংখ্যা লিখলেও Python সেটিকে string হিসেবে গ্রহণ করে এবং এর ফলে কী কী বিষয় খেয়াল রাখতে হয়।