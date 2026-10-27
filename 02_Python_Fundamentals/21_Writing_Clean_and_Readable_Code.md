# 21. Writing Clean and Readable Code

## 1. Introduction

**Clean Code** হলো এমন code, যা সঠিকভাবে কাজ করার পাশাপাশি সহজে পড়া, বোঝা, পরীক্ষা এবং maintain করা যায়।

একটি program শুধু কাজ করলেই যথেষ্ট নয়। অন্য developer যেন code পড়ে সহজে বুঝতে পারে, সেটিও গুরুত্বপূর্ণ।

উদাহরণ:

**Unclean Code:**

```python
a=80
b=90
c=(a+b)/2
print(c)
```

**Clean Code:**

```python
first_mark = 80
second_mark = 90

average_mark = (first_mark + second_mark) / 2

print(average_mark)
```

দুটি code-ই একই result দেয়। কিন্তু দ্বিতীয় code-এ variable-এর নাম অর্থপূর্ণ, spacing সুন্দর এবং calculation বোঝা সহজ।

## 2. Why Is Clean Code Important?

Clean code লেখার কয়েকটি গুরুত্বপূর্ণ সুবিধা রয়েছে:

1. **Readability:** Code সহজে পড়া ও বোঝা যায়।
2. **Maintainability:** ভবিষ্যতে code পরিবর্তন করা সহজ হয়।
3. **Debugging:** ভুল খুঁজে বের করা সহজ হয়।
4. **Reusability:** Code-এর অংশ অন্য জায়গায় পুনরায় ব্যবহার করা যায়।
5. **Teamwork:** অন্য developer-এর সঙ্গে কাজ করা সহজ হয়।
6. **Reliability:** পরিষ্কার structure-এর কারণে logic যাচাই ও test করা সহজ হয়।

Professional programming-এ clean code একটি গুরুত্বপূর্ণ অভ্যাস।

## 3. Use Meaningful Variable Names

Variable-এর নাম এমন হওয়া উচিত, যা দেখেই বোঝা যায় সেখানে কী ধরনের data রাখা হয়েছে।

**Bad Example:**

```python
x = 500
y = 5
z = x * y

print(z)
```

**Good Example:**

```python
product_price = 500
quantity = 5

total_price = product_price * quantity

print(total_price)
```

দ্বিতীয় উদাহরণে variable-এর উদ্দেশ্য সহজে বোঝা যায়।

### Naming Tips

- অর্থপূর্ণ নাম ব্যবহার করো।
- প্রয়োজন ছাড়া single-letter name ব্যবহার করো না।
- Variable-এর নামে space ব্যবহার করো না।
- Python-এর keyword variable name হিসেবে ব্যবহার করো না।
- একই variable-এর নাম পুরো program-এ ধারাবাহিকভাবে ব্যবহার করো।

Single-letter name কিছু ক্ষেত্রে গ্রহণযোগ্য, যেমন loop counter `i` অথবা গণিতের ছোট formula-তে `x` ও `y`।

## 4. Follow Python Naming Conventions

Python-এ বিভিন্ন ধরনের identifier-এর জন্য প্রচলিত naming convention রয়েছে।

| Item | Convention | Example |
|---|---|---|
| Variable | `snake_case` | `student_name` |
| Function | `snake_case` | `calculate_total()` |
| Class | `PascalCase` | `StudentRecord` |
| Constant | `UPPER_SNAKE_CASE` | `MAX_ATTEMPTS` |
| Module | সাধারণত ছোট হাতের নাম | `math_utils.py` |

উদাহরণ:

```python
MAX_MARKS = 100


def calculate_percentage(obtained_marks):
    return (obtained_marks / MAX_MARKS) * 100


percentage = calculate_percentage(85)

print(percentage)
```

এখানে variable, function এবং constant-এর নাম প্রচলিত Python convention অনুসরণ করেছে।

মনে রাখবে, Python সাধারণত naming convention সব ক্ষেত্রে বাধ্যতামূলক করে না; এগুলো code consistent ও readable রাখার জন্য ব্যবহৃত হয়।

## 5. Follow Proper Indentation

Python-এ indentation শুধু সৌন্দর্যের জন্য নয়; এটি program structure-এর অংশ।

**Incorrect Example:**

```python
age = 20

if age >= 18:
print("Adult")
```

এখানে `print()`-এর indentation ভুল, তাই `IndentationError` হতে পারে।

**Correct Example:**

```python
age = 20

if age >= 18:
    print("Adult")
```

Python code-এ সাধারণত প্রতি indentation level-এ চারটি space ব্যবহার করা হয়।

### Nested Blocks

```python
marks = 85

if marks >= 80:
    print("Good result")

    if marks >= 90:
        print("Excellent result")
```

এখানে nested `if` block-এর indentation সঠিকভাবে দেখানো হয়েছে।

**Rule:** একই block-এর statement-গুলো একই indentation level-এ রাখবে।

## 6. Use Spaces Properly

সঠিক spacing code পড়তে সহজ করে।

**Bad Example:**

```python
a=10
b=20
result=a+b
print(result)
```

**Good Example:**

```python
a = 10
b = 20

result = a + b

print(result)
```

### Common Spacing Rules

- Assignment operator `=`-এর দুই পাশে space রাখো।
- Binary operator যেমন `+`, `-`, `*`-এর দুই পাশে space রাখো।
- Comma-এর পরে space রাখো।
- Function call-এর নাম ও opening parenthesis-এর মাঝে অপ্রয়োজনীয় space দিও না।
- অপ্রয়োজনীয় blank line দিয়ে code ছড়িয়ে ফেলো না।

উদাহরণ:

```python
print("Hello", "Python")

total = price * quantity
```

Python-এর style guide PEP 8-এ এ ধরনের spacing convention বিস্তারিতভাবে দেওয়া আছে।

## 7. Write Comments When Necessary

Comment code-এর উদ্দেশ্য বা কোনো সিদ্ধান্তের কারণ ব্যাখ্যা করতে সাহায্য করে।

উদাহরণ:

```python
# Calculate the average of three marks
mark1 = 80
mark2 = 85
mark3 = 90

average = (mark1 + mark2 + mark3) / 3

print(average)
```

এখানে comment calculation-এর উদ্দেশ্য বোঝাচ্ছে।

### Avoid Unnecessary Comments

**Unnecessary Comment:**

```python
# Store 10 in age
age = 10
```

এখানে code নিজেই স্পষ্ট। তাই comment খুব বেশি উপকার করছে না।

**Better Comment:**

```python
# Minimum age required for registration
MINIMUM_AGE = 18
```

এই comment constant-টির উদ্দেশ্য ব্যাখ্যা করে।

### Commenting Guidelines

- জটিল logic বা গুরুত্বপূর্ণ decision ব্যাখ্যা করো।
- Code কী করছে, তা একেবারে স্পষ্ট হলে অপ্রয়োজনীয় comment দিও না।
- Code পরিবর্তন করলে comment-ও update করো।
- ভুল বা পুরোনো comment রেখে দিও না।

## 8. Avoid Repeating the Same Code

একই logic বারবার লিখলে code maintain করা কঠিন হয়ে যায়।

এই সমস্যাকে অনেক সময় **Code Duplication** বলা হয়।

**Bad Example:**

```python
price1 = 100
quantity1 = 2
total1 = price1 * quantity1
print(total1)

price2 = 200
quantity2 = 3
total2 = price2 * quantity2
print(total2)
```

**Better Example:**

```python
def calculate_total(price, quantity):
    return price * quantity


print(calculate_total(100, 2))
print(calculate_total(200, 3))
```

দ্বিতীয় উদাহরণে calculation-এর logic একটি function-এ রাখা হয়েছে। ফলে একই logic বারবার লিখতে হয়নি।

তবে ছোট program-এ সবকিছুর জন্য function তৈরি করাও প্রয়োজন নেই। Code পুনরাবৃত্তি কমানোর পাশাপাশি simplicity বজায় রাখা জরুরি।

## 9. Keep Functions Small and Focused

একটি function-এর সাধারণত একটি স্পষ্ট দায়িত্ব থাকা উচিত।

**Less Readable Example:**

```python
def process_student():
    name = "Masum"
    marks = [80, 85, 90]
    average = sum(marks) / len(marks)
    print("Name:", name)
    print("Average:", average)
    print("Result processed")
```

**More Focused Example:**

```python
def calculate_average(marks):
    return sum(marks) / len(marks)


def display_student_result(name, average):
    print("Name:", name)
    print("Average:", average)


student_name = "Masum"
student_marks = [80, 85, 90]

average_mark = calculate_average(student_marks)

display_student_result(student_name, average_mark)
```

দ্বিতীয় উদাহরণে calculation এবং output আলাদা function-এ রাখা হয়েছে।

এর ফলে প্রতিটি function-এর দায়িত্ব সহজে বোঝা যায় এবং প্রয়োজন হলে আলাদাভাবে test করা যায়।

## 10. Use Constants for Fixed Values

যেসব value program-এর মধ্যে স্থির নিয়ম বা configuration হিসেবে ব্যবহৃত হয়, সেগুলোর জন্য meaningful constant ব্যবহার করা যেতে পারে।

**Bad Example:**

```python
obtained_marks = 85
percentage = (obtained_marks / 100) * 100

print(percentage)
```

**Better Example:**

```python
MAX_MARKS = 100
obtained_marks = 85

percentage = (obtained_marks / MAX_MARKS) * 100

print(percentage)
```

এখানে `MAX_MARKS` দেখে বোঝা যায় `100`-এর অর্থ কী।

Python-এ uppercase naming একটি convention; এটি নিজে থেকে variable-কে immutable করে না।

## 11. Avoid Unnecessary Complexity

সহজ code অনেক সময় জটিল code-এর চেয়ে ভালো।

**Less Readable Example:**

```python
age = 20
status = "Adult" if age >= 18 else "Minor"
print(status)
```

এটি আসলে valid Python এবং ছোট expression-এর জন্য ভালোও হতে পারে। কিন্তু নতুনদের কাছে একই logic সাধারণ `if-else` দিয়ে লেখা আরও স্পষ্ট হতে পারে।

**Beginner-Friendly Example:**

```python
age = 20

if age >= 18:
    status = "Adult"
else:
    status = "Minor"

print(status)
```

যেখানে সরল code logic বুঝতে সাহায্য করে, সেখানে অপ্রয়োজনীয় shortcut এড়িয়ে চলবে।

তবে conditional expression বা অন্যান্য advanced feature নিজে থেকেই খারাপ নয়। উপযুক্ত পরিস্থিতিতে এগুলোও clean code-এর অংশ হতে পারে।

## 12. Use Blank Lines to Organize Code

Blank line সম্পর্কিত code-কে আলাদা করে দেখাতে সাহায্য করে।

**Poor Formatting:**

```python
name="Masum"
age=22
marks=[80,85,90]
average=sum(marks)/len(marks)
print(name)
print(age)
print(average)
```

**Improved Formatting:**

```python
name = "Masum"
age = 22
marks = [80, 85, 90]

average = sum(marks) / len(marks)

print("Name:", name)
print("Age:", age)
print("Average:", average)
```

এখানে input data, calculation এবং output আলাদা অংশে সাজানো হয়েছে।

Blank line-এর উদ্দেশ্য code সংগঠিত করা; অতিরিক্ত blank line ব্যবহার করা নয়।

## 13. Use f-Strings for Readable Output

String-এর মধ্যে variable-এর value দেখাতে f-string সাধারণত পরিষ্কার ও সুবিধাজনক।

**Less Readable Example:**

```python
name = "Masum"
age = 22

print("My name is " + name + " and I am " + str(age) + " years old.")
```

**Cleaner Example:**

```python
name = "Masum"
age = 22

print(f"My name is {name} and I am {age} years old.")
```

দ্বিতীয় উদাহরণে output format সহজে পড়া যায়।

## 14. Handle Errors Clearly

User input বা external data নিয়ে কাজ করার সময় সম্ভাব্য error বিবেচনা করা গুরুত্বপূর্ণ।

**Example:**

```python
try:
    age = int(input("Enter your age: "))
except ValueError:
    print("Please enter a valid integer.")
else:
    print(f"Your age is {age}.")
```

এখানে:

- `try` block-এ integer conversion করা হয়েছে।
- `except` block invalid input handle করেছে।
- `else` block তখনই execute হবে, যখন `try` block-এ exception ঘটবে না।

Error handling-এর উদ্দেশ্য হলো প্রত্যাশিত সমস্যাগুলো যথাযথভাবে সামলানো। সব exception লুকিয়ে ফেলা clean code নয়।

## 15. Follow the DRY Principle

**DRY**-এর পূর্ণরূপ হলো **Don't Repeat Yourself**।

এই principle অনুযায়ী একই business rule বা logic অপ্রয়োজনীয়ভাবে একাধিক জায়গায় duplicate করা এড়িয়ে চলা উচিত।

উদাহরণ:

```python
TAX_RATE = 0.05


def calculate_tax(price):
    return price * TAX_RATE


print(calculate_tax(1000))
print(calculate_tax(2000))
```

Tax rate এক জায়গায় define করা হয়েছে। ভবিষ্যতে rate পরিবর্তন করতে হলে একটি জায়গা পরিবর্তন করলেই হবে।

তবে একই রকম দেখতে সব code-ই duplicate logic নয়। অতিরিক্ত abstraction তৈরি না করে প্রয়োজন অনুযায়ী DRY principle অনুসরণ করবে।

## 16. Follow the KISS Principle

**KISS**-এর পূর্ণরূপ হলো **Keep It Simple, Stupid**। এর মূল ধারণা হলো, প্রয়োজনের তুলনায় code অযথা জটিল না করা।

উদাহরণ:

**Unnecessarily Complex:**

```python
number = 10

if number % 2 == 0:
    result = True
else:
    result = False

print(result)
```

**Simpler Version:**

```python
number = 10

result = number % 2 == 0

print(result)
```

দ্বিতীয় code একই কাজ কম statement-এ করে এবং বোঝাও সহজ।

তবে readability বজায় রাখা জরুরি। Code ছোট করার জন্য এমন shortcut ব্যবহার করবে না, যা logic বুঝতে কঠিন করে দেয়।

## 17. Follow PEP 8

**PEP 8** হলো Python code-এর style guide। এটি code-এর formatting এবং consistency সম্পর্কে সুপারিশ দেয়।

গুরুত্বপূর্ণ কিছু guideline:

- Indentation-এর জন্য সাধারণত চারটি space ব্যবহার করা।
- Variable ও function-এর জন্য `snake_case` ব্যবহার করা।
- Class-এর জন্য `PascalCase` ব্যবহার করা।
- প্রয়োজনীয় spacing বজায় রাখা।
- Import statement-গুলো সংগঠিত রাখা।
- অতিরিক্ত দীর্ঘ line এড়িয়ে চলা।
- Code-কে consistent ও readable রাখা।

PEP 8-এর line length guideline অনুযায়ী সাধারণ Python code-এর জন্য সর্বোচ্চ 79 character একটি প্রচলিত recommendation; তবে project-এর নিজস্ব style rule থাকতে পারে।

PEP 8 পড়তে পারো: https://peps.python.org/pep-0008/

### Code Formatting Tools

| Tool | Purpose |
|---|---|
| `Black` | Code format করে |
| `Ruff` | Linting ও বিভিন্ন code-quality check করতে পারে |
| `Flake8` | Style ও কিছু code issue শনাক্ত করতে সাহায্য করে |

এই tool-গুলো code quality উন্নত করতে সাহায্য করে, তবে সব logical bug স্বয়ংক্রিয়ভাবে খুঁজে পাবে—এমন নয়।

## 18. Complete Example: Clean Student Result Program

নিচে clean code-এর কয়েকটি principle একসঙ্গে ব্যবহার করা হয়েছে।

```python
MAX_MARKS = 100


def calculate_average(marks):
    return sum(marks) / len(marks)


def calculate_percentage(average):
    return (average / MAX_MARKS) * 100


def display_result(name, average, percentage):
    print(f"Student Name: {name}")
    print(f"Average Marks: {average:.2f}")
    print(f"Percentage: {percentage:.2f}%")


student_name = input("Enter student name: ").strip()

marks = [
    float(input("Enter first mark: ")),
    float(input("Enter second mark: ")),
    float(input("Enter third mark: "))
]

average_mark = calculate_average(marks)
percentage = calculate_percentage(average_mark)

display_result(student_name, average_mark, percentage)
```

Sample input:

```text
Enter student name: Masum
Enter first mark: 80
Enter second mark: 85
Enter third mark: 90
```

Output:

```text
Student Name: Masum
Average Marks: 85.00
Percentage: 85.00%
```

এই example-এ ব্যবহৃত clean coding practices:

1. Meaningful variable ও function names।
2. Consistent indentation ও spacing।
3. Fixed value-এর জন্য constant।
4. Calculation ও display-এর জন্য আলাদা function।
5. f-string দিয়ে readable output।
6. অপ্রয়োজনীয় code duplication এড়িয়ে চলা।

**Note:** এই উদাহরণে marks-এর valid range এবং invalid numeric input যাচাই করা হয়নি। বাস্তব program-এ প্রয়োজন অনুযায়ী validation ও exception handling যোগ করতে হবে।

## 19. Clean Code Checklist

Code লেখার পরে নিচের checklist ব্যবহার করতে পারো।

- [ ] Variable ও function-এর নাম অর্থপূর্ণ।
- [ ] Indentation consistent।
- [ ] Operators ও commas-এর spacing সঠিক।
- [ ] Code-এর structure সহজে বোঝা যায়।
- [ ] প্রয়োজনীয় জায়গায় comment দেওয়া হয়েছে।
- [ ] অপ্রয়োজনীয় code duplication নেই।
- [ ] Function-গুলোর দায়িত্ব পরিষ্কার।
- [ ] অপ্রয়োজনীয় complexity এড়িয়ে চলা হয়েছে।
- [ ] সম্ভাব্য error ও invalid input বিবেচনা করা হয়েছে।
- [ ] Code চালিয়ে expected output যাচাই করা হয়েছে।

## 20. Practice Exercises

### Exercise 1: Improve Variable Names

নিচের code-টি clean code principle অনুসারে rewrite করো।

```python
a = 500
b = 3
c = a * b
print(c)
```

### Exercise 2: Fix Formatting

```python
name="Masum"
age=22
if age>=18:
 print("Adult")
else:
 print("Minor")
```

Code-টির spacing ও indentation ঠিক করো।

### Exercise 3: Remove Repeated Logic

```python
price1 = 100
quantity1 = 2
print(price1 * quantity1)

price2 = 200
quantity2 = 3
print(price2 * quantity2)
```

একটি function ব্যবহার করে code duplication কমাও।

### Exercise 4: Improve Output

```python
name = "Masum"
department = "CSE"

print("Name: " + name + ", Department: " + department)
```

একটি f-string ব্যবহার করে output দেখাও।

### Exercise 5: Use a Constant

একটি program তৈরি করো, যেখানে `MAX_MARKS = 100` constant ব্যবহার করে percentage হিসাব করা হবে।

### Exercise 6: Improve a Long Program

নাম এবং তিনটি marks input নিয়ে average হিসাব করো। Calculation এবং result display-এর জন্য আলাদা function তৈরি করো।

### Exercise 7: Identify Clean Code Practices

নিচের code-এ কী কী সমস্যা রয়েছে, তা শনাক্ত করো।

```python
x=100
y=5
z=x*y
print("Result is "+str(z))
```

তারপর code-টিকে আরও readable করে লেখো।

## 21. Quick Revision

| Principle | Meaning |
|---|---|
| Clean Code | সহজে পড়া, বোঝা ও maintain করা যায় এমন code |
| Meaningful Naming | Variable ও function-এর উদ্দেশ্য বোঝায় এমন নাম |
| Consistent Indentation | একই block-এ সঠিক ও consistent indentation |
| DRY | অপ্রয়োজনীয় code duplication এড়িয়ে চলা |
| KISS | Code প্রয়োজনের তুলনায় জটিল না করা |
| PEP 8 | Python-এর প্রচলিত style guide |
| Code Reusability | Code পুনরায় ব্যবহার করার সুবিধা |
| Maintainability | Code পরিবর্তন ও রক্ষণাবেক্ষণের সহজতা |
| Readability | Code সহজে পড়া ও বোঝার সুবিধা |

## 22. Chapter Summary

এই topic-এ আমরা শিখেছি:

- Clean code কেন গুরুত্বপূর্ণ।
- Meaningful variable ও function name ব্যবহার করা।
- Python naming conventions অনুসরণ করা।
- সঠিক indentation, spacing এবং blank line ব্যবহার করা।
- প্রয়োজন অনুযায়ী comment ও constant ব্যবহার করা।
- Code duplication কমাতে function ব্যবহার করা।
- Function-এর দায়িত্ব পরিষ্কার রাখা।
- f-string দিয়ে readable output তৈরি করা।
- Error handling-এর মাধ্যমে সম্ভাব্য সমস্যা সামলানো।
- DRY, KISS এবং PEP 8-এর মতো গুরুত্বপূর্ণ guideline অনুসরণ করা।
- Checklist ব্যবহার করে নিজের code review করা।

**সবচেয়ে গুরুত্বপূর্ণ কথা:** ভালো code শুধু সঠিক result দেয় না; এটি এমনভাবে লেখা হয়, যাতে অন্যরাও সহজে বুঝতে ও maintain করতে পারে।

## 23. Next Topic

পরবর্তী ফাইল: [`22_Python_Fundamentals_Practice_Exercises.md`](22_Python_Fundamentals_Practice_Exercises.md)

সেখানে Chapter 02-এর গুরুত্বপূর্ণ বিষয়গুলো নিয়ে beginner-friendly practice problems, coding tasks এবং revision exercises থাকবে।