# 02. Understanding the `print()` Function

## 1. Introduction

Python-এ `print()` function ব্যবহার করে screen বা terminal-এ text, number, variable-এর value এবং calculation-এর result দেখানো হয়।

উদাহরণ:

```python
print("Hello, World!")
print(100)
print(10 + 20)
```

Output:

```text
Hello, World!
100
30
```

এখানে `print()` তিনটি ভিন্ন ধরনের output দেখিয়েছে—text, number এবং calculation-এর result।

## 2. What Is the `print()` Function?

`print()` হলো Python-এর একটি built-in function। অর্থাৎ, এটি ব্যবহার করার জন্য আলাদাভাবে কোনো library install বা import করতে হয় না।

এর প্রধান কাজ হলো দেওয়া object-গুলোর readable representation text stream-এ লেখা। সাধারণভাবে beginner-দের ক্ষেত্রে এটি terminal বা screen-এ output দেখায়।

### Example

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

এখানে `print(name)` variable-এর value `Masum` দেখিয়েছে এবং `print(age)` value `22` দেখিয়েছে।

**মনে রাখবে:** `print()` variable-এর value দেখায়, variable-এর নাম নয়।

## 3. Syntax of the `print()` Function

`print()`-এর সাধারণ syntax:

```python
print(*objects, sep=' ', end='\n', file=None, flush=False)
```

এখানে কয়েকটি গুরুত্বপূর্ণ parameter রয়েছে।

| Parameter | কাজ |
|---|---|
| `*objects` | যেসব value বা object দেখাতে হবে |
| `sep` | একাধিক object-এর মাঝখানে কী থাকবে |
| `end` | output-এর শেষে কী যোগ হবে |
| `file` | output কোন text stream-এ যাবে |
| `flush` | output stream-এর buffer জোর করে flush করা হবে কি না |

এই chapter-এর শুরুতে আমরা `objects`, `sep` এবং `end`-এর ওপর বেশি গুরুত্ব দেব। `file` ও `flush`-এর প্রয়োজনীয় ব্যবহার পরে শিখতে পারবে।

## 4. Printing a String

String হলো text data। `print()` দিয়ে string দেখাতে quotation marks-এর ভেতরে text লিখতে হয়।

### Example

```python
print("I am learning Python.")
print('Python is easy to start.')
```

Output:

```text
I am learning Python.
Python is easy to start.
```

Python-এ single quotes (`' '`) এবং double quotes (`" "`)—দুটিই string লেখার জন্য ব্যবহার করা যায়।

### Important

```python
print("Python")
```

এখানে quotation marks code-এর অংশ, কিন্তু output-এ quotation marks দেখা যাবে না।

Output:

```text
Python
```

## 5. Printing Numbers

`print()` দিয়ে integer, float এবং অন্যান্য numeric value দেখানো যায়।

### Example

```python
print(25)
print(3.14)
print(-10)
```

Output:

```text
25
3.14
-10
```

Number সরাসরি লিখলে সাধারণত quotation marks লাগে না।

```python
print(25)
print("25")
```

দুটি statement-এর output দেখতে একই রকম:

```text
25
25
```

কিন্তু প্রথমটি integer value, আর দ্বিতীয়টি string value। দেখতে একই হলেও তাদের data type আলাদা।

## 6. Printing Variables

Variable-এর মধ্যে থাকা value দেখাতে variable-এর নাম `print()`-এর ভেতরে লিখতে হয়।

### Example

```python
name = "Masum"
department = "CSE"
cgpa = 3.95

print(name)
print(department)
print(cgpa)
```

Output:

```text
Masum
CSE
3.95
```

এখানে Python variable-এর বর্তমান value দেখিয়েছে।

### Printing a Variable vs a String

```python
name = "Masum"

print(name)
print("name")
```

Output:

```text
Masum
name
```

ব্যাখ্যা:

- `print(name)` — `name` variable-এর value দেখায়।
- `print("name")` — `name` text-টি দেখায়।

**Common rule:** Variable-এর value দেখাতে quotation marks দেবে না; সরাসরি text দেখাতে quotation marks ব্যবহার করবে।

## 7. Printing Expressions and Calculations

`print()`-এর ভেতরে arithmetic expression লিখলে Python প্রথমে expression evaluate করে, তারপর result দেখায়।

### Example

```python
print(10 + 5)
print(20 - 8)
print(6 * 4)
print(20 / 5)
```

Output:

```text
15
12
24
4.0
```

শেষের output `4.0`, কারণ Python 3-এ `/` operator সাধারণত float result দেয়।

### Using Variables in Expressions

```python
a = 10
b = 5

print(a + b)
print(a * b)
print(a ** b)
```

Output:

```text
15
50
100000
```

এখানে `print()`-এর মধ্যে expression evaluate হয়ে result দেখানো হয়েছে।

## 8. Printing Multiple Values

একটি `print()` statement-এর মধ্যে comma দিয়ে একাধিক object দেওয়া যায়।

### Example

```python
name = "Masum"
age = 22
department = "CSE"

print(name, age, department)
```

Output:

```text
Masum 22 CSE
```

সাধারণভাবে `print()` একাধিক object-এর মাঝখানে একটি space যোগ করে।

আরও একটি example:

```python
print("Total marks:", 85)
print("CGPA:", 3.95)
```

Output:

```text
Total marks: 85
CGPA: 3.95
```

এভাবে text এবং variable-এর value একসঙ্গে দেখানো যায়।

## 9. The `sep` Parameter

`sep` হলো separator-এর সংক্ষিপ্ত রূপ। একাধিক object-এর মাঝখানে কী থাকবে, তা নির্ধারণ করে।

এর default value হলো একটি space (`' '`).

### Example 1: Default Separator

```python
print("Python", "Java", "C++")
```

Output:

```text
Python Java C++
```

### Example 2: Using a Hyphen

```python
print("2026", "10", "16", sep="-")
```

Output:

```text
2026-10-16
```

### Example 3: Using a Comma

```python
print("Dhaka", "Bangladesh", sep=", ")
```

Output:

```text
Dhaka, Bangladesh
```

### Example 4: Using No Separator

```python
print("Py", "thon", sep="")
```

Output:

```text
Python
```

এখানে `sep=""` দেওয়ায় object-গুলোর মাঝখানে কোনো character যোগ হয়নি।

**মনে রাখবে:** `sep` শুধু একাধিক object-এর মাঝখানে কাজ করে। একটি object-এর ভেতরের text পরিবর্তন করে না।

## 10. The `end` Parameter

`end` নির্ধারণ করে `print()`-এর output-এর শেষে কী যোগ হবে।

এর default value হলো newline character (`'\n'`)। তাই সাধারণত প্রতিটি `print()`-এর output নতুন লাইনে দেখা যায়।

### Example 1: Default Behavior

```python
print("Hello")
print("Python")
```

Output:

```text
Hello
Python
```

প্রথম `print()` শেষ হওয়ার পর cursor নতুন লাইনে চলে যায়।

### Example 2: Using an Empty String

```python
print("Hello", end="")
print("Python")
```

Output:

```text
HelloPython
```

এখানে প্রথম statement-এর শেষে newline যোগ হয়নি।

### Example 3: Using a Space

```python
print("Hello", end=" ")
print("Python")
```

Output:

```text
Hello Python
```

### Example 4: Using a Symbol

```python
print("Loading", end="...")
print("Done")
```

Output:

```text
Loading...Done
```

**মনে রাখবে:** `end` একটি `print()` call-এর output-এর শেষ নির্ধারণ করে। এর প্রভাব পরের output কোথা থেকে শুরু হবে, সেটিতেও পড়ে।

## 11. Combining `sep` and `end`

একই `print()` statement-এ `sep` ও `end` একসঙ্গে ব্যবহার করা যায়।

### Example

```python
print("Python", "Programming", sep=" - ", end="!")
print(" Welcome")
```

Output:

```text
Python - Programming! Welcome
```

ব্যাখ্যা:

- `sep=" - "` — দুটি object-এর মাঝে ` - ` বসিয়েছে।
- `end="!"` — প্রথম `print()`-এর output-এর শেষে `!` বসিয়েছে।
- পরের `print()`-এর শুরুতে space দেওয়া আছে, তাই output-এ শব্দগুলোর মাঝে space দেখা যাচ্ছে।

## 12. Printing Empty Values

কোনো argument না দিলেও `print()` ব্যবহার করা যায়।

### Example

```python
print()
print("Python")
```

Output:

```text

Python
```

প্রথম `print()` একটি খালি line তৈরি করেছে। এটি output-এর মাঝে ফাঁকা line রাখার জন্য কাজে লাগে।

## 13. The `file` Parameter: Basic Introduction

`print()`-এর `file` parameter দিয়ে output কোন text stream-এ লেখা হবে, তা নির্ধারণ করা যায়।

Default হিসেবে `print()` সাধারণত standard output stream, অর্থাৎ `sys.stdout`-এ লেখে।

### Example

```python
print("Hello, Python!")
```

এখানে `file` উল্লেখ করা হয়নি, তাই default output stream ব্যবহৃত হয়েছে।

পরবর্তীতে file handling শেখার সময় `print()`-এর output একটি file-এ পাঠানোও শিখবে।

## 14. The `flush` Parameter: Basic Introduction

অনেক output stream-এ data সঙ্গে সঙ্গে না দেখিয়ে সাময়িকভাবে buffer-এ রাখা হতে পারে। `flush=True` দিলে `print()` output stream-কে flush করার চেষ্টা করে।

### Example

```python
print("Processing...", flush=True)
```

এটি বিশেষ করে কিছু interactive program বা progress display-তে কাজে লাগতে পারে। তবে সব সাধারণ program-এ `flush=True` ব্যবহার করা প্রয়োজন নেই।

## 15. Understanding the Return Value of `print()`

একটি গুরুত্বপূর্ণ বিষয় হলো, `print()` output দেখালেও সাধারণত কোনো useful value return করে না। এর return value হলো `None`।

### Example

```python
result = print("Hello")
print(result)
```

Output:

```text
Hello
None
```

এখানে:
1. প্রথম `print()` `Hello` দেখিয়েছে।
2. প্রথম `print()`-এর return value `result`-এ রাখা হয়েছে।
3. সেই return value হলো `None`, তাই দ্বিতীয় `print()` `None` দেখিয়েছে।

**মনে রাখবে:** `print()`-এর কাজ output দেখানো; result-কে variable-এ ফেরত দেওয়া নয়।

## 16. Common Beginner Mistakes

### Mistake 1: Variable-এর নাম quotation marks-এর মধ্যে লেখা

```python
name = "Masum"
print("name")
```

Output:

```text
name
```

Variable-এর value দেখতে চাইলে:

```python
print(name)
```

Output:

```text
Masum
```

### Mistake 2: একাধিক value যোগ করার সময় comma-এর কাজ না বোঝা

```python
print("Total:", 10 + 20)
```

Output:

```text
Total: 30
```

এখানে comma আলাদা object-কে `print()`-এ পাঠিয়েছে এবং default separator একটি space দিয়েছে।

### Mistake 3: `sep` ও `end`-কে একই মনে করা

```python
print("A", "B", sep="-", end="!")
```

Output:

```text
A-B!
```

- `sep` object-গুলোর মাঝখানে কাজ করে।
- `end` পুরো output-এর শেষে কাজ করে।

### Mistake 4: `print()`-এর spelling বা capitalization ভুল করা

ভুল:

```python
Print("Hello")
```

সঠিক:

```python
print("Hello")
```

Python case-sensitive।

### Mistake 5: `print()`-কে value conversion মনে করা

```python
age = "22"
print(age)
```

Output:

```text
22
```

এখানে output দেখানো হয়েছে, কিন্তু `age`-এর data type পরিবর্তন হয়নি। এটি এখনও string।

## 17. Practical Examples

### Program 1: Student Information

```python
name = "Masum"
department = "CSE"
university = "NUB"
cgpa = 3.95

print("Name:", name)
print("Department:", department)
print("University:", university)
print("CGPA:", cgpa)
```

Output:

```text
Name: Masum
Department: CSE
University: NUB
CGPA: 3.95
```

### Program 2: Simple Bill

```python
product = "Notebook"
price = 80
quantity = 3

total = price * quantity

print("Product:", product)
print("Price:", price)
print("Quantity:", quantity)
print("Total:", total)
```

Output:

```text
Product: Notebook
Price: 80
Quantity: 3
Total: 240
```

### Program 3: Printing in One Line

```python
print("Name:", "Masum", "|", "Department:", "CSE")
```

Output:

```text
Name: Masum | Department: CSE
```

### Program 4: Creating a Simple Pattern

```python
print("*")
print("**")
print("***")
print("****")
```

Output:

```text
*
**
***
****
```

এখানে প্রতিটি `print()` নতুন লাইনে output দেখিয়েছে।

## 18. Practice Exercises

নিজে code লিখে output অনুমান করার চেষ্টা করো।

### Exercise 1

নিচের code-এর output কী?

```python
print("Hello")
print("World")
```

### Exercise 2

Output কী হবে?

```python
print("A", "B", "C", sep="-")
```

### Exercise 3

Output কী হবে?

```python
print("Python", end=" ")
print("Programming")
```

### Exercise 4

Output কী হবে?

```python
print(10, 20, 30, sep=":", end="!")
```

### Exercise 5

নিচের code-এর output কী?

```python
name = "Masum"
print(name)
print("name")
```

### Exercise 6

একটি `print()` statement ব্যবহার করে নিচের output দেখাও:

```text
Python | Java | C++
```

### Exercise 7

দুটি `print()` statement ব্যবহার করে নিচের output দেখাও:

```text
Hello Python
```

Output-টি যেন দুইটি statement ব্যবহার করেও একই লাইনে আসে।

### Exercise 8

নিচের code-এর output কী এবং কেন?

```python
result = print("Learning")
print(result)
```

## 19. Practice Answer Key

### Answer 1

```text
Hello
World
```

কারণ `print()`-এর default `end` হলো newline।

### Answer 2

```text
A-B-C
```

কারণ `sep="-"` object-গুলোর মাঝে hyphen বসিয়েছে।

### Answer 3

```text
Python Programming
```

কারণ প্রথম `print()`-এর শেষে একটি space দেওয়া হয়েছে, newline নয়।

### Answer 4

```text
10:20:30!
```

কারণ `sep=":"` এবং `end="!"` একসঙ্গে ব্যবহৃত হয়েছে।

### Answer 5

```text
Masum
name
```

প্রথম statement variable-এর value দেখায়; দ্বিতীয়টি literal text দেখায়।

### Answer 6

```python
print("Python", "Java", "C++", sep=" | ")
```

### Answer 7

```python
print("Hello", end=" ")
print("Python")
```

### Answer 8

```text
Learning
None
```

প্রথম `print()` output দেখায় এবং `None` return করে। সেই return value `result`-এ রাখা হয়েছে।

## 20. Chapter Summary

এই topic-এ আমরা শিখেছি:

1. `print()` Python-এর built-in output function।
2. এটি string, number, variable এবং expression-এর result দেখাতে পারে।
3. একাধিক object comma দিয়ে দেওয়া যায়।
4. `sep` object-গুলোর মাঝের separator নির্ধারণ করে।
5. `end` output-এর শেষ নির্ধারণ করে; default হলো newline।
6. `file` output stream নির্বাচন করতে সাহায্য করে।
7. `flush=True` output stream flush করার জন্য ব্যবহৃত হয়।
8. `print()`-এর return value হলো `None`।
9. `print()` output দেখালেও variable-এর data type পরিবর্তন করে না।

## 21. Self-Assessment Checklist

- [ ] `print()`-এর syntax বুঝি।
- [ ] String, number এবং variable print করতে পারি।
- [ ] Expression-এর result দেখাতে পারি।
- [ ] একাধিক object একসঙ্গে print করতে পারি।
- [ ] `sep` ও `end`-এর পার্থক্য বুঝি।
- [ ] একই লাইনে একাধিক output দেখাতে পারি।
- [ ] `print()`-এর return value `None`—এটি বুঝি।
- [ ] `file` ও `flush` parameter-এর basic purpose জানি।

**Next Topic:** `03_Printing_Strings_Numbers_and_Variables.md` — এখানে string, number এবং variable print করার নিয়ম ও তাদের পার্থক্য আরও বেশি example দিয়ে practice করব।