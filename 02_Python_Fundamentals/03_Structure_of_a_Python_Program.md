# 03. Structure of a Python Program

## 1. Introduction

একটি Python program হলো এক বা একাধিক instruction-এর সমষ্টি, যা নির্দিষ্ট কোনো কাজ সম্পন্ন করে।

Program লেখার সময় শুধু code লিখলেই হয় না; code-গুলো এমনভাবে সাজাতে হয়, যেন program সহজে বোঝা, চালানো এবং পরিবর্তন করা যায়।

**Program Structure** বলতে একটি program-এর বিভিন্ন অংশ কীভাবে সাজানো ও একসঙ্গে কাজ করে, তা বোঝায়।

একটি সাধারণ Python program-এ থাকতে পারে:

- Comments
- Variables
- Input statements
- Processing বা calculation
- Conditional statements
- Loops
- Functions
- Output statements

তবে প্রতিটি program-এ সব অংশ থাকা বাধ্যতামূলক নয়। Program-এর কাজ অনুযায়ী এর structure পরিবর্তিত হয়।

## 2. A Simple Python Program

প্রথমে একটি সাধারণ program দেখি।

```python
# Calculate the total price

product_price = 100
quantity = 3

total_price = product_price * quantity

print("Total Price:", total_price)
```

Output:

```text
Total Price: 300
```

### Code Explanation

**1. Comment**

```python
# Calculate the total price
```

এই comment-টি program-এর উদ্দেশ্য ব্যাখ্যা করছে। Python সাধারণত comment-কে executable instruction হিসেবে বিবেচনা করে না।

**2. Variables**

```python
product_price = 100
quantity = 3
```

এখানে দুটি variable তৈরি করে তাদের value দেওয়া হয়েছে।

**3. Processing**

```python
total_price = product_price * quantity
```

এখানে product-এর price ও quantity গুণ করে মোট মূল্য বের করা হয়েছে।

**4. Output**

```python
print("Total Price:", total_price)
```

এখানে `print()` ব্যবহার করে ফলাফল দেখানো হয়েছে।

এই program-এর structure হলো: Comment → Variables → Processing → Output।

এটি একটি সহজ উদাহরণ; সব Python program-এর জন্য এই একই structure অনুসরণ করা বাধ্যতামূলক নয়।

## 3. Python Program-এর Execution Order

Python সাধারণত program-এর statements-গুলো source code-এ যেভাবে সাজানো থাকে, সেই অনুযায়ী execute করে। তবে condition, loop, function call এবং অন্যান্য control-flow features execution order পরিবর্তন করতে পারে।

উদাহরণ:

```python
print("First")
print("Second")
print("Third")
```

Output:

```text
First
Second
Third
```

এখানে প্রথমে প্রথম statement, এরপর দ্বিতীয় statement এবং সবশেষে তৃতীয় statement execute হয়েছে।

### Execution Order পরিবর্তন হওয়ার উদাহরণ

```python
age = 20

if age >= 18:
    print("Adult")

print("Program finished")
```

Output:

```text
Adult
Program finished
```

এখানে `if` condition সত্য হওয়ায় `Adult` print হয়েছে। এরপর program-এর পরবর্তী statement execute হয়েছে।

**মনে রাখবে:** Python code-এর execution order বোঝার জন্য প্রতিটি statement কী করছে এবং control flow কীভাবে কাজ করছে, তা বুঝতে হবে।

## 4. Statements কীভাবে সাজানো হয়?

একটি program-এর statements সাধারণত যৌক্তিক ক্রমে সাজানো হয়।

উদাহরণস্বরূপ, কোনো সংখ্যার বর্গ বের করতে চাইলে:

1. সংখ্যাটি নির্ধারণ করতে হবে।
2. সংখ্যাটির square calculate করতে হবে।
3. ফলাফল দেখাতে হবে।

Python code:

```python
number = 5

square = number * number

print("Square:", square)
```

Output:

```text
Square: 25
```

এখানে প্রথমে input value নির্ধারণ করা হয়েছে, এরপর calculation করা হয়েছে এবং সবশেষে output দেখানো হয়েছে।

এই ধরনের logical arrangement program-কে বোঝা সহজ করে।

## 5. Input, Processing এবং Output

অনেক program-কে তিনটি প্রধান অংশে বোঝা যায়:

1. **Input:** প্রয়োজনীয় data গ্রহণ করা।
2. **Processing:** data নিয়ে calculation বা অন্য কাজ করা।
3. **Output:** result দেখানো বা সংরক্ষণ করা।

এই ধারণাটিকে অনেক সময় IPO Model (Input–Process–Output) বলা হয়।

### Example

```python
number1 = 10
number2 = 5

result = number1 + number2

print("Result:", result)
```

Output:

```text
Result: 15
```

এখানে:

| Part | Code | কাজ |
|---|---|---|
| Input/Data | `number1 = 10`, `number2 = 5` | প্রয়োজনীয় value নির্ধারণ |
| Processing | `result = number1 + number2` | দুটি সংখ্যা যোগ |
| Output | `print("Result:", result)` | ফলাফল দেখানো |

এই উদাহরণে value-গুলো code-এর মধ্যে সরাসরি দেওয়া হয়েছে। পরবর্তী topics-এ `input()` function ব্যবহার করে user-এর কাছ থেকে data নেওয়া শিখব।

## 6. Comments ও Documentation-এর অবস্থান

Program-এর গুরুত্বপূর্ণ অংশ ব্যাখ্যা করার জন্য comments ব্যবহার করা যায়।

```python
# Store the student's marks
marks = 85

# Display the marks
print("Marks:", marks)
```

Output:

```text
Marks: 85
```

Comments code-এর উদ্দেশ্য বুঝতে সাহায্য করে।

তবে প্রতিটি line-এর জন্য comment লেখা প্রয়োজন হয় না। Code নিজেই পরিষ্কার হলে অপ্রয়োজনীয় comments এড়িয়ে চলা ভালো।

### Poor Example

```python
# Assign 10 to x
x = 10

# Print x
print(x)
```

এখানে comments-গুলো code যা করছে, ঠিক সেটিই আবার বলছে।

### Better Example

```python
# Minimum marks required to pass
passing_marks = 40

print(passing_marks)
```

এখানে comment-টি একটি value-এর উদ্দেশ্য ব্যাখ্যা করছে।

## 7. Variables ও Calculations-এর অবস্থান

যে data ব্যবহার করতে হবে, সেটি সাধারণত ব্যবহারের আগে তৈরি বা নির্ধারণ করতে হয়।

সঠিক উদাহরণ:

```python
price = 500
discount = 50

final_price = price - discount

print(final_price)
```

Output:

```text
450
```

ভুল উদাহরণ:

```python
final_price = price - discount

price = 500
discount = 50

print(final_price)
```

এখানে `price` ও `discount` ব্যবহারের সময় সেগুলো আগে সংজ্ঞায়িত করা হয়নি। তাই `NameError` হবে।

**মূল ধারণা:** কোনো variable ব্যবহার করার আগে নিশ্চিত হতে হবে যে সেটি বর্তমান execution path-এ সঠিকভাবে তৈরি বা সংজ্ঞায়িত হয়েছে।

## 8. Indentation ও Program Structure

Python-এ indentation code block-এর structure নির্ধারণ করে।

উদাহরণ:

```python
temperature = 35

if temperature > 30:
    print("It is hot")
    print("Drink enough water")

print("Program finished")
```

Output:

```text
It is hot
Drink enough water
Program finished
```

এখানে প্রথম দুটি `print()` statement `if` block-এর ভেতরে রয়েছে। তাই condition সত্য হলে সেগুলো execute হবে।

শেষের `print()` statement block-এর বাইরে থাকায় condition সত্য হোক বা মিথ্যা, statement-টি execute হবে।

### Structure Diagram

```text
Program
│
├── Variable Assignment
│
├── if Statement
│   ├── First print()
│   └── Second print()
│
└── Final print()
```

এখানে diagram-টি code-এর logical structure দেখাচ্ছে।

## 9. Functions দিয়ে Program সাজানো

Program বড় হলে একই কাজের code বারবার না লিখে function ব্যবহার করা যায়।

**Function** হলো নির্দিষ্ট কাজ সম্পন্ন করার জন্য তৈরি reusable block of code।

উদাহরণ:

```python
def greet():
    print("Hello!")
    print("Welcome to Python")

greet()
```

Output:

```text
Hello!
Welcome to Python
```

### Code Explanation

- `def` keyword দিয়ে function সংজ্ঞায়িত করা হয়।
- `greet` হলো function-এর নাম।
- `()` function-এর parameter list নির্দেশ করে; এই উদাহরণে কোনো parameter নেই।
- `:` function body শুরু করে।
- Indented statements function-এর body-এর অংশ।
- `greet()` লিখে function call করা হয়েছে।

Function-এর ভেতরের code সাধারণত function call করার সময় execute হয়। Function সংজ্ঞায়িত করলেই তার body স্বয়ংক্রিয়ভাবে execute হয় না।

বড় program-এ functions ব্যবহার করলে code-কে ছোট, পরিষ্কার এবং reusable অংশে ভাগ করা যায়।

## 10. Program-এর Structure ও File Structure-এর পার্থক্য

এই দুটি বিষয় এক নয়।

### Program Structure

একটি program-এর ভেতরে statements, variables, functions এবং control flow কীভাবে সাজানো হয়েছে, তা বোঝায়।

উদাহরণ:

```python
name = "Masum"
print(name)
```

### File Structure

Project-এর মধ্যে Python files, folders এবং অন্যান্য files কীভাবে সাজানো হয়েছে, তা বোঝায়।

উদাহরণ:

```text
my_python_project/
├── main.py
├── README.md
└── practice.py
```

এখানে `main.py` ও `practice.py` Python files এবং `README.md` project সম্পর্কে তথ্য রাখে।

ছোট project-এ একটি Python file যথেষ্ট হতে পারে। বড় project-এ একাধিক files, packages ও folders ব্যবহার করা হয়।

## 11. একটি ভালো Python Program-এর বৈশিষ্ট্য

একটি ভালো program শুধু সঠিক output দিলেই যথেষ্ট নয়। Code-টি সহজে বোঝা ও maintain করা যায় কি না, সেটিও গুরুত্বপূর্ণ।

### 11.1 Readability

Code সহজে পড়া ও বোঝা যায়।

ভালো উদাহরণ:

```python
student_marks = 85
print(student_marks)
```

তুলনামূলকভাবে দুর্বোধ্য উদাহরণ:

```python
sm = 85
print(sm)
```

দ্বিতীয় উদাহরণটিও valid, কিন্তু `student_marks` নামটি variable-এর উদ্দেশ্য আরও পরিষ্কার করে।

### 11.2 Meaningful Names

Variable ও function-এর জন্য অর্থপূর্ণ নাম ব্যবহার করা উচিত।

```python
total_price = 1200
discount_amount = 100

final_price = total_price - discount_amount

print(final_price)
```

এখানে variable-এর নাম দেখেই বোঝা যায় কোন value কী বোঝাচ্ছে।

### 11.3 Consistent Formatting

একই ধরনের code-এ consistent spacing ও indentation ব্যবহার করা উচিত।

```python
first_number = 10
second_number = 20

total = first_number + second_number
print(total)
```

### 11.4 Avoid Unnecessary Repetition

একই কাজ বারবার করতে হলে উপযুক্ত ক্ষেত্রে function বা loop ব্যবহার করা যায়। এতে code ছোট এবং maintain করা সহজ হয়।

### 11.5 Follow PEP 8

**PEP 8** হলো Python code-এর style guide। এটি naming, indentation, line length এবং formatting-এর মতো বিষয় নিয়ে নির্দেশনা দেয়।

Beginner হিসেবে এখন থেকেই readable code লেখার অভ্যাস তৈরি করা উচিত।

## 12. Common Structural Mistakes

### Mistake 1: Variable ব্যবহারের আগে define না করা

ভুল:

```python
print(student_name)
student_name = "Masum"
```

এখানে `student_name` ব্যবহারের সময় variable-টি আগে সংজ্ঞায়িত করা হয়নি।

সঠিক:

```python
student_name = "Masum"
print(student_name)
```

### Mistake 2: Indentation ভুল করা

ভুল:

```python
if True:
print("Hello")
```

সঠিক:

```python
if True:
    print("Hello")
```

### Mistake 3: Processing-এর আগে প্রয়োজনীয় data না থাকা

ভুল:

```python
total = price * quantity
price = 100
quantity = 2

print(total)
```

সঠিক:

```python
price = 100
quantity = 2

total = price * quantity

print(total)
```

### Mistake 4: অপ্রয়োজনীয়ভাবে সব code একসঙ্গে লেখা

তুলনামূলকভাবে কম readable:

```python
price=100;quantity=2;total=price*quantity;print(total)
```

আরও readable:

```python
price = 100
quantity = 2

total = price * quantity

print(total)
```

একাধিক statement একই লাইনে লেখা কিছু ক্ষেত্রে valid হলেও, beginner হিসেবে আলাদা লাইনে লেখা বেশি পরিষ্কার।

## 13. Practice Exercises

### Exercise 1: Simple Program Structure

একটি program লেখো, যেখানে:

1. দুটি variable-এ দুটি সংখ্যা রাখবে।
2. তাদের যোগফল বের করবে।
3. যোগফল print করবে।

### Exercise 2: Input–Process–Output

একটি rectangle-এর length ও width নির্ধারণ করে area বের করো।

Formula:

```text
Area = Length × Width
```

Python code-এ আলাদা variable ব্যবহার করে calculation করো।

### Exercise 3: Fix the Structure

নিচের code-টির ভুল ঠিক করো:

```python
total = first + second

first = 10
second = 20

print(total)
```

### Exercise 4: Understand Execution Order

নিচের program-এর output অনুমান করো:

```python
print("Start")

number = 10
print(number)

number = 20
print(number)

print("End")
```

তারপর code চালিয়ে তোমার অনুমানের সঙ্গে output মিলিয়ে দেখো।

### Exercise 5: Use a Function

`welcome()` নামে একটি function তৈরি করো, যা দুটি message print করবে। এরপর function-টি call করো।

### Exercise 6: Program Analysis

নিচের program-টির কোন অংশটি data, কোনটি processing এবং কোনটি output, তা চিহ্নিত করো:

```python
price = 200
quantity = 4

total = price * quantity

print("Total:", total)
```

## 14. Chapter Summary

এই topic-এ আমরা শিখেছি:

- Program Structure হলো program-এর বিভিন্ন অংশের arrangement।
- Python সাধারণত statements-গুলো source code-এর ক্রম অনুযায়ী execute করে, তবে control flow এই ক্রম পরিবর্তন করতে পারে।
- অনেক program-কে Input, Processing ও Output দিয়ে বোঝা যায়।
- Variables ব্যবহার করার আগে সেগুলো সঠিকভাবে define করতে হয়।
- Indentation Python-এর code block নির্ধারণ করে।
- Functions ব্যবহার করে code-কে reusable অংশে ভাগ করা যায়।
- Program Structure এবং File Structure আলাদা বিষয়।
- Meaningful names, consistent formatting এবং readability ভালো programming practice-এর অংশ।

## 15. Next Topic

পরবর্তী ফাইল: [`04_Your_First_Python_Program.md`](04_Your_First_Python_Program.md)

এখানে আমরা নিজের হাতে প্রথম Python program তৈরি, save, run এবং output যাচাই করার সম্পূর্ণ প্রক্রিয়া শিখব।
