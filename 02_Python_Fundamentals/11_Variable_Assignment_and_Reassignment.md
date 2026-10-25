# 11. Variable Assignment and Reassignment in Python

## 1. Introduction

Python-এ variable assignment হলো কোনো নামের সঙ্গে একটি object যুক্ত করার প্রক্রিয়া। আর **reassignment** হলো একই variable name-এর সঙ্গে পরে অন্য object যুক্ত করা।

উদাহরণ:

```python
age = 22
```

এখানে `age`-এর সঙ্গে integer object `22` যুক্ত হয়েছে।

পরে যদি লিখি:

```python
age = 23
```

তাহলে `age` এখন `23`-কে refer করবে। এটিই reassignment-এর একটি উদাহরণ।

এই topic-এ আমরা শিখব:

- Basic assignment
- Assignment কীভাবে কাজ করে
- Reassignment
- Multiple assignment
- Chained assignment
- Unpacking
- Augmented assignment
- Assignment-এর সাধারণ ভুল ও best practices

## 2. Basic Variable Assignment

Python-এ assignment করার সাধারণ syntax:

```python
variable_name = value
```

উদাহরণ:

```python
name = "Masum"
age = 22
cgpa = 3.95

print(name)
print(age)
print(cgpa)
```

Output:

```text
Masum
22
3.95
```

এখানে `=` operator-এর মাধ্যমে প্রতিটি variable name-এর সঙ্গে একটি object যুক্ত হয়েছে।

### Assignment-এর তিনটি অংশ

```python
marks = 85
```

- `marks` — variable name বা target।
- `=` — assignment operator।
- `85` — value বা expression।

Python প্রথমে ডান পাশের expression evaluate করে, তারপর পাওয়া object-টিকে বাম পাশের target-এর সঙ্গে bind করে।

উদাহরণ:

```python
total = 50 + 30
print(total)
```

Output:

```text
80
```

এখানে `50 + 30` প্রথমে evaluate হয়ে `80` তৈরি করে। তারপর `total` নামটি সেই integer object-কে refer করে।

## 3. Assignment Is Not the Same as Equality

Python-এ `=` এবং `==`-এর কাজ আলাদা।

### Assignment Operator (`=`)

কোনো নামের সঙ্গে object যুক্ত করে।

```python
x = 10
```

### Equality Operator (`==`)

দুটি value সমান কি না পরীক্ষা করে।

```python
x = 10

print(x == 10)
print(x == 20)
```

Output:

```text
True
False
```

| Operator | কাজ | Example |
|---|---|---|
| `=` | Assignment | `x = 10` |
| `==` | Equality comparison | `x == 10` |

**মনে রাখবে:** Assignment statement সাধারণত `=` ব্যবহার করে, কিন্তু condition-এ সমতা পরীক্ষা করতে `==` ব্যবহার করা হয়।

## 4. Reassignment of Variables

একটি variable name-এর সঙ্গে নতুন object যুক্ত করাকে reassignment বলা হয়।

উদাহরণ:

```python
score = 50
print(score)

score = 80
print(score)
```

Output:

```text
50
80
```

প্রথমে `score` নামটি `50`-কে refer করছিল। পরে `80` assign করায় নামটি এখন `80`-কে refer করছে।

### Reassignment with Different Data Types

Python dynamically typed language হওয়ায় একই নাম ভিন্ন type-এর object-কে refer করতে পারে।

```python
value = 100
print(value)

value = "Python"
print(value)

value = 3.14
print(value)
```

Output:

```text
100
Python
3.14
```

এখানে `value` প্রথমে integer, পরে string এবং শেষে floating-point object-কে refer করছে।

তবে professional code-এ একই variable-এর উদ্দেশ্য অকারণে বারবার পরিবর্তন না করাই ভালো। এতে code বোঝা সহজ থাকে।

## 5. Reassignment Does Not Always Change the Original Object

Variable reassignment এবং object modification এক জিনিস নয়।

উদাহরণ:

```python
x = 10
y = x

x = 20

print(x)
print(y)
```

Output:

```text
20
10
```

এখানে:

1. `x` প্রথমে `10`-কে refer করে।
2. `y = x` করার সময় `y`-ও `10`-কে refer করে।
3. পরে `x = 20` করার ফলে `x` নতুন integer object `20`-কে refer করে।
4. `y`-এর binding পরিবর্তিত হয় না; এটি `10`-কেই refer করে।

### Reassignment with a Mutable Object

```python
first = [1, 2, 3]
second = first

first.append(4)

print(first)
print(second)
```

Output:

```text
[1, 2, 3, 4]
[1, 2, 3, 4]
```

এখানে reassignment হয়নি। বরং `first` যে list object-কে refer করছে, সেই object-টিই পরিবর্তন করা হয়েছে। `second` একই object-কে refer করায় পরিবর্তনটি তার মাধ্যমেও দেখা যাচ্ছে।

**মূল পার্থক্য:**

- `x = new_value` — variable-এর binding পরিবর্তন করতে পারে।
- `some_list.append(item)` — বিদ্যমান list object-কে পরিবর্তন করে।

## 6. Multiple Assignment

Python-এ এক statement-এ একাধিক variable-এ value assign করা যায়।

উদাহরণ:

```python
name, age, department = "Masum", 22, "CSE"

print(name)
print(age)
print(department)
```

Output:

```text
Masum
22
CSE
```

এখানে তিনটি variable-এ একসঙ্গে তিনটি value assign করা হয়েছে।

একে multiple assignment বলা হয়।

### Different Types of Values

```python
student_name, marks, is_passed = "Masum", 85, True

print(student_name)
print(marks)
print(is_passed)
```

Output:

```text
Masum
85
True
```

Multiple assignment-এর ক্ষেত্রে সাধারণত target এবং value-এর সংখ্যা মিলতে হবে।

ভুল উদাহরণ:

```python
# Value-এর সংখ্যা target-এর সংখ্যার সঙ্গে মেলে না
# x, y = 10, 20, 30
```

এটি execute করলে `ValueError` হবে, কারণ দুটি target-এর জন্য তিনটি value দেওয়া হয়েছে।

সঠিক:

```python
x, y, z = 10, 20, 30

print(x, y, z)
```

Output:

```text
10 20 30
```

## 7. Assigning the Same Value to Multiple Variables

একই value একাধিক variable-এ assign করতে chained assignment ব্যবহার করা যায়।

উদাহরণ:

```python
a = b = c = 100

print(a)
print(b)
print(c)
```

Output:

```text
100
100
100
```

এখানে `a`, `b` এবং `c`—তিনটি নামই একই integer object `100`-কে refer করছে।

আরেকটি উদাহরণ:

```python
x = y = z = "Python"

print(x)
print(y)
print(z)
```

Output:

```text
Python
Python
Python
```

### Important Note for Mutable Objects

Mutable object-এর ক্ষেত্রে chained assignment ব্যবহার করলে সতর্ক থাকতে হবে।

```python
a = b = []

a.append(10)

print(a)
print(b)
```

Output:

```text
[10]
[10]
```

এখানে `a` এবং `b` একই list object-কে refer করছে। তাই list-এ পরিবর্তন করলে দুটি নামের মাধ্যমেই পরিবর্তনটি দেখা যায়।

যদি দুটি আলাদা list প্রয়োজন হয়, তাহলে আলাদাভাবে তৈরি করো:

```python
a = []
b = []

a.append(10)

print(a)
print(b)
```

Output:

```text
[10]
[]
```

## 8. Swapping Variable Values

Python-এ temporary variable ছাড়াও দুটি variable-এর value swap করা যায়।

### Traditional Method

```python
a = 10
b = 20

temporary = a
a = b
b = temporary

print(a)
print(b)
```

Output:

```text
20
10
```

এখানে `temporary` variable-এর সাহায্যে প্রথম value সাময়িকভাবে রাখা হয়েছে।

### Pythonic Method

Python-এ multiple assignment ব্যবহার করে আরও সহজে swap করা যায়।

```python
a = 10
b = 20

a, b = b, a

print(a)
print(b)
```

Output:

```text
20
10
```

Python আগে ডান পাশের expression-গুলো evaluate করে, তারপর বাম পাশের target-গুলোতে result assign করে। তাই পুরোনো value হারিয়ে না গিয়ে সঠিকভাবে swap হয়।

## 9. Unpacking Assignment

Iterable-এর একাধিক item-কে একাধিক variable-এ আলাদা করে assign করাকে unpacking বলা হয়।

উদাহরণ:

```python
student = ("Masum", 22, "CSE")

name, age, department = student

print(name)
print(age)
print(department)
```

Output:

```text
Masum
22
CSE
```

এখানে tuple-এর তিনটি item আলাদা variable-এ assign হয়েছে।

### Unpacking a List

```python
numbers = [10, 20, 30]

a, b, c = numbers

print(a)
print(b)
print(c)
```

Output:

```text
10
20
30
```

### Using the Starred Target

একটি iterable-এর কিছু item একটি list হিসেবে সংগ্রহ করতে `*` ব্যবহার করা যায়।

```python
numbers = [10, 20, 30, 40, 50]

first, *middle, last = numbers

print(first)
print(middle)
print(last)
```

Output:

```text
10
[20, 30, 40]
50
```

এখানে:

- `first` প্রথম item পেয়েছে।
- `middle` মাঝের item-গুলোকে একটি list হিসেবে পেয়েছে।
- `last` শেষ item পেয়েছে।

Starred target একটি unpacking assignment-এ সাধারণত একটিই থাকতে পারে।

## 10. Augmented Assignment Operators

কোনো variable-এর বর্তমান value-এর ওপর operation করে সেই variable-এ result assign করতে **augmented assignment operator** ব্যবহার করা হয়।

এগুলো code সংক্ষিপ্ত করতে সাহায্য করে।

### 10.1 Addition Assignment (`+=`)

```python
x = 10
x += 5

print(x)
```

Output:

```text
15
```

এটি সাধারণ numeric ক্ষেত্রে নিচের মতো ফল দেয়:

```python
x = x + 5
```

### 10.2 Subtraction Assignment (`-=`)

```python
x = 20
x -= 5

print(x)
```

Output:

```text
15
```

সাধারণ numeric ক্ষেত্রে:

```python
x = x - 5
```

### 10.3 Multiplication Assignment (`*=`)

```python
x = 5
x *= 3

print(x)
```

Output:

```text
15
```

### 10.4 Division Assignment (`/=`)

```python
x = 20
x /= 4

print(x)
```

Output:

```text
5.0
```

Python-এ `/` সাধারণত floating-point division করে।

### 10.5 Floor Division Assignment (`//=`)

```python
x = 17
x //= 5

print(x)
```

Output:

```text
3
```

### 10.6 Modulus Assignment (`%=`)

```python
x = 17
x %= 5

print(x)
```

Output:

```text
2
```

### 10.7 Exponentiation Assignment (`**=`)

```python
x = 2
x **= 3

print(x)
```

Output:

```text
8
```

### Augmented Assignment Operators Summary

| Operator | সাধারণ Numeric Equivalent | Example |
|---|---|---|
| `+=` | `x = x + value` | `x += 5` |
| `-=` | `x = x - value` | `x -= 5` |
| `*=` | `x = x * value` | `x *= 2` |
| `/=` | `x = x / value` | `x /= 2` |
| `//=` | `x = x // value` | `x //= 2` |
| `%=` | `x = x % value` | `x %= 3` |
| `**=` | `x = x ** value` | `x **= 2` |

এগুলো common numeric examples। Mutable object বা custom class-এর ক্ষেত্রে augmented assignment-এর আচরণ সাধারণ assignment-এর মতো নাও হতে পারে।

## 11. Augmented Assignment with Strings and Lists

Augmented assignment শুধু সংখ্যার ক্ষেত্রেই নয়, কিছু অন্যান্য data type-এর সঙ্গেও কাজ করে।

### String Example

```python
message = "Hello"
message += " Python"

print(message)
```

Output:

```text
Hello Python
```

এখানে string concatenation করে নতুন string `message`-এর সঙ্গে assign করা হয়েছে।

### List Example

```python
numbers = [1, 2, 3]
numbers += [4, 5]

print(numbers)
```

Output:

```text
[1, 2, 3, 4, 5]
```

এখানে list-এর মধ্যে নতুন item যুক্ত হয়েছে। List-এর ক্ষেত্রে `+=` সাধারণত বিদ্যমান list-কে পরিবর্তন করে, যা সাধারণ reassignment-এর থেকে আলাদা হতে পারে।

## 12. Assignment Expressions (`:=`)

Python-এ `:=` নামে একটি operator রয়েছে, যাকে **assignment expression operator** বা *walrus operator* বলা হয়।

এটি expression-এর মধ্যে value assign করার পাশাপাশি সেই value-টিকে expression-এর result হিসেবেও ব্যবহার করতে দেয়।

উদাহরণ:

```python
if (length := len("Python")) > 5:
    print(length)
```

Output:

```text
6
```

এখানে:

1. `len("Python")` evaluate হয়ে `6` তৈরি করে।
2. `length := ...` `length`-এর সঙ্গে `6` assign করে এবং expression হিসেবে `6` দেয়।
3. `6 > 5` সত্য হওয়ায় `print(length)` execute হয়।

সাধারণ assignment ও assignment expression-এর পার্থক্য:

```python
length = len("Python")

if length > 5:
    print(length)
```

দুটিই এখানে একই result দেয়।

**Note:** Assignment expression সব জায়গায় সাধারণ `=`-এর বিকল্প নয়। এর নির্দিষ্ট syntax rules আছে। Basic assignment ভালোভাবে শেখার পর এটি ব্যবহার করাই সহজ।

## 13. Assignment and Variable Scope

Variable কোথায় assign করা হচ্ছে, তার ওপর কোন scope-এ সেটি পাওয়া যাবে তা নির্ভর করতে পারে।

উদাহরণ:

```python
name = "Masum"

def show_name():
    name = "Ritu"
    print(name)

show_name()
print(name)
```

Output:

```text
Ritu
Masum
```

Function-এর ভেতরে `name = "Ritu"` একটি local variable তৈরি করেছে। এটি বাইরের `name`-এর binding পরিবর্তন করেনি।

Function-এর ভেতর থেকে global variable-এর binding পরিবর্তন করতে হলে কিছু ক্ষেত্রে `global` keyword প্রয়োজন হয়। এটি পরবর্তী Function chapter-এ বিস্তারিত আলোচনা করা হবে।

## 14. Common Beginner Mistakes

### Mistake 1: Confusing Assignment and Comparison

ভুল:

```python
# if x = 10:
#     print("Equal")
```

সঠিক:

```python
x = 10

if x == 10:
    print("Equal")
```

Output:

```text
Equal
```

### Mistake 2: Wrong Number of Unpacking Targets

ভুল:

```python
# a, b = 10, 20, 30
```

এখানে দুটি target-এর জন্য তিনটি value রয়েছে।

সঠিক:

```python
a, b, c = 10, 20, 30
```

### Mistake 3: Forgetting the Current Value in Augmented Assignment

```python
count = 5
count += 1

print(count)
```

Output:

```text
6
```

`count += 1` আগের value-এর সঙ্গে `1` যোগ করে।

### Mistake 4: Unexpected Shared Mutable Objects

```python
first = []
second = first

second.append(10)

print(first)
```

Output:

```text
[10]
```

কারণ দুটি variable একই list object-কে refer করছে।

### Mistake 5: Using an Uninitialized Variable

```python
# print(total)
```

যদি `total`-এর কোনো accessible binding না থাকে, তাহলে `NameError` হবে।

সঠিক:

```python
total = 0
print(total)
```

## 15. Practical Examples

### Example 1: Updating a Student's Marks

```python
marks = 70

marks += 10
print("After bonus:", marks)

marks -= 5
print("After deduction:", marks)
```

Output:

```text
After bonus: 80
After deduction: 75
```

### Example 2: Swapping Two Values

```python
first_number = 100
second_number = 200

first_number, second_number = second_number, first_number

print(first_number)
print(second_number)
```

Output:

```text
200
100
```

### Example 3: Calculating a Bill

```python
price = 100
quantity = 3

total = price * quantity
total += 20

print("Final bill:", total)
```

Output:

```text
Final bill: 320
```

### Example 4: Unpacking Student Data

```python
student = ("Masum", "CSE", 3.95)

name, department, cgpa = student

print("Name:", name)
print("Department:", department)
print("CGPA:", cgpa)
```

Output:

```text
Name: Masum
Department: CSE
CGPA: 3.95
```

## 16. Practice Exercises

### Exercise 1: Basic Assignment

তিনটি variable তৈরি করো: `name`, `age` এবং `department`। প্রত্যেকটিতে value assign করে print করো।

### Exercise 2: Reassignment

```python
score = 40
score = 70
score = 90

print(score)
```

Output কী হবে? কেন?

### Exercise 3: Multiple Assignment

এক statement-এ `a`, `b` এবং `c`-তে যথাক্রমে `10`, `20` এবং `30` assign করো।

### Exercise 4: Swap Variables

দুটি variable-এর value temporary variable ব্যবহার না করে swap করো।

### Exercise 5: Augmented Assignment

নিচের code-এর final output বের করো।

```python
x = 10
x += 5
x *= 2
x -= 4

print(x)
```

### Exercise 6: Unpacking

```python
student = ("Masum", 22, "CSE")
```

Tuple-এর value-গুলো `name`, `age` এবং `department` variable-এ unpack করো।

### Exercise 7: Shared Reference

```python
a = [1, 2]
b = a
a = [3, 4]

print(a)
print(b)
```

Output কী হবে? কেন?

### Exercise 8: Build a Small Calculator

দুটি number variable-এ রাখো। Assignment এবং augmented assignment ব্যবহার করে যোগ, বিয়োগ ও গুণের result বের করো।

## 17. Quick Revision

| Concept | Example | Meaning |
|---|---|---|
| Assignment | `x = 10` | `x`-এর সঙ্গে object যুক্ত করা |
| Reassignment | `x = 20` | `x`-কে নতুন object-এর সঙ্গে bind করা |
| Multiple assignment | `a, b = 1, 2` | একাধিক target-এ value assign করা |
| Chained assignment | `a = b = 10` | একাধিক নামকে একই object-এর সঙ্গে bind করা |
| Swapping | `a, b = b, a` | দুটি variable-এর binding swap করা |
| Unpacking | `a, b = [1, 2]` | Iterable-এর item আলাদা variable-এ assign করা |
| Augmented assignment | `x += 5` | বর্তমান value-এর ওপর operation করা |
| Assignment expression | `n := len("Python")` | Expression-এর মধ্যে assign করা |

## 18. Chapter Summary

এই topic-এ আমরা শিখেছি:

- `=` operator দিয়ে variable assignment করা হয়।
- `==` operator দিয়ে equality পরীক্ষা করা হয়।
- Reassignment-এর মাধ্যমে একই variable name নতুন object-কে refer করতে পারে।
- Multiple assignment দিয়ে এক statement-এ একাধিক variable assign করা যায়।
- Chained assignment-এ একাধিক নাম একই object-কে refer করতে পারে।
- Tuple বা list-এর item unpacking করে আলাদা variable-এ assign করা যায়।
- `a, b = b, a` ব্যবহার করে সহজে variable swap করা যায়।
- `+=`, `-=`, `*=`, `/=`-এর মতো augmented assignment operators code সংক্ষিপ্ত করে।
- `:=` assignment expression-এর মাধ্যমে expression-এর মধ্যে assignment করা যায়।
- Mutable object-এর reference sharing এবং object modification বুঝতে হবে।

## 19. Next Topic

পরবর্তী ফাইল: [`12_Multiple_Assignment_and_Unpacking.md`](12_Multiple_Assignment_and_Unpacking.md)

এই ফাইলটি মূলত multiple assignment ও unpacking-এর ওপর আরও focused এবং advanced examples দেবে। সেখানে tuple unpacking, starred unpacking, nested unpacking, iterable unpacking এবং common errors নিয়ে বিস্তারিত practice করা হবে।