# 17. Introduction to String Formatting

## 1. What Is String Formatting?

**String Formatting** হলো string-এর মধ্যে variable, number বা অন্য value-কে নির্দিষ্ট format-এ সাজিয়ে output দেখানোর পদ্ধতি।

ধরো, আমাদের কাছে একজন student-এর নাম এবং marks আছে।

```python
name = "Masum"
marks = 85

print("Student name:", name)
print("Marks:", marks)
```

Output:

```text
Student name: Masum
Marks: 85
```

এটি সঠিক output। তবে কখনো আমরা variable-এর value-গুলোকে একটি sentence-এর মধ্যে রাখতে চাই।

যেমন:

```text
Masum obtained 85 marks.
```

এ কাজটি সুন্দরভাবে করার জন্য string formatting ব্যবহার করা যায়।

## 2. Why Do We Need String Formatting?

String formatting ব্যবহার করার প্রধান কারণগুলো হলো:

1. Output-কে সুন্দর ও readable করা।
2. String-এর মধ্যে variable-এর value দেখানো।
3. Number-কে নির্দিষ্ট decimal places-এ দেখানো।
4. Text ও number-কে একসঙ্গে সাজানো।
5. Table, report ও invoice-এর মতো structured output তৈরি করা।
6. Output-এর alignment ও spacing নিয়ন্ত্রণ করা।

### Example: Without Formatting

```python
name = "Masum"
cgpa = 3.95

print("Student: " + name)
print("CGPA: " + str(cgpa))
```

Output:

```text
Student: Masum
CGPA: 3.95
```

এখানে number-কে string-এ convert করতে `str()` ব্যবহার করতে হয়েছে।

### Example: With Formatting

```python
name = "Masum"
cgpa = 3.95

print(f"Student: {name}")
print(f"CGPA: {cgpa}")
```

Output:

```text
Student: Masum
CGPA: 3.95
```

এখানে f-string ব্যবহার করে variable-এর value সরাসরি string-এর মধ্যে দেখানো হয়েছে।

## 3. Main String Formatting Methods in Python

Python-এ string formatting করার কয়েকটি প্রচলিত পদ্ধতি রয়েছে।

| Method | Example | ব্যবহার |
|---|---|---|
| String concatenation | `"Hello " + name` | String যুক্ত করা |
| `str.format()` | `"Hello {}".format(name)` | Placeholder-এ value বসানো |
| f-string | `f"Hello {name}"` | String-এর মধ্যে value দেখানো |
| Percent formatting | `"Hello %s" % name` | পুরোনো formatting পদ্ধতি |

এই chapter-এ আমরা formatting-এর ধারণা শিখছি। প্রতিটি পদ্ধতি পরবর্তী topic-গুলোতে আরও বিস্তারিতভাবে আলোচনা করা হবে।

**Modern Python-এ সাধারণত f-string সবচেয়ে সহজ ও readable পদ্ধতিগুলোর একটি।**

## 4. String Concatenation vs String Formatting

দুটির মধ্যে পার্থক্য বোঝা গুরুত্বপূর্ণ।

### Using Concatenation

```python
name = "Masum"
age = 22

message = "My name is " + name + " and I am " + str(age) + " years old."

print(message)
```

Output:

```text
My name is Masum and I am 22 years old.
```

এখানে integer `age`-কে string-এ convert করতে হয়েছে।

### Using an f-string

```python
name = "Masum"
age = 22

message = f"My name is {name} and I am {age} years old."

print(message)
```

Output:

```text
My name is Masum and I am 22 years old.
```

এখানে `age`-কে আলাদাভাবে `str()` দিয়ে convert করতে হয়নি।

### Main Difference

- **Concatenation:** একাধিক string `+` দিয়ে যুক্ত করে।
- **String formatting:** string-এর মধ্যে value-কে নির্দিষ্ট জায়গায় ও format-এ দেখাতে সাহায্য করে।

## 5. Introduction to Placeholders

কিছু formatting method-এ string-এর মধ্যে নির্দিষ্ট জায়গা রাখা হয়, যেখানে পরে value বসানো হয়। এই জায়গাকে সাধারণভাবে **placeholder** বলা হয়।

### Example: Using `{}`

```python
name = "Masum"

message = "Hello, {}".format(name)

print(message)
```

Output:

```text
Hello, Masum
```

এখানে `{}` হলো placeholder। `.format(name)` সেই placeholder-এর জায়গায় `name`-এর value বসিয়েছে।

### Example: Multiple Placeholders

```python
name = "Masum"
department = "CSE"

message = "{} studies {}".format(name, department)

print(message)
```

Output:

```text
Masum studies CSE
```

প্রথম `{}`-এ `name` এবং দ্বিতীয় `{}`-এ `department`-এর value বসেছে।

## 6. Introduction to f-Strings

f-string হলো Python-এর string formatting-এর একটি আধুনিক পদ্ধতি। Python 3.6 থেকে এটি পাওয়া যায়।

String-এর শুরুতে `f` বা `F` লিখলে সেটি f-string হয়। এর মধ্যে `{}` ব্যবহার করে variable বা expression-এর value দেখানো যায়।

### Basic Syntax

```python
f"Text {variable}"
```

### Example

```python
name = "Masum"
age = 22

print(f"My name is {name}.")
print(f"I am {age} years old.")
```

Output:

```text
My name is Masum.
I am 22 years old.
```

এখানে `{name}` এবং `{age}`-এর জায়গায় সংশ্লিষ্ট variable-এর value বসেছে।

### Why Are f-Strings Useful?

- সহজে পড়া যায়।
- কম code লিখতে হয়।
- String-এর মধ্যে variable সরাসরি ব্যবহার করা যায়।
- Arithmetic expression-ও লেখা যায়।
- Number formatting সহজ হয়।

f-string-এর বিস্তারিত ব্যবহার পরবর্তী topic `18_f_Strings_in_Python.md`-এ শেখা হবে।

## 7. Formatting Numbers

String formatting দিয়ে number-কে নির্দিষ্টভাবে দেখানো যায়।

ধরো, একটি calculation-এর ফলাফল হলো:

```python
price = 125.6789

print(price)
```

Output:

```text
125.6789
```

কিন্তু আমরা যদি দশমিকের পর দুই ঘর দেখাতে চাই:

```python
price = 125.6789

print(f"{price:.2f}")
```

Output:

```text
125.68
```

এখানে:

- `:` formatting specification শুরু করে।
- `.2f` floating-point number-কে দশমিকের পর দুই ঘরসহ দেখায়।

মনে রাখবে, এই formatting শুধু প্রদর্শনের ফলাফলকে format করে। এটি মূল `price` variable-কে string-এ পরিবর্তন করে না।

## 8. Formatting Percentages

Percentage দেখানোর জন্যও formatting ব্যবহার করা যায়।

```python
score = 0.8567

print(f"{score:.2%}")
```

Output:

```text
85.67%
```

এখানে `.2%` value-কে 100 দিয়ে গুণ করে percentage হিসেবে দেখায় এবং দশমিকের পর দুই ঘর রাখে।

**গুরুত্বপূর্ণ:** যদি `score = 85.67` হয়, তাহলে একই formatting ব্যবহার করলে output হবে `8567.00%`। তাই percentage formatting-এর জন্য সাধারণত ratio হিসেবে রাখা value ব্যবহার করা হয়, যেমন `0.8567`।

## 9. Formatting Text and Numbers Together

বাস্তব program-এ প্রায়ই text ও numeric value একসঙ্গে দেখাতে হয়।

### Example: Student Result

```python
name = "Masum"
marks = 85
cgpa = 3.95

print(f"Name: {name}")
print(f"Marks: {marks}")
print(f"CGPA: {cgpa:.2f}")
```

Output:

```text
Name: Masum
Marks: 85
CGPA: 3.95
```

### Example: Product Information

```python
product = "Keyboard"
price = 1250.5
quantity = 2

print(f"Product: {product}")
print(f"Price: {price:.2f}")
print(f"Quantity: {quantity}")
print(f"Total: {price * quantity:.2f}")
```

Output:

```text
Product: Keyboard
Price: 1250.50
Quantity: 2
Total: 2501.00
```

এখানে expression `{price * quantity:.2f}` হিসাব করে ফলাফলকে দুই decimal place-এ দেখিয়েছে।

## 10. Introduction to Alignment and Width

String formatting-এর মাধ্যমে output-এর spacing ও alignment নিয়ন্ত্রণ করা যায়।

### Example: Right Alignment

```python
name = "Masum"

print(f"|{name:>10}|")
```

Output:

```text
|     Masum|
```

এখানে `>10` মানে value-টিকে মোট 10 character-এর জায়গায় right-align করা।

### Example: Left Alignment

```python
name = "Masum"

print(f"|{name:<10}|")
```

Output:

```text
|Masum     |
```

এখানে `<10` value-টিকে left-align করেছে।

### Example: Center Alignment

```python
name = "Masum"

print(f"|{name:^10}|")
```

Output:

```text
|  Masum   |
```

এখানে `^10` value-টিকে 10 character-এর জায়গায় center-align করেছে।

Alignment ও padding-এর বিস্তারিত আলোচনা থাকবে `21_String_Alignment_Width_and_Padding.md` ফাইলে।

## 11. Formatting in Real-World Programs

String formatting শুধু সাধারণ sentence-এর জন্য নয়। বাস্তব program-এও এটি গুরুত্বপূর্ণ।

### Example 1: Result Report

```python
name = "Masum"
marks = 85
total_marks = 100

percentage = marks / total_marks

print("=" * 30)
print("STUDENT RESULT")
print("=" * 30)
print(f"Name: {name}")
print(f"Marks: {marks}/{total_marks}")
print(f"Percentage: {percentage:.2%}")
print("=" * 30)
```

Output:

```text
==============================
STUDENT RESULT
==============================
Name: Masum
Marks: 85/100
Percentage: 85.00%
==============================
```

### Example 2: Simple Receipt

```python
item = "Notebook"
price = 50
quantity = 3

total = price * quantity

print("Item:", item)
print(f"Price: {price:.2f}")
print(f"Quantity: {quantity}")
print(f"Total: {total:.2f}")
```

Output:

```text
Item: Notebook
Price: 50.00
Quantity: 3
Total: 150.00
```

এ ধরনের formatting output-কে আরও পরিষ্কার ও professional করে।

## 12. Common Mistakes

### Mistake 1: Forgetting the `f` Prefix

```python
name = "Masum"

print("Hello, {name}")
```

Output:

```text
Hello, {name}
```

এখানে `{name}`-কে Python variable হিসেবে evaluate করা হয়নি, কারণ string-টি f-string নয়।

সঠিক code:

```python
print(f"Hello, {name}")
```

Output:

```text
Hello, Masum
```

### Mistake 2: Using Incorrect Braces

```python
name = "Masum"

print(f"Hello, (name)")
```

Output:

```text
Hello, (name)
```

f-string-এ variable-এর value দেখাতে curly braces `{}` ব্যবহার করতে হয়।

সঠিক code:

```python
print(f"Hello, {name}")
```

### Mistake 3: Confusing Display Formatting with Data Conversion

```python
price = 12.5

result = f"{price:.2f}"

print(result)
print(type(result))
```

Output:

```text
12.50
<class 'str'>
```

এখানে `result` একটি string। Formatting-এর মাধ্যমে numeric value-কে formatted text-এ রূপান্তর করা হয়েছে।

অন্যদিকে:

```python
price = 12.5

print(f"{price:.2f}")
print(type(price))
```

Output:

```text
12.50
<class 'float'>
```

এখানে মূল `price` variable এখনো float।

### Mistake 4: Using `%` Without Understanding Its Meaning

```python
score = 0.75

print(f"{score:.0%}")
```

Output:

```text
75%
```

এখানে `%` formatting specification হিসেবে ব্যবহৃত হয়েছে। এটি সাধারণ string-এর মধ্যে শুধু `%` character বসানোর সমান নয়।

## 13. Choosing the Right Formatting Method

| Situation | Recommended approach |
|---|---|
| সাধারণ text যুক্ত করা | `+` অথবা f-string |
| Variable-এর value sentence-এ দেখানো | f-string |
| নির্দিষ্ট decimal places দেখানো | f-string formatting |
| Existing placeholder-based format ব্যবহার করা | `str.format()` |
| পুরোনো code maintain করা | `%` formatting বুঝে রাখা |
| একাধিক string list থেকে একত্র করা | `str.join()` বিবেচনা করা |

নতুন Python code-এ সাধারণ output formatting-এর জন্য f-string প্রায়ই সবচেয়ে সহজ পছন্দ।

তবে পুরোনো project-এ `.format()` বা `%` formatting দেখতে পারো। তাই সেগুলোর basic ধারণাও জানা দরকার।

## 14. Practice Exercises

### Exercise 1: Basic Formatting

`name = "Masum"` variable ব্যবহার করে নিচের output তৈরি করো:

```text
Hello, Masum!
```

### Exercise 2: Multiple Variables

`name`, `department` এবং `university` variable ব্যবহার করে একটি sentence তৈরি করো।

### Exercise 3: Decimal Formatting

`price = 125.6789` দেওয়া আছে। দশমিকের পর দুই ঘর দেখাও।

### Exercise 4: Percentage Formatting

`score = 0.875` দেওয়া আছে। percentage হিসেবে দশমিকের পর এক ঘর দেখাও।

### Exercise 5: Student Result

একটি student-এর নাম, marks এবং CGPA নিয়ে formatted report তৈরি করো।

### Exercise 6: Predict the Output

```python
name = "Python"

print("Hello, {name}")
print(f"Hello, {name}")
```

দুটি output কী হবে?

### Exercise 7: Alignment

`"CSE"` string-টিকে 10-character width-এর মধ্যে right-align করো।

### Exercise 8: Product Receipt

একটি product-এর name, price ও quantity ব্যবহার করে total-সহ formatted receipt তৈরি করো।

### Exercise 9: `str.format()`

নিচের code সম্পূর্ণ করো:

```python
name = "Masum"
message = "Welcome, {}"

print(message.format(name))
```

Output কী হবে?

### Exercise 10: Challenge

একটি student-এর নাম, প্রাপ্ত নম্বর এবং মোট নম্বর input নিয়ে একটি formatted report তৈরি করো। Percentage দুই decimal place-এ দেখাবে। মোট নম্বর শূন্য হলে division করবে না।

## 15. Practice Answer Key

### Answer 1

```python
name = "Masum"

print(f"Hello, {name}!")
```

### Answer 2

```python
name = "Masum"
department = "CSE"
university = "NUB"

print(f"{name} studies {department} at {university}.")
```

### Answer 3

```python
price = 125.6789

print(f"{price:.2f}")
```

Output:

```text
125.68
```

### Answer 4

```python
score = 0.875

print(f"{score:.1%}")
```

Output:

```text
87.5%
```

### Answer 5

```python
name = "Masum"
marks = 85
cgpa = 3.95

print(f"Name: {name}")
print(f"Marks: {marks}")
print(f"CGPA: {cgpa:.2f}")
```

### Answer 6

Output:

```text
Hello, {name}
Hello, Python
```

প্রথম string-টি f-string নয়। দ্বিতীয় string-এ `f` prefix থাকায় variable evaluate হয়েছে।

### Answer 7

```python
text = "CSE"

print(f"{text:>10}")
```

Output:

```text
       CSE
```

### Answer 8

```python
product = "Notebook"
price = 50
quantity = 3

total = price * quantity

print(f"Product: {product}")
print(f"Price: {price:.2f}")
print(f"Quantity: {quantity}")
print(f"Total: {total:.2f}")
```

### Answer 9

Output:

```text
Welcome, Masum
```

### Answer 10

```python
name = input("Enter student name: ")

try:
    marks = float(input("Enter obtained marks: "))
    total_marks = float(input("Enter total marks: "))

    if total_marks <= 0:
        print("Total marks must be greater than zero.")
    elif marks < 0 or marks > total_marks:
        print("Obtained marks must be within the valid range.")
    else:
        percentage = marks / total_marks * 100

        print("=" * 30)
        print("STUDENT REPORT")
        print("=" * 30)
        print(f"Name: {name}")
        print(f"Marks: {marks:g}/{total_marks:g}")
        print(f"Percentage: {percentage:.2f}%")

except ValueError:
    print("Please enter valid numeric marks.")
```

## 16. Best Practices

1. সাধারণ text formatting-এর জন্য f-string ব্যবহার করতে শেখো।
2. Variable-এর value দেখাতে f-string-এর মধ্যে `{variable}` লেখো।
3. Number-এর decimal places নিয়ন্ত্রণ করতে `:.2f`-এর মতো specification ব্যবহার করো।
4. Percentage দেখানোর সময় input value ratio নাকি already percentage, তা বুঝে নাও।
5. Formatting-এর ফলাফল প্রায়ই string হয়—পরবর্তী calculation-এর জন্য মূল numeric variable ব্যবহার করো।
6. Code readable রাখো এবং অপ্রয়োজনীয় concatenation এড়িয়ে চলো।
7. পুরোনো code পড়তে `.format()` ও `%` formatting-এর basic ধারণা রাখো।

## 17. Chapter Summary

- String formatting হলো string-এর মধ্যে value-কে সুন্দরভাবে দেখানোর পদ্ধতি।
- Concatenation-এর জন্য `+` ব্যবহার করা যায়।
- `str.format()` placeholder-এর জায়গায় value বসায়।
- f-string-এর জন্য string-এর শুরুতে `f` বা `F` লিখতে হয়।
- `{variable}` দিয়ে f-string-এ variable-এর value দেখানো যায়।
- `:.2f` দশমিকের পর দুই ঘর দেখায়।
- `:.2%` ratio-কে percentage হিসেবে দুই decimal place-এ দেখায়।
- Alignment ও width formatting-এর সাহায্যে output সাজানো যায়।

## 18. Self-Assessment Checklist

- [ ] String formatting-এর প্রয়োজন বুঝি।
- [ ] Concatenation ও formatting-এর পার্থক্য বুঝি।
- [ ] Placeholder ও `str.format()` ব্যবহার করতে পারি।
- [ ] Basic f-string লিখতে পারি।
- [ ] Number-কে নির্দিষ্ট decimal places-এ দেখাতে পারি।
- [ ] Percentage formatting করতে পারি।
- [ ] Text alignment ও width-এর basic syntax বুঝি।
- [ ] Formatted string এবং original numeric variable-এর পার্থক্য বুঝি।

**Next Topic:** `18_f_Strings_in_Python.md` — এখানে f-string-এর syntax, variable, expression, function call, number formatting এবং practical usage বিস্তারিতভাবে শিখব।