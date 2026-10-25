# 18. Case Sensitivity and Whitespace in Python

## 1. Introduction

Python-এ code লেখার সময় **Case Sensitivity** এবং **Whitespace**—দুটিই গুরুত্বপূর্ণ।

- **Case Sensitivity:** Uppercase ও lowercase letters-কে আলাদা হিসেবে বিবেচনা করা।
- **Whitespace:** Space, tab এবং newline-এর মতো character, যা code-এর মধ্যে separation বা structure তৈরি করে।

উদাহরণ:

```python
name = "Masum"
Name = "Abdulla"

print(name)
print(Name)
```

Output:

```text
Masum
Abdulla
```

এখানে `name` এবং `Name` দুটি আলাদা variable, কারণ Python case-sensitive।

অন্যদিকে, সঠিক জায়গায় whitespace ব্যবহার করলে code পড়া সহজ হয় এবং কিছু ক্ষেত্রে code-এর অর্থও নির্ধারিত হয়।

## 2. What Is Case Sensitivity?

Case sensitivity হলো uppercase ও lowercase letters-এর মধ্যে পার্থক্য বজায় রাখা।

Python case-sensitive language। অর্থাৎ, `a`, `A` এবং `A`-এর মতো আলাদা capitalization-সহ নামগুলো একই identifier নয়।

উদাহরণ:

```python
name = "Masum"
Name = "Ritu"
NAME = "Hasib"

print(name)
print(Name)
print(NAME)
```

Output:

```text
Masum
Ritu
Hasib
```

এখানে তিনটি variable আলাদা।

## 3. Case Sensitivity in Variables

Python-এ variable name লেখার সময় capitalization ঠিক রাখতে হবে।

উদাহরণ:

```python
student_name = "Masum"

print(student_name)
```

Output:

```text
Masum
```

কিন্তু নিচের code-এ error হবে:

```python
student_name = "Masum"

# print(Student_name)
```

কারণ `student_name` এবং `Student_name` আলাদা identifier। `Student_name` define করা হয়নি।

এটি uncomment করে run করলে সাধারণত `NameError` পাওয়া যাবে।

### Another Example

```python
age = 22
Age = 25

print(age + Age)
```

Output:

```text
47
```

এখানে `age` ও `Age`-এর value আলাদা।

**Best Practice:** একই ধরনের variable name-এ অপ্রয়োজনীয় uppercase ও lowercase variation এড়িয়ে চলো। এতে ভুল কম হবে।

## 4. Case Sensitivity in Functions

Python-এ function name-ও case-sensitive।

উদাহরণ:

```python
print("Hello Python")
```

Output:

```text
Hello Python
```

কিন্তু:

```python
# Print("Hello Python")
```

এটি uncomment করে run করলে `NameError` হবে, কারণ built-in function-এর সঠিক নাম `print()`, `Print()` নয়।

একইভাবে:

```python
def greet():
    print("Hello")

greet()
```

Output:

```text
Hello
```

এখানে `greet()`-এর পরিবর্তে `Greet()` call করলে Python আলাদা identifier হিসেবে বিবেচনা করবে।

## 5. Case Sensitivity in Keywords

Python-এর keywords-এর capitalization-ও ঠিক রাখতে হয়।

উদাহরণ:

```python
if True:
    print("Correct")
```

Output:

```text
Correct
```

কিন্তু:

```python
# If True:
#     print("Incorrect")
```

এটি uncomment করলে `SyntaxError` হবে। কারণ `If` Python-এর keyword নয়; সঠিক keyword হলো `if`।

একইভাবে:

| Correct | Incorrect |
|---|---|
| `if` | `If` |
| `else` | `Else` |
| `for` | `For` |
| `while` | `While` |
| `True` | `true` |
| `False` | `false` |
| `None` | `none` |

মনে রাখবে, `True`, `False` এবং `None` Python-এ নির্দিষ্ট capitalization-সহ ব্যবহৃত হয়।

## 6. Case Sensitivity in Strings

String-এর ভেতরের uppercase ও lowercase character-ও আলাদা।

উদাহরণ:

```python
a = "Python"
b = "python"

print(a == b)
```

Output:

```text
False
```

কারণ `"Python"` এবং `"python"` একই string নয়।

### Case Conversion

String-এর case পরিবর্তন করতে বিভিন্ন method ব্যবহার করা যায়।

```python
text = "Python Programming"

print(text.lower())
print(text.upper())
print(text.title())
```

Output:

```text
python programming
PYTHON PROGRAMMING
Python Programming
```

এখানে:

- `lower()` সব অক্ষর lowercase করে।
- `upper()` সব অক্ষর uppercase করে।
- `title()` প্রতিটি word-এর শুরুতে uppercase করে।

### Case-Insensitive Comparison

দুটি string-এর case উপেক্ষা করে তুলনা করতে চাইলে:

```python
a = "Python"
b = "PYTHON"

print(a.lower() == b.lower())
```

Output:

```text
True
```

এটি সাধারণ English text-এর জন্য কার্যকর। Unicode text-এর আরও নির্ভুল caseless comparison-এর জন্য `casefold()` ব্যবহার করা যেতে পারে।

## 7. What Is Whitespace?

Whitespace হলো এমন character, যা text বা code-এর মধ্যে separation তৈরি করে।

Python-এ গুরুত্বপূর্ণ whitespace-এর উদাহরণ:

- Space
- Tab
- Newline

উদাহরণ:

```python
name = "Masum"
age = 22

print(name)
print(age)
```

এখানে variable declaration-এর মাঝে newline এবং `=` operator-এর চারপাশে space ব্যবহার করা হয়েছে।

Whitespace-এর কিছু ব্যবহার শুধু readability বাড়ায়, আবার কিছু ব্যবহার Python-এর syntax ও execution-এর জন্য গুরুত্বপূর্ণ।

## 8. Spaces Around Operators

Operator-এর চারপাশে space ব্যবহার করলে code পড়া সহজ হয়।

কম readable:

```python
a=10
b=20
result=a+b
```

আরও readable:

```python
a = 10
b = 20
result = a + b
```

দুই ক্ষেত্রেই result একই।

Output:

```text
30
```

Python-এর প্রচলিত style guide, PEP 8, assignment ও arithmetic operator-এর চারপাশে উপযুক্ত spacing ব্যবহারের পরামর্শ দেয়।

### Important Note

সব operator-এর চারপাশে একইভাবে space দিতে হয় না। যেমন function call-এ function name ও opening parenthesis-এর মাঝে সাধারণত space দেওয়া হয় না।

সঠিক:

```python
print("Hello")
```

প্রচলিত style-এর বাইরে:

```python
# print ("Hello")
```

দ্বিতীয় উদাহরণটি Python-এ valid হলেও প্রথমটি প্রচলিত style-এর সঙ্গে বেশি সামঞ্জস্যপূর্ণ।

## 9. Whitespace in Expressions

একই expression-এ কিছু whitespace পরিবর্তন করলেও result পরিবর্তন হয় না।

উদাহরণ:

```python
a = 10 + 5
b = 10+5
c = 10  +  5

print(a, b, c)
```

Output:

```text
15 15 15
```

তবে whitespace এমনভাবে সরানো যাবে না, যাতে token বা operator-এর অর্থ বদলে যায়।

যেমন:

```python
x = 10
```

এটি assignment।

কিন্তু:

```python
# x 10
```

এটি valid assignment statement নয়; `=` অনুপস্থিত।

অর্থাৎ, whitespace-এর স্বাধীনতা আছে, কিন্তু Python-এর syntax rules মানতে হবে।

## 10. Whitespace and Indentation

Python-এ indentation শুধু readability-এর জন্য নয়; এটি code block নির্ধারণ করে।

উদাহরণ:

```python
if True:
    print("Inside block")

print("Outside block")
```

Output:

```text
Inside block
Outside block
```

এখানে indentation-এর কারণে প্রথম `print()` block-এর ভেতরে এবং দ্বিতীয়টি বাইরে।

কিন্তু নিচের code-এ indentation সমস্যা রয়েছে:

```python
# if True:
#     print("First")
#   print("Second")
```

একই block-এর statement-গুলোর indentation level সঠিকভাবে মেলেনি। এটি `IndentationError` তৈরি করতে পারে।

Python-এর প্রচলিত নিয়ম হলো প্রতি indentation level-এ চারটি space ব্যবহার করা।

## 11. Newlines and Statements

Python-এ সাধারণত প্রতিটি statement নতুন line-এ লেখা হয়।

উদাহরণ:

```python
a = 10
b = 20

print(a + b)
```

Output:

```text
30
```

এখানে প্রতিটি statement আলাদা line-এ রয়েছে।

### Multiple Statements on One Line

Python-এ semicolon (`;`) দিয়ে একই line-এ একাধিক simple statement লেখা যায়।

```python
a = 10; b = 20; print(a + b)
```

Output:

```text
30
```

তবে beginner হিসেবে প্রতিটি statement আলাদা line-এ লেখাই ভালো। এতে code পড়া, debugging এবং maintenance সহজ হয়।

### Line Continuation

Parentheses-এর ভেতরে expression একাধিক line-এ লেখা যায়।

```python
total = (
    10
    + 20
    + 30
)

print(total)
```

Output:

```text
60
```

Parentheses, brackets বা braces-এর ভেতরে implicit line continuation ব্যবহার করা যায়।

Backslash (`\`) দিয়েও explicit line continuation করা সম্ভব, তবে সাধারণত parentheses ব্যবহার করাই বেশি readable।

## 12. Blank Lines in Python

Blank line হলো এমন line, যেখানে কোনো visible code নেই।

উদাহরণ:

```python
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

মাঝখানে blank line থাকার কারণে output পরিবর্তিত হয়নি।

Blank lines code-এর আলাদা section বা logical group পৃথক করতে সাহায্য করে।

### Best Practices

- Related statements একসঙ্গে রাখো।
- আলাদা logical section-এর মাঝে প্রয়োজনমতো blank line দাও।
- অপ্রয়োজনীয় অনেক blank line ব্যবহার কোরো না।
- Function ও class-এর মতো top-level definition-এর মাঝে প্রচলিত style অনুসরণ করো।

## 13. Leading and Trailing Whitespace in Strings

String-এর ভেতরে থাকা whitespace string-এর অংশ।

উদাহরণ:

```python
a = "Python"
b = " Python"
c = "Python "

print(a == b)
print(a == c)
```

Output:

```text
False
False
```

এখানে `b`-এর শুরুতে এবং `c`-এর শেষে space রয়েছে। তাই তারা `a`-এর সমান নয়।

### Removing Extra Spaces

String-এর শুরু ও শেষের whitespace সরাতে `strip()` ব্যবহার করা যায়।

```python
name = "  Masum  "

print(name.strip())
```

Output:

```text
Masum
```

আরও দুটি method:

```python
text = "  Python  "

print(text.lstrip())
print(text.rstrip())
```

Output:

```text
Python  
  Python
```

- `lstrip()` শুরু থেকে whitespace সরায়।
- `rstrip()` শেষ থেকে whitespace সরায়।
- `strip()` দুই দিক থেকেই whitespace সরায়।

এগুলো নতুন string return করে; মূল string পরিবর্তন করে না, কারণ Python string immutable।

## 14. Whitespace in User Input

`input()` ব্যবহার করে user-এর কাছ থেকে নেওয়া text-এর শুরু বা শেষে অতিরিক্ত whitespace থাকতে পারে।

উদাহরণ:

```python
name = input("Enter your name: ")

print("Hello", name)
```

User যদি শুরু বা শেষে extra spaces দিয়ে input দেয়, সেগুলো string-এর অংশ হিসেবেই থাকবে।

সমাধান:

```python
name = input("Enter your name: ").strip()

print("Hello", name)
```

এখানে `strip()` input-এর শুরু ও শেষের whitespace সরিয়ে দেয়।

তবে মনে রাখবে, এটি মাঝখানের whitespace সরায় না।

## 15. Whitespace Characters in Strings

String-এর মধ্যে কিছু special whitespace character ব্যবহার করা যায়।

### Newline (`\n`)

```python
print("Hello\nPython")
```

Output:

```text
Hello
Python
```

`\n` নতুন line তৈরি করে।

### Tab (`\t`)

```python
print("Name:\tMasum")
```

Output:

```text
Name:   Masum
```

`\t` একটি tab character তৈরি করে। প্রদর্শিত spacing terminal বা editor অনুযায়ী পরিবর্তিত হতে পারে।

### Carriage Return (`\r`)

```python
print("Hello\rPython")
```

এখানে `\r` line-এর শুরুতে ফিরে যাওয়ার character। Terminal কীভাবে এটি display করবে, তা environment-এর ওপর নির্ভর করে।

**Important:** String-এর ভেতরের `\n` বা `\t` এবং Python source code-এর indentation এক জিনিস নয়।

## 16. Common Mistakes

### Mistake 1: Incorrect Capitalization

```python
# Name = "Masum"
# print(name)
```

এটি uncomment করলে `Name` ও `name` আলাদা identifier হওয়ায় `NameError` হবে।

সঠিক:

```python
name = "Masum"
print(name)
```

### Mistake 2: Incorrect Boolean Capitalization

ভুল:

```python
# is_active = true
```

সঠিক:

```python
is_active = True
```

Python-এ Boolean value-এর সঠিক নাম `True` ও `False`।

### Mistake 3: Assuming String Comparison Ignores Case

```python
print("Python" == "python")
```

Output:

```text
False
```

Case উপেক্ষা করতে চাইলে:

```python
print("Python".lower() == "python".lower())
```

Output:

```text
True
```

### Mistake 4: Forgetting Whitespace in Strings

```python
name = "Masum "
print(name == "Masum")
```

Output:

```text
False
```

শেষের space-টিও string-এর অংশ।

### Mistake 5: Incorrect Indentation

```python
# if True:
# print("Hello")
```

`if` block-এর body indent করা হয়নি।

সঠিক:

```python
if True:
    print("Hello")
```

### Mistake 6: Assuming All Extra Spaces Are Harmless

```python
a = "Hello"
b = " Hello"

print(a == b)
```

Output:

```text
False
```

Source code-এর বাইরে extra space এবং string-এর ভেতরে extra space-এর প্রভাব এক নয়।

## 17. Practical Example: Clean User Input

নিচের example-এ case conversion এবং whitespace handling একসঙ্গে ব্যবহার করা হয়েছে।

```python
name = input("Enter your name: ").strip()
department = input("Enter your department: ").strip()

print("Name:", name.title())
print("Department:", department.upper())
```

ধরি, user input দিয়েছে:

```text
Enter your name:   masum
Enter your department:   cse
```

Output:

```text
Name: Masum
Department: CSE
```

এখানে:

- `strip()` শুরু ও শেষের whitespace সরিয়েছে।
- `title()` নামের প্রথম অক্ষর uppercase করেছে।
- `upper()` department-এর সব অক্ষর uppercase করেছে।

**Note:** `title()` সব ধরনের ব্যক্তিনামের capitalization ঠিকভাবে handle করতে পারে না। বাস্তব application-এ নামের formatting-এর ক্ষেত্রে সতর্ক থাকতে হবে।

## 18. Practice Exercises

### Exercise 1: Case Sensitivity

```python
name = "Masum"
Name = "Ritu"

print(name)
print(Name)
```

Output অনুমান করো এবং ব্যাখ্যা করো কেন দুটি result আলাদা।

### Exercise 2: Find the Error

```python
# age = 22
# print(Age)
```

এখানে কী error হবে এবং কেন?

### Exercise 3: String Comparison

```python
a = "Python"
b = "PYTHON"

print(a == b)
print(a.lower() == b.lower())
```

দুটি result ব্যাখ্যা করো।

### Exercise 4: Whitespace

```python
a = "Hello"
b = " Hello "
c = "Hello"

print(a == b)
print(a == c)
print(b.strip() == c)
```

Output নির্ণয় করো।

### Exercise 5: Indentation

নিচের code-এর indentation ঠিক করো:

```python
# if True:
# print("First")
# print("Second")
```

Expected output:

```text
First
Second
```

### Exercise 6: Clean User Input

একটি program লেখো, যা user-এর নাম input নেবে, শুরু ও শেষের whitespace সরাবে এবং নামটি print করবে।

### Exercise 7: Case Conversion

একটি string `"python programming"` নিয়ে নিচের output তৈরি করো:

```text
PYTHON PROGRAMMING
Python Programming
python programming
```

## 19. Quick Revision

| Concept | Main Point |
|---|---|
| Case Sensitivity | Uppercase ও lowercase আলাদা |
| Variable Names | `name` ও `Name` আলাদা |
| Keywords | `if`, `True`, `False`, `None`-এর capitalization ঠিক রাখতে হয় |
| Whitespace | Space, tab ও newline |
| Indentation | Python-এর code block নির্ধারণ করে |
| Blank Lines | Code-এর section আলাদা করতে সাহায্য করে |
| `strip()` | String-এর দুই পাশের whitespace সরায় |
| `lstrip()` | String-এর শুরু থেকে whitespace সরায় |
| `rstrip()` | String-এর শেষ থেকে whitespace সরায় |
| `lower()` | String-কে lowercase করে |
| `upper()` | String-কে uppercase করে |
| `\n` | String-এ নতুন line তৈরি করে |
| `\t` | String-এ tab character তৈরি করে |

## 20. Chapter Summary

এই topic-এ আমরা শিখেছি:

- Python case-sensitive; uppercase ও lowercase আলাদা।
- Variable, function এবং keyword-এর capitalization সঠিক রাখতে হয়।
- String comparison-এ uppercase ও lowercase আলাদা হিসেবে বিবেচিত হয়।
- `lower()`, `upper()`, `title()` এবং `casefold()` case handling-এ কাজে লাগে।
- Whitespace-এর মধ্যে spaces, tabs এবং newlines রয়েছে।
- Operator-এর চারপাশে সঠিক spacing code readable করে।
- Indentation Python-এর code block নির্ধারণ করে।
- String-এর ভেতরের leading ও trailing spaces value-এর অংশ।
- `strip()`, `lstrip()` এবং `rstrip()` দিয়ে string-এর পাশের whitespace সরানো যায়।

## 21. Next Topic

পরবর্তী ফাইল: [`19_Basic_Input_and_Output.md`](19_Basic_Input_and_Output.md)

সেখানে `input()`, `print()`, user input নেওয়া, type conversion এবং input থেকে output তৈরি করার নিয়ম practical example-সহ আলোচনা করা হবে।