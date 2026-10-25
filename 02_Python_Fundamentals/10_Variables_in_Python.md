# 10. Variables in Python

## 1. Introduction to Variables

Programming-এ **Variable** হলো এমন একটি নাম, যার মাধ্যমে আমরা কোনো value বা object-কে refer করতে পারি।

সহজভাবে বললে, program-এর মধ্যে কোনো data ব্যবহার করার জন্য আমরা একটি নাম দিই। সেই নাম ব্যবহার করে পরে data access বা পরিবর্তন করতে পারি।

উদাহরণ:

```python
name = "Masum"
age = 22
marks = 3.95

print(name)
print(age)
print(marks)
```

Output:

```text
Masum
22
3.95
```

এখানে:

- `name` একটি variable name।
- `"Masum"` একটি string value।
- `age` একটি variable name।
- `22` একটি integer value।
- `marks` একটি variable name।
- `3.95` একটি floating-point value।

Variable ব্যবহার করে data সংরক্ষণ, গণনা, তুলনা এবং program-এর বিভিন্ন অংশে data পুনরায় ব্যবহার করা যায়।

## 2. Why Do We Need Variables?

Variable ছাড়া প্রতিবার একই data সরাসরি code-এ লিখতে হতে পারে। Variable ব্যবহার করলে data-কে একটি অর্থপূর্ণ নাম দিয়ে বারবার ব্যবহার করা যায়।

### Without Variables

```python
print(80)
print(80 + 10)
print(80 + 20)
```

Output:

```text
80
90
100
```

### With Variables

```python
marks = 80

print(marks)
print(marks + 10)
print(marks + 20)
```

Output:

```text
80
90
100
```

দ্বিতীয় উদাহরণে `marks` একবার assign করা হয়েছে এবং পরে একাধিকবার ব্যবহার করা হয়েছে।

যদি marks পরিবর্তন করতে হয়, তাহলে একটি জায়গায় value পরিবর্তন করলেই হবে।

```python
marks = 90

print(marks)
print(marks + 10)
```

Output:

```text
90
100
```

এভাবে variables code-কে flexible, readable এবং maintainable করে।

## 3. Creating a Variable in Python

Python-এ variable ব্যবহার করার আগে সাধারণত assignment-এর মাধ্যমে তার সঙ্গে একটি value যুক্ত করা হয়।

Syntax:

```python
variable_name = value
```

উদাহরণ:

```python
name = "Masum"
age = 22
is_student = True
```

এখানে:

- `name`-এর সঙ্গে `"Masum"` object যুক্ত হয়েছে।
- `age`-এর সঙ্গে `22` object যুক্ত হয়েছে।
- `is_student`-এর সঙ্গে `True` object যুক্ত হয়েছে।

Python-এ সাধারণ assignment-এর মাধ্যমে variable-এর নাম তৈরি করতে আলাদা করে type declaration লিখতে হয় না।

অন্য কিছু programming language-এ type আগে উল্লেখ করতে হতে পারে, কিন্তু Python-এ সাধারণত তা প্রয়োজন হয় না।

## 4. Understanding the Assignment Operator

Python-এ `=` হলো **assignment operator**।

এটি কোনো variable-এর সঙ্গে একটি value বা object-এর reference যুক্ত করে।

উদাহরণ:

```python
x = 10
```

এর অর্থ `x`-এর সঙ্গে `10` যুক্ত করা হয়েছে।

এটি mathematical equality পরীক্ষা করার অর্থে ব্যবহৃত হয়নি।

দুটি value সমান কি না পরীক্ষা করতে `==` ব্যবহার করা হয়।

```python
x = 10

print(x == 10)
```

Output:

```text
True
```

এখানে:

- `x = 10` — assignment।
- `x == 10` — equality comparison expression।

**মনে রাখবে:** `=` এবং `==` এক নয়।

## 5. How Variables Work in Python

Python-এ variable-কে একটি নির্দিষ্ট box হিসেবে কল্পনা করা শেখার জন্য সহজ হতে পারে। তবে বাস্তবে Python-এর variable name একটি object-কে refer করে।

উদাহরণ:

```python
age = 22
```

এটিকে ধারণাগতভাবে এভাবে ভাবতে পারো:

<box border radius="lg" padding={3} gap={2}>
  <box background="surface-secondary" radius="md" padding={3} align="center">
    <text color="secondary" size="sm">Variable Name</text>
    <title size="lg">age</title>
  </box>
  <box align="center">
    <icon name="arrow-down" size="xl" />
    <text color="secondary" size="sm">refers to</text>
  </box>
  <box border radius="md" padding={3} align="center">
    <text color="secondary" size="sm">Integer Object</text>
    <title size="lg">22</title>
  </box>
</box>

এটি বোঝার একটি সহজ model। বাস্তবে Python variable-কে object-এর সঙ্গে binding করে।

আরেকটি উদাহরণ:

```python
student_name = "Masum"
```

এখানে `student_name` নামটি `"Masum"` string object-কে refer করে।

Python-এ object-এর value বা type সম্পর্কে জানতে built-in functions ব্যবহার করা যায়।

```python
age = 22

print(type(age))
print(id(age))
```

Output-এর উদাহরণ:

```text
<class 'int'>
```

দ্বিতীয় লাইনে একটি integer ID দেখা যাবে। এর নির্দিষ্ট সংখ্যাটি প্রতিবার বা প্রতিটি environment-এ একই হবে—এমন নয়।

- `type()` object-এর type জানায়।
- `id()` object-এর identity নির্দেশকারী একটি integer দেয়।

## 6. Variables Can Store Different Types of Data

Python variable-এর সঙ্গে বিভিন্ন ধরনের object যুক্ত করা যায়।

### 6.1 Integer

পূর্ণসংখ্যার জন্য `int` ব্যবহার হয়।

```python
age = 22
student_count = 50

print(age)
print(student_count)
```

Output:

```text
22
50
```

### 6.2 Floating-Point Number

দশমিক-যুক্ত সংখ্যার জন্য `float` ব্যবহার হয়।

```python
cgpa = 3.95
price = 99.50

print(cgpa)
print(price)
```

Output:

```text
3.95
99.5
```

### 6.3 String

Text সংরক্ষণের জন্য `str` ব্যবহার হয়।

```python
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

### 6.4 Boolean

Boolean object-এর দুটি value হলো `True` এবং `False`।

```python
is_student = True
is_graduated = False

print(is_student)
print(is_graduated)
```

Output:

```text
True
False
```

### 6.5 List

একটি list-এর মধ্যে একাধিক item রাখা যায়।

```python
marks = [80, 85, 90]

print(marks)
```

Output:

```text
[80, 85, 90]
```

### 6.6 Dictionary

Dictionary key-value pair সংরক্ষণ করে।

```python
student = {
    "name": "Masum",
    "age": 22
}

print(student)
```

Output:

```text
{'name': 'Masum', 'age': 22}
```

এই data types-গুলো বিস্তারিতভাবে `03_Data_Types_and_Type_Conversion` chapter-এ শেখা হবে।

## 7. Python Is Dynamically Typed

Python একটি **dynamically typed language**। এর অর্থ, সাধারণ variable assignment-এর সময় variable-এর type আলাদাভাবে declare করতে হয় না। Python runtime-এ object-এর type নির্ধারণ করতে পারে।

উদাহরণ:

```python
value = 10
print(type(value))

value = "Hello"
print(type(value))
```

Output:

```text
<class 'int'>
<class 'str'>
```

প্রথমে `value` integer object-কে refer করছিল। পরে একই নামটি string object-কে refer করছে।

Python-এ এটিকে সাধারণত dynamic typing-এর উদাহরণ বলা হয়।

### Another Example

```python
data = 100
print(data)

data = 25.5
print(data)

data = "Python"
print(data)
```

Output:

```text
100
25.5
Python
```

এখানে একই variable name-কে ভিন্ন সময়ে ভিন্ন type-এর object-এর সঙ্গে যুক্ত করা হয়েছে।

**মনে রাখবে:** Python-এ variable নিজে স্থায়ীভাবে কোনো একটি data type-এর মধ্যে সীমাবদ্ধ থাকে না। তবে প্রতিটি object-এর নিজস্ব type থাকে।

## 8. Variables and Data Types

Variable-এর সঙ্গে যুক্ত object-এর type `type()` দিয়ে দেখা যায়।

```python
name = "Masum"
age = 22
cgpa = 3.95
is_student = True

print(type(name))
print(type(age))
print(type(cgpa))
print(type(is_student))
```

Output:

```text
<class 'str'>
<class 'int'>
<class 'float'>
<class 'bool'>
```

এখানে:

| Variable | Value | Type |
|---|---|---|
| `name` | `"Masum"` | `str` |
| `age` | `22` | `int` |
| `cgpa` | `3.95` | `float` |
| `is_student` | `True` | `bool` |

Type বুঝতে পারলে পরবর্তীতে কোন operation করা যাবে এবং কোন operation-এ error হতে পারে, তা নির্ধারণ করা সহজ হয়।

## 9. Reassigning Variables

একটি variable-এর সঙ্গে পরে নতুন value যুক্ত করাকে **reassignment** বলা হয়।

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

প্রথমে `score`-এর সঙ্গে `50` যুক্ত ছিল। পরে `80` যুক্ত করা হয়েছে।

আরেকটি উদাহরণ:

```python
name = "Masum"
name = "Abdulla"

print(name)
```

Output:

```text
Abdulla
```

শেষ assignment-এর পরে `name` এখন `"Abdulla"` string object-কে refer করছে।

Reassignment-এর বিস্তারিত আলোচনা পরবর্তী ফাইল `11_Variable_Assignment_and_Reassignment.md`-এ করা হবে।

## 10. Multiple Variables

Python-এ একই program-এ একাধিক variable ব্যবহার করা যায়।

```python
name = "Masum"
age = 22
department = "CSE"
cgpa = 3.95

print(name)
print(age)
print(department)
print(cgpa)
```

Output:

```text
Masum
22
CSE
3.95
```

প্রতিটি variable আলাদা নামের মাধ্যমে একটি object-কে refer করছে।

Variable-গুলোর নাম অর্থপূর্ণ হলে program বোঝা সহজ হয়।

## 11. Variables in Calculations

Variable-এর value ব্যবহার করে calculation করা যায়।

```python
first_number = 10
second_number = 20

total = first_number + second_number

print(total)
```

Output:

```text
30
```

এখানে `first_number` ও `second_number`-এর value যোগ করে result `total`-এর সঙ্গে assign করা হয়েছে।

### Practical Example: Calculate Average Marks

```python
math_marks = 80
english_marks = 90
science_marks = 85

total_marks = math_marks + english_marks + science_marks
average_marks = total_marks / 3

print("Total:", total_marks)
print("Average:", average_marks)
```

Output:

```text
Total: 255
Average: 85.0
```

এভাবে variable-এর সাহায্যে intermediate result সংরক্ষণ করে calculation ধাপে ধাপে করা যায়।

## 12. Variables and Object References

Python-এর variable বোঝার জন্য object reference-এর ধারণা গুরুত্বপূর্ণ।

উদাহরণ:

```python
first = [10, 20, 30]
second = first

print(first)
print(second)
```

Output:

```text
[10, 20, 30]
[10, 20, 30]
```

এখানে `second = first` করার ফলে `second` নতুন list তৈরি করেনি। বরং `first` যে list object-কে refer করছে, `second`-ও সেই একই object-কে refer করছে।

এটি যাচাই করা যায়:

```python
first = [10, 20, 30]
second = first

print(first is second)
```

Output:

```text
True
```

এখন list-এ পরিবর্তন করলে:

```python
first = [10, 20, 30]
second = first

first.append(40)

print(first)
print(second)
```

Output:

```text
[10, 20, 30, 40]
[10, 20, 30, 40]
```

দুটি নাম একই mutable list object-কে refer করছে বলে পরিবর্তনটি দুটির মাধ্যমেই দেখা যাচ্ছে।

এটি variable assignment-এর একটি গুরুত্বপূর্ণ বৈশিষ্ট্য।

## 13. Variable Names and Values Are Different

Variable name এবং value এক জিনিস নয়।

```python
name = "Masum"
```

এখানে:

- `name` হলো identifier বা variable name।
- `"Masum"` হলো string object।
- `=` হলো assignment operator।

আরেকটি উদাহরণ:

```python
age = 22
```

এখানে `age` নামটি integer object `22`-কে refer করছে।

নামটি পরিবর্তন করলে object-এর value অবশ্যই পরিবর্তিত হবে—এমন নয়। আবার নতুন object-এর সঙ্গে একই নাম যুক্ত করাও সম্ভব।

এই পার্থক্য বুঝলে Python-এর variable এবং assignment সহজে বোঝা যায়।

## 14. Common Beginner Mistakes

### Mistake 1: Using a Variable Before Assignment

ভুল:

```python
print(age)
```

যদি আগে `age`-এর সঙ্গে কোনো value assign না করা হয়ে থাকে এবং অন্য কোনো scope থেকেও এটি পাওয়া না যায়, তাহলে `NameError` হবে।

সঠিক:

```python
age = 22
print(age)
```

Output:

```text
22
```

### Mistake 2: Using `=` and `==` Incorrectly

```python
age = 22
print(age == 22)
```

Output:

```text
True
```

`=` assignment-এর জন্য এবং `==` equality comparison-এর জন্য ব্যবহৃত হয়।

### Mistake 3: Incorrect Variable Naming

ভুল:

```python
# student name = "Masum"
```

এখানে `student name` একটি valid identifier নয়।

সঠিক:

```python
student_name = "Masum"
```

### Mistake 4: Confusing Text and Variable Names

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

`name` variable-এর value হলো `"Masum"`। কিন্তু `"name"` হলো একটি string literal, যা সরাসরি `name` text-টি নির্দেশ করে।

### Mistake 5: Assuming Variables Have Permanent Types

```python
value = 10
value = "Python"

print(value)
```

Output:

```text
Python
```

Python-এ সাধারণ assignment-এর মাধ্যমে একই variable name ভিন্ন type-এর object-কে refer করতে পারে।

### Mistake 6: Thinking Assignment Always Copies an Object

```python
first = [1, 2, 3]
second = first
```

এখানে `second` আলাদা list তৈরি করেনি। দুটি নাম একই list object-কে refer করছে।

এই বিষয়টি বিশেষ করে list, dictionary এবং অন্যান্য mutable object ব্যবহারের সময় গুরুত্বপূর্ণ।

## 15. Best Practices for Using Variables

1. **Use Meaningful Names:** `student_name`-এর মতো পরিষ্কার নাম ব্যবহার করো।
2. **Follow Naming Conventions:** সাধারণ variable-এর জন্য `snake_case` ব্যবহার করো।
3. **Avoid Unnecessary Reassignment:** অপ্রয়োজনীয়ভাবে একই variable-এর value বারবার পরিবর্তন কোরো না।
4. **Initialize Before Use:** প্রয়োজনীয় variable ব্যবহার করার আগে সঠিকভাবে assign করো।
5. **Use Consistent Types When Appropriate:** একই variable-এ বারবার ভিন্ন ধরনের object রাখলে code বোঝা কঠিন হতে পারে।
6. **Use Constants by Convention:** পরিবর্তন না করার জন্য নির্ধারিত value-কে `MAX_MARKS`-এর মতো নামে প্রকাশ করো।
7. **Understand Mutable Objects:** List বা dictionary-এর মতো object assign করলে reference sharing হতে পারে।
8. **Keep Code Readable:** প্রয়োজন হলে intermediate result-এর জন্য আলাদা variable ব্যবহার করো।

## 16. Practical Examples

### Example 1: Student Profile

```python
student_name = "Masum"
student_age = 22
department = "CSE"
current_cgpa = 3.95

print("Name:", student_name)
print("Age:", student_age)
print("Department:", department)
print("CGPA:", current_cgpa)
```

Output:

```text
Name: Masum
Age: 22
Department: CSE
CGPA: 3.95
```

### Example 2: Simple Shopping Bill

```python
product_name = "Notebook"
product_price = 80
quantity = 3

total_price = product_price * quantity

print("Product:", product_name)
print("Price:", product_price)
print("Quantity:", quantity)
print("Total:", total_price)
```

Output:

```text
Product: Notebook
Price: 80
Quantity: 3
Total: 240
```

### Example 3: Convert Temperature

```python
celsius = 30

fahrenheit = (celsius * 9 / 5) + 32

print("Celsius:", celsius)
print("Fahrenheit:", fahrenheit)
```

Output:

```text
Celsius: 30
Fahrenheit: 86.0
```

### Example 4: Check Data Types

```python
name = "Masum"
age = 22
cgpa = 3.95
is_active = True

print(type(name))
print(type(age))
print(type(cgpa))
print(type(is_active))
```

Output:

```text
<class 'str'>
<class 'int'>
<class 'float'>
<class 'bool'>
```

## 17. Practice Exercises

### Exercise 1: Create Variables

নিচের তথ্যগুলো দিয়ে variable তৈরি করো:

- নিজের নাম
- বয়স
- Department
- CGPA
- বর্তমানে student কি না

তারপর সব value `print()` দিয়ে দেখাও।

### Exercise 2: Calculate Total and Average

তিনটি subject-এর marks variable-এ রাখো। তারপর total ও average বের করো।

### Exercise 3: Predict the Output

```python
x = 10
y = x

x = 20

print(x)
print(y)
```

Output কী হবে? কেন?

### Exercise 4: Check Data Types

```python
name = "Python"
version = 3
rating = 4.5
is_easy = True
```

প্রতিটি variable-এর type `type()` দিয়ে দেখাও।

### Exercise 5: Fix the Errors

নিচের code-এ ভুলগুলো খুঁজে ঠিক করো।

```python
# age = 22
# student name = "Masum"

print(age)
```

### Exercise 6: Understand Shared References

```python
first = [1, 2, 3]
second = first

second.append(4)

print(first)
print(second)
```

Output কী হবে? কেন?

### Exercise 7: Build a Shopping Bill

Product name, price এবং quantity-এর জন্য variable তৈরি করো। তারপর total price হিসাব করে একটি ছোট bill print করো।

## 18. Quick Revision

| Concept | Example | Explanation |
|---|---|---|
| Variable | `age = 22` | `age` নামটি `22`-কে refer করছে |
| Assignment | `x = 10` | `x`-এর সঙ্গে object যুক্ত করা |
| Type checking | `type(x)` | Object-এর type দেখা |
| Reassignment | `x = 20` | একই নামের সঙ্গে নতুন object যুক্ত করা |
| Dynamic typing | `x = "Hello"` | Variable name ভিন্ন type-এর object-কে refer করতে পারে |
| Object reference | `second = first` | একই object-কে একাধিক নাম refer করতে পারে |
| Meaningful naming | `student_name` | Variable-এর উদ্দেশ্য পরিষ্কার করে |

## 19. Chapter Summary

এই topic-এ আমরা শিখেছি:

- Variable হলো object-কে refer করার জন্য ব্যবহৃত নাম।
- Python-এ সাধারণ assignment-এর জন্য `=` ব্যবহার করা হয়।
- Variable ব্যবহার করে data সংরক্ষণ, access এবং calculation করা যায়।
- Python dynamically typed language।
- `type()` দিয়ে object-এর type দেখা যায়।
- Reassignment-এর মাধ্যমে একই নাম নতুন object-কে refer করতে পারে।
- একাধিক variable একই object-কে refer করতে পারে।
- List ও dictionary-এর মতো mutable object-এর reference sharing গুরুত্বপূর্ণ।
- Meaningful variable names code-কে readable ও maintainable করে।

## 20. Next Topic

পরবর্তী ফাইল: [`11_Variable_Assignment_and_Reassignment.md`](11_Variable_Assignment_and_Reassignment.md)

এখানে আমরা assignment statement কীভাবে কাজ করে, reassignment, multiple assignment, chained assignment, augmented assignment এবং variable binding আরও বিস্তারিতভাবে শিখব।