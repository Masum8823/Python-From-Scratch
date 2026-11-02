# 05. `sep` Parameter in `print()`

## 1. Introduction

Python-এর `print()` function-এ `sep` একটি গুরুত্বপূর্ণ parameter। `sep`-এর পূর্ণরূপ হলো **separator**।

একটি `print()` statement-এ একাধিক object দেওয়া হলে, তাদের মাঝখানে কী বসবে তা `sep` নির্ধারণ করে।

### Example

```python
print("Python", "Java", "C++")
```

Output:

```text
Python Java C++
```

এখানে Python প্রতিটি object-এর মাঝখানে একটি space দিয়েছে। কারণ `sep`-এর default value হলো একটি space (`' '`)।

এখন আমরা separator পরিবর্তন করতে পারি।

```python
print("Python", "Java", "C++", sep="-")
```

Output:

```text
Python-Java-C++
```

এখানে space-এর পরিবর্তে hyphen (`-`) বসেছে।

## 2. Syntax of the `sep` Parameter

`print()` function-এর সাধারণ syntax:

```python
print(*objects, sep=' ', end='\n', file=None, flush=False)
```

এখানে:

- `*objects` হলো যেসব value বা object দেখাতে চাই।
- `sep` নির্ধারণ করে object-গুলোর মাঝখানে কী থাকবে।
- `end` নির্ধারণ করে output-এর শেষে কী থাকবে।

এই topic-এ আমাদের মূল focus হলো `sep`।

### Basic Syntax

```python
print(value1, value2, value3, sep="separator")
```

এখানে `"separator"`-এর জায়গায় নিজের প্রয়োজন অনুযায়ী character বা text লেখা যায়।

উদাহরণ:

```python
print("A", "B", "C", sep=":")
```

Output:

```text
A:B:C
```

## 3. Default Value of `sep`

`sep` উল্লেখ না করলে Python স্বয়ংক্রিয়ভাবে একটি space ব্যবহার করে।

### Example 1

```python
print("I", "am", "learning", "Python")
```

Output:

```text
I am learning Python
```

### Example 2

```python
print(10, 20, 30)
```

Output:

```text
10 20 30
```

### Example 3

```python
name = "Masum"
department = "CSE"

print(name, department)
```

Output:

```text
Masum CSE
```

এই তিনটি উদাহরণেই `sep` দেওয়া হয়নি। তাই default separator ব্যবহৃত হয়েছে।

### Explicitly Using the Default Separator

নিচের দুটি statement একই output দেয়:

```python
print("A", "B", "C")
```

```python
print("A", "B", "C", sep=" ")
```

Output:

```text
A B C
```

**মনে রাখবে:** `sep` না দিলে Python একটি space ব্যবহার করে। তাই প্রয়োজন না থাকলে আলাদাভাবে `sep=" "` লেখার দরকার নেই।

## 4. Using a Hyphen (`-`) as Separator

একাধিক value-এর মাঝে hyphen বসাতে `sep="-"` ব্যবহার করা যায়।

### Example 1: Dates

```python
year = 2026
month = 10
day = 16

print(year, month, day, sep="-")
```

Output:

```text
2026-10-16
```

### Example 2: Joining Words

```python
print("Learn", "Python", "Step", "by", "Step", sep="-")
```

Output:

```text
Learn-Python-Step-by-Step
```

### Example 3: Product Code

```python
category = "IT"
product = "205"
version = "03"

print(category, product, version, sep="-")
```

Output:

```text
IT-205-03
```

এভাবে code, label বা formatted text তৈরি করতে hyphen separator ব্যবহার করা যায়।

## 5. Using a Comma (`,`) as Separator

Value-গুলোর মাঝে comma বসাতে `sep=", "` ব্যবহার করা যায়।

### Example

```python
print("Apple", "Banana", "Mango")
```

Output:

```text
Apple Banana Mango
```

এবার separator পরিবর্তন করি:

```python
print("Apple", "Banana", "Mango", sep=", ")
```

Output:

```text
Apple, Banana, Mango
```

এখানে `", "`-এর মধ্যে একটি comma এবং একটি space রয়েছে।

### Without a Space After the Comma

```python
print("Apple", "Banana", "Mango", sep=",")
```

Output:

```text
Apple,Banana,Mango
```

**পার্থক্য:**

- `sep=", "` → comma-এর পরে space থাকবে।
- `sep=","` → comma-এর পরে space থাকবে না।

## 6. Using a Colon (`:`) as Separator

Colon separator দিয়ে value-গুলোকে আলাদা করা যায়।

### Example 1

```python
print("Hours", "Minutes", "Seconds", sep=":")
```

Output:

```text
Hours:Minutes:Seconds
```

### Example 2: Time Components

```python
hours = 10
minutes = 30
seconds = 45

print(hours, minutes, seconds, sep=":")
```

Output:

```text
10:30:45
```

এখানে `sep` কেবল value-গুলোর মাঝে colon বসিয়েছে। এটি নিজে থেকে কোনো time calculation বা validation করেনি।

## 7. Using a Vertical Bar (`|`) as Separator

Vertical bar (`|`) ব্যবহার করে value-গুলোকে পরিষ্কারভাবে আলাদা করা যায়।

### Example 1

```python
print("Python", "Java", "C++", sep=" | ")
```

Output:

```text
Python | Java | C++
```

### Example 2: Student Information

```python
name = "Masum"
department = "CSE"
cgpa = 3.95

print(name, department, cgpa, sep=" | ")
```

Output:

```text
Masum | CSE | 3.95
```

এটি ছোট report, summary এবং terminal output সাজানোর জন্য কাজে লাগে।

## 8. Using an Empty String as Separator

যদি object-গুলোর মাঝে কোনো character না রাখতে চাও, তাহলে `sep=""` ব্যবহার করতে পারো।

### Example 1

```python
print("Py", "thon", sep="")
```

Output:

```text
Python
```

### Example 2

```python
print("Mas", "um", sep="")
```

Output:

```text
Masum
```

### Example 3

```python
print("10", "20", "30", sep="")
```

Output:

```text
102030
```

এখানে তিনটি আলাদা string পাশাপাশি বসেছে।

**সতর্কতা:** `sep=""` শুধু object-গুলোর মাঝখানের separator সরায়। এটি object-এর ভেতরের character পরিবর্তন করে না।

## 9. Using Text as a Separator

`sep`-এ শুধু একটি character নয়, একাধিক character বা সম্পূর্ণ text-ও দেওয়া যায়।

### Example 1: Arrow Separator

```python
print("Input", "Process", "Output", sep=" -> ")
```

Output:

```text
Input -> Process -> Output
```

### Example 2: Double Colon

```python
print("A", "B", "C", sep="::")
```

Output:

```text
A::B::C
```

### Example 3: Custom Text

```python
print("Masum", "CSE", "NUB", sep=" studies at ")
```

Output:

```text
Masum studies at CSE studies at NUB
```

খেয়াল করো, separator প্রতিটি adjacent object-এর মাঝখানে বসেছে। তাই এখানে `studies at` দুবার এসেছে।

যদি স্বাভাবিক sentence তৈরি করতে চাও, তাহলে অন্য পদ্ধতি ব্যবহার করা ভালো:

```python
name = "Masum"
department = "CSE"
university = "NUB"

print(name, "studies", department, "at", university)
```

Output:

```text
Masum studies CSE at NUB
```

## 10. How Does `sep` Work with Multiple Objects?

ধরা যাক, একটি `print()` statement-এ চারটি object রয়েছে:

```python
print("A", "B", "C", "D", sep="-")
```

Output:

```text
A-B-C-D
```

চারটি object-এর মাঝে মোট তিনটি separator বসেছে।

সাধারণভাবে, \(n\)টি object থাকলে তাদের মাঝে \(n-1\)টি separator বসে, যদি অন্তত একটি object থাকে।

| Object-এর সংখ্যা | Separator-এর সংখ্যা |
|---:|---:|
| 1 | 0 |
| 2 | 1 |
| 3 | 2 |
| 4 | 3 |
| 5 | 4 |

### Example: Four Objects

```python
print(1, 2, 3, 4, sep="---")
```

Output:

```text
1---2---3---4
```

এখানে চারটি object-এর মাঝে তিনবার `---` বসেছে।

## 11. `sep` Does Not Change the Objects

`sep` শুধু output-এর সময় object-গুলোর মাঝখানে separator বসায়। এটি variable-এর value পরিবর্তন করে না।

### Example

```python
a = "Hello"
b = "Python"

print(a, b, sep="-")

print(a)
print(b)
```

Output:

```text
Hello-Python
Hello
Python
```

প্রথম `print()`-এ hyphen দেখা গেলেও `a` এবং `b`-এর value অপরিবর্তিত রয়েছে।

অর্থাৎ, `sep` দিয়ে output সাজানো যায়, কিন্তু variable-এর মধ্যে থাকা data পরিবর্তন হয় না।

## 12. `sep` Works Between Objects, Not Inside Objects

এটি খুব গুরুত্বপূর্ণ একটি নিয়ম।

### Example 1

```python
print("Hello World", "Python", sep="-")
```

Output:

```text
Hello World-Python
```

এখানে `"Hello World"`-এর ভেতরের space অপরিবর্তিত আছে। Hyphen শুধু প্রথম object এবং দ্বিতীয় object-এর মাঝে বসেছে।

### Example 2

```python
name = "Abdulla Masum"

print(name, "CSE", sep="-")
```

Output:

```text
Abdulla Masum-CSE
```

`name` variable-এর ভেতরের space-টি পরিবর্তন হয়নি।

**মূল নিয়ম:** `sep` object-এর ভেতরের text নয়, object-গুলোর মধ্যবর্তী অংশ নিয়ন্ত্রণ করে।

## 13. Combining `sep` with Calculations

Calculation-এর result-ও অন্য value-এর সঙ্গে custom separator দিয়ে print করা যায়।

### Example 1: Addition

```python
a = 10
b = 20

print(a, b, a + b, sep=" | ")
```

Output:

```text
10 | 20 | 30
```

### Example 2: Rectangle

```python
length = 10
width = 5
area = length * width

print(length, width, area, sep=" -> ")
```

Output:

```text
10 -> 5 -> 50
```

### Example 3: Marks

```python
math = 80
english = 90
science = 85

total = math + english + science

print(math, english, science, total, sep=" | ")
```

Output:

```text
80 | 90 | 85 | 255
```

এখানে `sep` শুধু value-গুলোকে আলাদা করেছে; calculation-এর কাজ করেছে arithmetic operator।

## 14. Combining `sep` and `end`

`sep` এবং `end` একসঙ্গে ব্যবহার করা যায়, কিন্তু তাদের কাজ আলাদা।

- `sep`: একটি `print()` call-এর object-গুলোর মাঝখানে বসে।
- `end`: সেই `print()` call-এর output-এর শেষে বসে।

### Example

```python
print("Python", "Java", sep="-", end=" | ")
print("C++", "JavaScript", sep="-")
```

Output:

```text
Python-Java | C++-JavaScript
```

প্রথম `print()`-এর object-গুলোর মাঝে hyphen এবং output-এর শেষে ` | ` বসেছে। দ্বিতীয় `print()`-এও hyphen separator ব্যবহৃত হয়েছে।

## 15. Common Mistakes

### Mistake 1: `sep`-এর value string হিসেবে না লেখা

সঠিক:

```python
print("A", "B", sep="-")
```

Output:

```text
A-B
```

`sep`-এর value সাধারণত string হিসেবে দেওয়া হয়। যেমন `"-"`, `", "` বা `" | "`।

### Mistake 2: `sep`-কে প্রথম object-এর আগে বসানোর parameter মনে করা

```python
print("A", "B", sep="-")
```

Output:

```text
A-B
```

এখানে output `-A-B` নয়। কারণ `sep` শুরুতে বা শেষে বসে না; এটি object-গুলোর মাঝখানে বসে।

### Mistake 3: একটি object-এর ভেতরের space সরানোর জন্য `sep` ব্যবহার করা

```python
print("Hello World", sep="-")
```

Output:

```text
Hello World
```

এখানে মাত্র একটি object রয়েছে। তাই object-এর ভেতরের space-এর ওপর `sep`-এর কোনো প্রভাব নেই।

### Mistake 4: `sep` দিলে সব output-এর separator পরিবর্তন হবে মনে করা

```python
print("A", "B", sep="-")
print("C", "D")
```

Output:

```text
A-B
C D
```

প্রতিটি `print()` call-এর parameter আলাদাভাবে নির্ধারিত হয়।

### Mistake 5: `sep` ও `end`-কে এক মনে করা

```python
print("A", "B", sep="-", end="!")
```

Output:

```text
A-B!
```

এখানে `-` মাঝখানে এবং `!` শেষে বসেছে।

## 16. Practical Programs

### Program 1: Date Format

```python
day = 16
month = 10
year = 2026

print(day, month, year, sep="/")
```

Output:

```text
16/10/2026
```

এই উদাহরণটি separator-এর ব্যবহার দেখায়। বাস্তব date formatting-এর জন্য Python-এর `datetime` module এবং প্রয়োজন অনুযায়ী zero-padding ব্যবহার করা ভালো।

### Program 2: Student Report

```python
name = "Masum"
department = "CSE"
semester = 9
cgpa = 3.95

print(name, department, semester, cgpa, sep=" | ")
```

Output:

```text
Masum | CSE | 9 | 3.95
```

### Program 3: Product Information

```python
product = "Keyboard"
price = 1200
quantity = 2
total = price * quantity

print(product, price, quantity, total, sep=" -> ")
```

Output:

```text
Keyboard -> 1200 -> 2 -> 2400
```

### Program 4: IPO Flow

```python
print("Input", "Process", "Output", sep=" -> ")
```

Output:

```text
Input -> Process -> Output
```

## 17. Practice Exercises

প্রথমে নিজে output অনুমান করবে, তারপর code চালিয়ে যাচাই করবে।

### Exercise 1

নিচের output তৈরি করো:

```text
Python-Java-C++
```

### Exercise 2

নিচের output তৈরি করো:

```text
Dhaka, Bangladesh, Asia
```

### Exercise 3

একটি `print()` statement ব্যবহার করে `10`, `20`, `30`-এর মাঝে ` | ` বসাও।

### Exercise 4

Output কী হবে?

```python
print("A", "B", "C", sep=":")
```

### Exercise 5

Output কী হবে?

```python
print("Py", "thon", sep="")
```

### Exercise 6

Output কী হবে?

```python
print("Hello World", "Python", sep="-")
```

### Exercise 7

Output কী হবে?

```python
print("A", "B", sep="-")
print("C", "D")
```

### Exercise 8

Output কী হবে?

```python
a = 5
b = 10

print(a, b, a + b, sep=" -> ")
```

### Exercise 9

নিচের output তৈরি করো:

```text
Masum studies at NUB
```

### Exercise 10

কোডটি চালানোর পর `name`-এর value কী থাকবে?

```python
name = "Abdulla Masum"
print(name, "CSE", sep="-")
print(name)
```

## 18. Practice Answer Key

### Answer 1

```python
print("Python", "Java", "C++", sep="-")
```

### Answer 2

```python
print("Dhaka", "Bangladesh", "Asia", sep=", ")
```

### Answer 3

```python
print(10, 20, 30, sep=" | ")
```

### Answer 4

```text
A:B:C
```

### Answer 5

```text
Python
```

### Answer 6

```text
Hello World-Python
```

প্রথম object-এর ভেতরের space অপরিবর্তিত রয়েছে।

### Answer 7

```text
A-B
C D
```

প্রথম `print()`-এ custom separator আছে; দ্বিতীয়টিতে default separator ব্যবহৃত হয়েছে।

### Answer 8

```text
5 -> 10 -> 15
```

### Answer 9

```python
print("Masum", "studies", "at", "NUB")
```

### Answer 10

`name`-এর value অপরিবর্তিত থাকবে:

```text
Abdulla Masum
```

`sep` শুধু প্রথম output-এ object-গুলোর মাঝে hyphen বসিয়েছে। এটি variable পরিবর্তন করেনি।

## 19. Chapter Summary

এই topic থেকে আমরা শিখেছি:

1. `sep` হলো `print()` function-এর separator parameter।
2. এর default value একটি space (`' '`)।
3. `sep` দিয়ে hyphen, comma, colon, vertical bar বা যেকোনো custom text ব্যবহার করা যায়।
4. `sep=""` দিলে object-গুলোর মাঝে কোনো separator বসে না।
5. \(n\)টি object থাকলে সাধারণত তাদের মাঝে \(n-1\)টি separator বসে।
6. `sep` object-এর ভেতরের text পরিবর্তন করে না।
7. `sep` variable-এর value পরিবর্তন করে না।
8. `sep` এবং `end` একসঙ্গে ব্যবহার করা যায়, তবে তাদের কাজ আলাদা।

## 20. Self-Assessment Checklist

- [ ] `sep`-এর কাজ ও syntax বুঝি।
- [ ] Default separator কী, তা জানি।
- [ ] Custom separator ব্যবহার করতে পারি।
- [ ] একাধিক object-এর মাঝে separator কীভাবে বসে, তা বুঝি।
- [ ] `sep` এবং `end`-এর পার্থক্য বুঝি।
- [ ] `sep` variable-এর value পরিবর্তন করে না—এটি বুঝি।
- [ ] প্রয়োজন অনুযায়ী readable output তৈরি করতে পারি।

**Next Topic:** `06_end_Parameter_in_print.md` — এখানে `end` parameter, newline, same-line output এবং একাধিক `print()` statement-এর আচরণ বিস্তারিত শিখব।