# 06. Comments in Python

## 1. Introduction to Comments

**Comment** হলো code-এর মধ্যে লেখা এমন text, যা programmer-কে code বুঝতে সাহায্য করে, কিন্তু সাধারণভাবে program-এর executable instruction হিসেবে কাজ করে না।

Comments ব্যবহার করা হয় code-এর উদ্দেশ্য ব্যাখ্যা করতে, গুরুত্বপূর্ণ logic বোঝাতে এবং program maintain করা সহজ করতে।

উদাহরণ:

```python
# Display a welcome message
print("Welcome to Python")
```

Output:

```text
Welcome to Python
```

এখানে `# Display a welcome message` হলো comment। Python এটি সাধারণ executable statement হিসেবে চালায় না। শুধু `print()` statement execute হয়।

## 2. Why Are Comments Important?

Comments কয়েকটি গুরুত্বপূর্ণ কাজে সাহায্য করে।

### 2.1 Explain the Purpose of Code

কোনো code কেন লেখা হয়েছে, তা বোঝাতে comment ব্যবহার করা যায়।

```python
# Store the student's final marks
marks = 85
```

এখানে comment-টি `marks` variable-এর উদ্দেশ্য ব্যাখ্যা করছে।

### 2.2 Improve Code Readability

জটিল logic থাকলে একটি সংক্ষিপ্ত comment code বুঝতে সাহায্য করতে পারে।

```python
# Apply a 10% discount to the original price
original_price = 1000
discount = original_price * 0.10
final_price = original_price - discount

print(final_price)
```

Output:

```text
900.0
```

Comment-টি calculation-এর উদ্দেশ্য ব্যাখ্যা করছে।

### 2.3 Help During Debugging

Code-এর কোনো অংশ সাময়িকভাবে execute না করিয়ে পরীক্ষা করতে comment ব্যবহার করা যায়। এই পদ্ধতিকে অনেক সময় *commenting out* বলা হয়।

```python
print("Program started")

# print("This line is temporarily disabled")

print("Program finished")
```

Output:

```text
Program started
Program finished
```

Comment করা line-টি সাধারণ Python statement হিসেবে execute হয়নি।

### 2.4 Support Teamwork and Maintenance

বড় project-এ একাধিক developer কাজ করতে পারে। প্রয়োজনীয় comments code-এর উদ্দেশ্য ও গুরুত্বপূর্ণ সিদ্ধান্ত বুঝতে সাহায্য করে।

তবে comments যেন code-এর সঙ্গে সামঞ্জস্যপূর্ণ থাকে, তা নিশ্চিত করতে হবে।

## 3. Single-Line Comments

Python-এ single-line comment শুরু করতে `#` symbol ব্যবহার করা হয়।

Syntax:

```python
# This is a comment
```

উদাহরণ:

```python
# Print a greeting
print("Hello, Python!")
```

Output:

```text
Hello, Python!
```

`#`-এর পর থেকে ওই physical line-এর শেষ পর্যন্ত text comment হিসেবে বিবেচিত হয়।

### Another Example

```python
# Student information
name = "Masum"
age = 22

print(name)
print(age)
```

Output:

```text
Masum
22
```

এখানে comment-টি code-এর উদ্দেশ্য বোঝাচ্ছে।

## 4. Inline Comments

**Inline Comment** হলো code statement-এর একই লাইনে লেখা comment।

উদাহরণ:

```python
age = 22  # Student's age
```

এখানে `age = 22` হলো statement এবং `# Student's age` হলো inline comment।

আরেকটি উদাহরণ:

```python
price = 500  # Original product price
quantity = 2  # Number of products

total = price * quantity

print(total)
```

Output:

```text
1000
```

### Inline Comment লেখার নিয়ম

- Comment যেন statement-এর উদ্দেশ্য ব্যাখ্যা করে।
- অপ্রয়োজনীয় inline comments এড়িয়ে চলো।
- সাধারণত code statement-এর পরে অন্তত দুটি space দিয়ে `#` লেখা হয়।
- Comment যেন code-এর readability কমিয়ে না দেয়।

## 5. Comments in Multiple Lines

Python-এ একাধিক লাইনে comment লেখার সবচেয়ে সরাসরি পদ্ধতি হলো প্রতিটি লাইনের শুরুতে `#` ব্যবহার করা।

```python
# This program stores student information.
# It then displays the student's name
# and department.
name = "Masum"
department = "CSE"

print(name)
print(department)
```

Output:

```text
Masum
CSE
```

এভাবে একাধিক লাইনে explanation লেখা যায়।

### Another Example

```python
# Step 1: Store the numbers
first_number = 10
second_number = 20

# Step 2: Calculate the sum
total = first_number + second_number

# Step 3: Display the result
print(total)
```

Output:

```text
30
```

এখানে প্রতিটি logical section-এর আগে comment দিয়ে code-এর ধাপ ব্যাখ্যা করা হয়েছে।

## 6. Are Triple Quotes Multiline Comments?

Python-এ triple quotes ব্যবহার করে multiline string লেখা যায়:

```python
"""
This is a multiline string.
It contains more than one line.
"""
```

এখানে `""" ... """` হলো multiline string, comment syntax নয়।

একইভাবে:

```python
'''
This is also a multiline string.
It uses single quotes in groups of three.
'''
```

এটিও multiline string।

### তাহলে Triple Quotes কেন Comments-এর মতো দেখায়?

যখন কোনো string expression variable-এ assign করা হয় না এবং function call-এর argument হিসেবে ব্যবহার করা হয় না, তখন সেটি অনেক ক্ষেত্রে কোনো visible output ছাড়াই execute হয়। তাই beginners কখনো কখনো triple-quoted string-কে comment হিসেবে ব্যবহার করেন।

কিন্তু এর গুরুত্বপূর্ণ পার্থক্য রয়েছে:

- `#` দিয়ে লেখা comment Python-এর সাধারণ runtime string object নয়।
- Triple-quoted text একটি string literal।
- Module, class বা function-এর প্রথম statement হিসেবে উপযুক্ত string থাকলে সেটি docstring হিসেবে ব্যবহৃত হতে পারে।
- সাধারণ multiline explanation-এর জন্য প্রতিটি লাইনে `#` ব্যবহার করাই স্পষ্ট পদ্ধতি।

## 7. Docstrings কী?

**Docstring** হলো module, function, class বা method-এর উদ্দেশ্য ব্যাখ্যা করার জন্য ব্যবহৃত documentation string।

সাধারণত docstring triple double quotes `""" ... """` দিয়ে লেখা হয়।

উদাহরণ:

```python
def greet():
    """Display a welcome message."""
    print("Welcome to Python")

greet()
```

Output:

```text
Welcome to Python
```

এখানে `"""Display a welcome message."""` হলো function-এর docstring।

Docstring function কী করে, কী input নেয় এবং কী output দেয়—এসব বোঝাতে ব্যবহার করা যায়।

### Docstring-এর আরেকটি উদাহরণ

```python
def add(a, b):
    """
    Return the sum of two numbers.

    Parameters:
        a: The first number.
        b: The second number.

    Returns:
        The sum of a and b.
    """
    return a + b

print(add(10, 20))
```

Output:

```text
30
```

এখানে docstring-টি function-এর উদ্দেশ্য, parameters এবং return value ব্যাখ্যা করছে।

**মনে রাখবে:** Docstring এবং সাধারণ comment এক নয়। Docstring Python-এর documentation mechanism-এর অংশ।

## 8. Comments vs Docstrings

| বিষয় | Comments | Docstrings |
|---|---|---|
| সাধারণ syntax | `#` | সাধারণত `""" ... """` |
| প্রধান উদ্দেশ্য | Code ও logic ব্যাখ্যা করা | Module, function, class বা method document করা |
| অবস্থান | বিভিন্ন জায়গায় লেখা যায় | সংশ্লিষ্ট module, function, class বা method-এর প্রথম statement হিসেবে |
| Runtime string | সাধারণত নয় | হ্যাঁ, string হিসেবে সংরক্ষিত থাকে |
| Documentation tools | সাধারণত সরাসরি docstring-এর বিকল্প নয় | Documentation tools ব্যবহার করতে পারে |

### Example

```python
# Add two numbers
def add(a, b):
    """Return the sum of two numbers."""
    return a + b
```

এখানে:

- `# Add two numbers` হলো comment।
- `"""Return the sum of two numbers."""` হলো docstring।

দুটিই code বুঝতে সাহায্য করে, তবে তাদের ব্যবহার ও ভূমিকা আলাদা।

## 9. Good Comments vs Bad Comments

সব code line-এর জন্য comment লেখার প্রয়োজন নেই। ভালো comment এমন তথ্য দেয়, যা শুধু code দেখে সহজে বোঝা যায় না।

### 9.1 Bad Comment: Repeating the Code

```python
# Store 10 in x
x = 10
```

এখানে comment শুধু code-টি আবার বলছে। এটি তেমন কোনো অতিরিক্ত তথ্য দিচ্ছে না।

আরেকটি উদাহরণ:

```python
# Add a and b
total = a + b
```

সহজ expression-এর ক্ষেত্রে এই comment সাধারণত অপ্রয়োজনীয়।

### 9.2 Good Comment: Explain the Reason

```python
# Keep a small safety margin for rounding differences
final_amount = calculated_amount + 0.01
```

এখানে comment-টি calculation-এর পেছনের উদ্দেশ্য ব্যাখ্যা করছে।

### 9.3 Explain Non-Obvious Logic

```python
# Use a temporary value to avoid overwriting the original data
temporary_value = original_value
```

এখানে comment-টি একটি গুরুত্বপূর্ণ decision-এর কারণ ব্যাখ্যা করছে।

**মূল নিয়ম:** Code কী করছে, তা যদি code থেকেই পরিষ্কার হয়, তাহলে comment দিয়ে একই কথা বারবার লেখার প্রয়োজন নেই। প্রয়োজন হলে code কেন এভাবে কাজ করছে, তা ব্যাখ্যা করো।

## 10. Commenting Out Code

Debugging বা testing-এর সময় কোনো statement সাময়িকভাবে বন্ধ রাখতে comment করা যায়।

উদাহরণ:

```python
print("Step 1")

# print("Step 2")

print("Step 3")
```

Output:

```text
Step 1
Step 3
```

এখানে দ্বিতীয় statement-টি comment করা হয়েছে, তাই সেটি execute হয়নি।

### Multiple Lines Commenting Out

```python
print("Start")

# print("Temporary line 1")
# print("Temporary line 2")

print("End")
```

Output:

```text
Start
End
```

তবে দীর্ঘ সময়ের জন্য অপ্রয়োজনীয় বা পুরোনো code comment করে রেখে দেওয়া ভালো practice নয়। প্রয়োজনীয় পরিবর্তন Git-এর মতো version control system দিয়ে সংরক্ষণ করা যায়।

## 11. Comments and Indentation

Python-এ comments code block-এর মধ্যে বা বাইরে লেখা যায়।

```python
age = 20

if age >= 18:
    # Check whether the person is an adult
    print("Adult")
```

Output:

```text
Adult
```

এখানে comment-টি `if` block-এর ভেতরে লেখা হয়েছে। এটি executable statement নয়।

আরেকটি উদাহরণ:

```python
# Check the user's age
age = 16

if age >= 18:
    print("Adult")
else:
    print("Minor")
```

Output:

```text
Minor
```

Comments লিখলেও code-এর executable statements-গুলোর indentation সঠিক রাখতে হবে।

## 12. Important Rules for Writing Comments

ভালো comments লেখার জন্য নিচের নিয়মগুলো অনুসরণ করো।

1. **Be Clear:** সহজ ও পরিষ্কার ভাষায় লেখো।
2. **Be Relevant:** Code-এর সঙ্গে সম্পর্কিত তথ্য দাও।
3. **Avoid Obvious Comments:** Code যা সরাসরি বোঝায়, তা অকারণে পুনরাবৃত্তি করো না।
4. **Explain Why:** প্রয়োজন হলে সিদ্ধান্তের কারণ ব্যাখ্যা করো।
5. **Keep Comments Updated:** Code পরিবর্তন করলে comments-ও মিলিয়ে দেখো।
6. **Use Proper Indentation:** Code block-এর মধ্যে comment থাকলে indentation consistent রাখো।
7. **Avoid Excessive Comments:** প্রতিটি statement-এর জন্য comment লেখা প্রয়োজন নেই।
8. **Use Docstrings Appropriately:** Function, class এবং module-এর documentation-এর জন্য docstring ব্যবহার করো।

## 13. Common Beginner Mistakes

### Mistake 1: `#` ব্যবহার না করে comment লেখা

ভুল:

```python
This is a comment
print("Hello")
```

এখানে প্রথম লাইনটি valid Python statement নয়। তাই syntax error হবে।

সঠিক:

```python
# This is a comment
print("Hello")
```

### Mistake 2: Multiline Comment ভুলভাবে লেখা

ভুল:

```python
# This is the first line
This is the second line
```

দ্বিতীয় লাইনে `#` নেই, তাই সেটি comment নয়।

সঠিক:

```python
# This is the first line
# This is the second line
```

### Mistake 3: Triple Quotes-কে সব ক্ষেত্রে Comment মনে করা

```python
"""
This is a string literal,
not the same as a # comment.
"""
```

Triple-quoted text একটি string literal। এটিকে সাধারণ multiline comment syntax মনে করা ঠিক নয়।

### Mistake 4: Outdated Comment

```python
# Store the student's age
marks = 85
```

এখানে comment ও variable-এর মধ্যে মিল নেই। এটি বিভ্রান্তি তৈরি করে।

সঠিক:

```python
# Store the student's marks
marks = 85
```

## 14. Practical Examples

### Example 1: Student Information

```python
# Store student information
name = "Masum"
department = "CSE"
marks = 85

# Display student information
print("Name:", name)
print("Department:", department)
print("Marks:", marks)
```

Output:

```text
Name: Masum
Department: CSE
Marks: 85
```

### Example 2: Calculate Rectangle Area

```python
# Store rectangle dimensions
length = 10
width = 5

# Calculate the area
area = length * width

# Display the result
print("Area:", area)
```

Output:

```text
Area: 50
```

### Example 3: Function with a Docstring

```python
def square(number):
    """Return the square of a number."""
    return number * number

print(square(5))
```

Output:

```text
25
```

## 15. Practice Exercises

### Exercise 1: Add Comments

নিচের code-এ উপযুক্ত comments যোগ করো।

```python
name = "Masum"
age = 22

print(name)
print(age)
```

### Exercise 2: Explain a Calculation

Rectangle-এর area বের করার code লেখো এবং প্রতিটি logical section-এর উদ্দেশ্য ব্যাখ্যা করে comments যোগ করো।

### Exercise 3: Fix the Comments

নিচের code-এর comments-গুলো ঠিক করো।

```python
# Store the student's name
marks = 85

# Print the student's age
print(marks)
```

### Exercise 4: Comment Out a Statement

নিচের code পরিবর্তন করে দ্বিতীয় `print()` statement-টি সাময়িকভাবে বন্ধ করো।

```python
print("First")
print("Second")
print("Third")
```

Expected output:

```text
First
Third
```

### Exercise 5: Write a Docstring

`multiply(a, b)` নামে একটি function তৈরি করো, যা দুটি সংখ্যা গুণ করে return করবে। Function-এর উদ্দেশ্য ব্যাখ্যা করার জন্য একটি docstring লেখো।

### Exercise 6: Identify the Difference

নিজের ভাষায় উত্তর দাও:

1. Comment কী?
2. Inline comment কী?
3. `#` কী কাজে লাগে?
4. Docstring কী?
5. Triple-quoted string ও comment-এর পার্থক্য কী?
6. কেন অপ্রয়োজনীয় comments এড়িয়ে চলা উচিত?

## 16. Quick Revision

| Concept | Syntax | Purpose |
|---|---|---|
| Single-line comment | `# Comment` | Code ব্যাখ্যা করা |
| Inline comment | `x = 10  # Explanation` | একই লাইনে ব্যাখ্যা লেখা |
| Multiline comments | একাধিক লাইনে `#` | একাধিক লাইনে explanation |
| Docstring | `"""Description"""` | Module, function বা class document করা |
| Commenting out | `# print("Hello")` | Statement সাময়িকভাবে বন্ধ রাখা |

## 17. Chapter Summary

এই topic-এ আমরা শিখেছি:

- Comments code-এর উদ্দেশ্য বুঝতে সাহায্য করে।
- Python-এ `#` দিয়ে single-line comment লেখা হয়।
- Inline comment statement-এর একই লাইনে লেখা যায়।
- Multiline explanation-এর জন্য একাধিক `#` ব্যবহার করা যায়।
- Triple-quoted text হলো string literal; এটি নিজে থেকে comment syntax নয়।
- Docstring function, class ও module document করতে ব্যবহৃত হয়।
- ভালো comment code-এর উদ্দেশ্য বা গুরুত্বপূর্ণ সিদ্ধান্ত ব্যাখ্যা করে।
- অপ্রয়োজনীয় ও outdated comments code বুঝতে সমস্যা তৈরি করতে পারে।

## 18. Next Topic

পরবর্তী ফাইল: [`07_Statements_and_Expressions.md`](07_Statements_and_Expressions.md)

এখানে আমরা Statement ও Expression-এর পার্থক্য, expression evaluation, assignment, function call এবং Python code কীভাবে value তৈরি করে তা শিখব।
