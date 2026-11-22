
# 39. Old-Style String Formatting in Python

## 1. Introduction to Old-Style String Formatting

Python-এ String Formatting-এর একটি পুরোনো পদ্ধতি হলো **Old-Style String Formatting**।

এই পদ্ধতিতে String-এর মধ্যে Value বসানোর জন্য Percentage (`%`) Operator ব্যবহার করা হয়।

এটি Python-এর পুরোনো String Formatting পদ্ধতি। বর্তমানে f-String এবং `format()` method বেশি ব্যবহার করা হয়। তবে পুরোনো Python Code বুঝতে এই পদ্ধতি জানা গুরুত্বপূর্ণ।

Old-Style String Formatting ব্যবহার করে আমরা:

- String-এর মধ্যে Variable-এর Value বসাতে পারি।
- Integer এবং Float Format করতে পারি।
- Decimal Places নির্ধারণ করতে পারি।
- String Alignment করতে পারি।
- Number-এর Width নির্ধারণ করতে পারি।
- একাধিক Value একটি String-এর মধ্যে ব্যবহার করতে পারি।

### Example

```python
name = "Masum"

message = "Hello, %s" % name

print(message)
```

**Output:**

```text
Hello, Masum
```

এখানে:

- `%s` হলো String Format Specifier।
- `%` Operator Value-কে Placeholder-এ বসিয়েছে।
- `name` Variable-এর Value হিসেবে `Masum` Display হয়েছে।

---

## 2. Basic Syntax of Old-Style Formatting

### Syntax

```python
"string %specifier" % value
```

এখানে:

- `string` হলো মূল Text।
- `%specifier` হলো Value-এর Data Type অনুযায়ী Placeholder।
- `%` হলো Formatting Operator।
- `value` হলো যে Value String-এর মধ্যে বসবে।

### Example

```python
name = "Rahim"
age = 22

message = "My name is %s and I am %d years old." % (name, age)

print(message)
```

**Output:**

```text
My name is Rahim and I am 22 years old.
```

এখানে:

- `%s` → String Value।
- `%d` → Integer Value।
- `(name, age)` → Formatting-এর জন্য দেওয়া Values।

---

## 3. Important Format Specifiers

Old-Style String Formatting-এ বিভিন্ন Data Type-এর জন্য বিভিন্ন Format Specifier ব্যবহার করা হয়।

| Specifier | কাজ |
|---|---|
| `%s` | String |
| `%d` | Integer |
| `%i` | Integer |
| `%f` | Floating-Point Number |
| `%e` | Scientific Notation |
| `%x` | Hexadecimal (Lowercase) |
| `%X` | Hexadecimal (Uppercase) |
| `%o` | Octal |
| `%%` | Percentage Symbol |

### Example

```python
name = "Masum"
age = 23
marks = 87.567

print("Name: %s" % name)
print("Age: %d" % age)
print("Marks: %f" % marks)
```

**Output:**

```text
Name: Masum
Age: 23
Marks: 87.567000
```

এখানে:

- `%s` String Display করেছে।
- `%d` Integer Display করেছে।
- `%f` Float-কে Default Six Decimal Places-এ Display করেছে।

---

## 4. Using %s for String Formatting

String Value Display করার জন্য `%s` ব্যবহার করা হয়।

### Example 1

```python
name = "Masum"

print("My name is %s" % name)
```

**Output:**

```text
My name is Masum
```

### Example 2: Multiple Strings

```python
first_name = "Abdulla"
last_name = "Masum"

print("Name: %s %s" % (first_name, last_name))
```

**Output:**

```text
Name: Abdulla Masum
```

এখানে দুটি `%s` Placeholder-এর জন্য দুটি String Value দেওয়া হয়েছে।

---

## 5. Using %d and %i for Integers

Integer Value Display করার জন্য `%d` এবং `%i` ব্যবহার করা যায়।

### Example 1: Using %d

```python
age = 23

print("Age: %d" % age)
```

**Output:**

```text
Age: 23
```

### Example 2: Using %i

```python
number = 100

print("Number: %i" % number)
```

**Output:**

```text
Number: 100
```

### Example 3: Integer Conversion

```python
number = 25.89

print("Number: %d" % number)
```

**Output:**

```text
Number: 25
```

এখানে `%d` Float Value-কে Integer-এ Convert করেছে। Decimal Part বাদ পড়েছে; এটি সাধারণ Rounding নয়।

**মনে রাখবে:** `%d` এবং `%i` উভয়ই Integer Formatting-এর জন্য ব্যবহার করা হয়।

---

## 6. Using %f for Floating-Point Numbers

Float Value Display করার জন্য `%f` ব্যবহার করা হয়।

### Example 1

```python
price = 125.5

print("Price: %f" % price)
```

**Output:**

```text
Price: 125.500000
```

Default হিসেবে `%f` Decimal-এর পরে ছয়টি Digit দেখায়।

### Example 2: Two Decimal Places

```python
price = 125.5678

print("Price: %.2f" % price)
```

**Output:**

```text
Price: 125.57
```

এখানে `%.2f` Decimal-এর পরে দুইটি Digit দেখিয়েছে।

### Example 3: Three Decimal Places

```python
number = 12.345678

print("%.3f" % number)
```

**Output:**

```text
12.346
```

### Example 4: No Decimal Places

```python
number = 45.89

print("%.0f" % number)
```

**Output:**

```text
46
```

**মনে রাখবে:** `%.nf` ব্যবহার করে Decimal-এর পরে নির্দিষ্ট সংখ্যক Digit দেখানো যায়।

---

## 7. Formatting Multiple Values

একটি String-এর মধ্যে একাধিক Value বসানোর জন্য Tuple ব্যবহার করা হয়।

### Syntax

```python
"Value: %s, Number: %d" % (value1, value2)
```

### Example

```python
name = "Masum"
age = 23
cgpa = 3.95

message = "Name: %s, Age: %d, CGPA: %.2f" % (name, age, cgpa)

print(message)
```

**Output:**

```text
Name: Masum, Age: 23, CGPA: 3.95
```

এখানে:

- প্রথম `%s` → `name`
- দ্বিতীয় `%d` → `age`
- তৃতীয় `%.2f` → `cgpa`

**Important:** একাধিক Value ব্যবহার করলে তাদের Order অবশ্যই Placeholder-এর Order অনুযায়ী হতে হবে।

---

## 8. Formatting Numbers with Thousands Separator

বড় Number সহজে পড়ার জন্য Comma ব্যবহার করা যায়।

### Example 1: Integer

```python
number = 1000000

print("%,d" % number)
```

**Output:**

```text
1,000,000
```

### Example 2: Float

```python
price = 1234567.89

print("%,.2f" % price)
```

**Output:**

```text
1,234,567.89
```

এখানে:

- `,` → Thousands Separator যোগ করে।
- `.2f` → Decimal-এর পরে দুইটি Digit দেখায়।

---

## 9. Formatting Percentage

Old-Style Formatting-এ Percentage Symbol Display করতে `%%` ব্যবহার করা হয়।

### Example 1

```python
result = 85

print("Result: %d%%" % result)
```

**Output:**

```text
Result: 85%
```

এখানে `%%` ব্যবহার করে একটি Percentage Symbol Display করা হয়েছে।

### Example 2: Decimal to Percentage

```python
result = 0.85

print("Percentage: %.2f%%" % (result * 100))
```

**Output:**

```text
Percentage: 85.00%
```

**Important:** Old-Style Formatting-এ `%%` নিজে থেকে Decimal Value-কে 100 দিয়ে গুণ করে না। প্রয়োজন হলে নিজেকেই 100 দিয়ে গুণ করতে হবে।

---

## 10. String Width and Alignment

Old-Style Formatting ব্যবহার করে নির্দিষ্ট Width-এর মধ্যে String বা Number Display করা যায়।

### Example 1: Right Alignment

```python
name = "Python"

print("%15s" % name)
```

**Output:**

```text
         Python
```

এখানে Text ডান পাশে থাকে এবং বাম পাশে Space যোগ হয়।

### Example 2: Left Alignment

```python
name = "Python"

print("%-15s" % name)
```

**Output:**

```text
Python
```

এখানে Text বাম পাশে থাকে এবং ডান পাশে Space যোগ হয়।

### Example 3: Integer Width

```python
number = 42

print("%5d" % number)
```

**Output:**

```text
   42
```

এখানে Number-এর জন্য মোট 5 Character Width রাখা হয়েছে।

### Alignment Summary

| Format | কাজ |
|---|---|
| `%15s` | Right Alignment |
| `%-15s` | Left Alignment |
| `%5d` | Integer-এর Width 5 |
| `%10.2f` | Width 10 এবং দুই Decimal Places |

---

## 11. Zero Padding

Number-এর বাম পাশে Zero যোগ করতে `0` Flag ব্যবহার করা হয়।

### Example 1

```python
number = 42

print("%05d" % number)
```

**Output:**

```text
00042
```

এখানে:

- `0` → Zero Padding।
- `5` → Total Width।

### Example 2

```python
number = 25

print("%08d" % number)
```

**Output:**

```text
00000025
```

এখানে Number-এর মোট Width 8 করা হয়েছে।

---

## 12. Formatting Positive and Negative Signs

Number-এর আগে Positive বা Negative Sign Display করতে `+` এবং Space Flag ব্যবহার করা যায়।

### Example 1: Always Show Sign

```python
a = 25
b = -25

print("%+d" % a)
print("%+d" % b)
```

**Output:**

```text
+25
-25
```

এখানে Positive এবং Negative উভয় Number-এর Sign Display হয়েছে।

### Example 2: Space for Positive Numbers

```python
a = 25
b = -25

print("% d" % a)
print("% d" % b)
```

**Output:**

```text
 25
-25
```

এখানে Positive Number-এর আগে Space রাখা হয়েছে।

---

## 13. Scientific Notation

বড় বা ছোট Number-কে Scientific Notation-এ Display করতে `%e` এবং `%E` ব্যবহার করা হয়।

### Example 1: Lowercase e

```python
number = 1234567

print("%e" % number)
```

**Output:**

```text
1.234567e+06
```

### Example 2: Uppercase E

```python
number = 1234567

print("%E" % number)
```

**Output:**

```text
1.234567E+06
```

### Example 3: Two Decimal Places

```python
number = 1234567

print("%.2e" % number)
```

**Output:**

```text
1.23e+06
```

এখানে `%.2e` Scientific Notation-এ Decimal-এর পরে দুইটি Digit দেখিয়েছে।

---

## 14. Hexadecimal and Octal Formatting

Integer-কে বিভিন্ন Number System-এ Display করতে Old-Style Formatting ব্যবহার করা যায়।

### Example 1: Hexadecimal

```python
number = 255

print("%x" % number)
print("%X" % number)
```

**Output:**

```text
ff
FF
```

এখানে:

- `%x` → Lowercase Hexadecimal।
- `%X` → Uppercase Hexadecimal।

### Example 2: Octal

```python
number = 8

print("%o" % number)
```

**Output:**

```text
10
```

এখানে Decimal Number `8` Octal Number `10` হিসেবে Display হয়েছে।

---

## 15. Using %% to Display Percentage Symbol

Old-Style Formatting-এ `%` একটি Special Character।

তাই সরাসরি Percentage Symbol Display করতে Double Percentage (`%%`) ব্যবহার করতে হয়।

### Example

```python
print("Progress: 75%%")
print("Discount: 20%%")
```

**Output:**

```text
Progress: 75%
Discount: 20%
```

**মনে রাখবে:**

- `%` → Formatting শুরু করে।
- `%%` → একটি `%` Display করে।

---

## 16. Formatting with Dictionary

Old-Style Formatting-এ Dictionary-এর Key ব্যবহার করেও Value বসানো যায়।

### Example

```python
student = {
    "name": "Masum",
    "age": 23,
    "department": "CSE"
}

message = "Name: %(name)s, Age: %(age)d, Department: %(department)s" % student

print(message)
```

**Output:**

```text
Name: Masum, Age: 23, Department: CSE
```

এখানে:

- `%(name)s` → Dictionary-এর `name` Value।
- `%(age)d` → Dictionary-এর `age` Value।
- `%(department)s` → Dictionary-এর `department` Value।

এভাবে Dictionary Key ব্যবহার করে নির্দিষ্ট Value Access করা যায়।

---

## 17. Combining Multiple Formatting Options

একটি Format Specifier-এর মধ্যে একাধিক Formatting Option ব্যবহার করা যায়।

### General Syntax

```python
%[flags][width][.precision]type
```

এখানে:

- `flags` → Alignment, Sign বা Zero Padding নির্ধারণ করে।
- `width` → মোট Character Width নির্ধারণ করে।
- `precision` → Decimal Places নির্ধারণ করে।
- `type` → Value-এর Data Type নির্ধারণ করে।

### Example

```python
price = 12345.678

print("%+015,.2f" % price)
```

**Output:**

```text
+0000,012,345.68
```

এখানে:

- `+` → Positive Sign দেখায়।
- `0` → Zero Padding করে।
- `15` → Total Width নির্ধারণ করে।
- `,` → Thousands Separator যোগ করে।
- `.2f` → দুই Decimal Places দেখায়।

---

## 18. Practical Example: Student Information

```python
name = "Masum"
department = "CSE"
semester = 9
cgpa = 3.95

print("Student Information")
print("---------------------------")
print("Name: %s" % name)
print("Department: %s" % department)
print("Semester: %d" % semester)
print("CGPA: %.2f" % cgpa)
```

**Output:**

```text
Student Information
---------------------------
Name: Masum
Department: CSE
Semester: 9
CGPA: 3.95
```

এখানে Old-Style Formatting ব্যবহার করে Student Information Display করা হয়েছে।

---

## 19. Practical Example: Product Price List

```python
products = [
    ("Keyboard", 1250.567),
    ("Mouse", 750.5),
    ("Monitor", 12500.999)
]

print("%-15s %12s" % ("Product", "Price"))
print("-" * 27)

for name, price in products:
    print("%-15s %12,.2f" % (name, price))
```

**Output:**

```text
Product                Price
---------------------------
Keyboard            1,250.57
Mouse                 750.50
Monitor            12,501.00
```

এখানে:

- `%-15s` → Product Name-কে Left Alignment করেছে।
- `%12,.2f` → Price-কে Right Alignment করেছে।
- `,` → Thousands Separator যোগ করেছে।
- `.2f` → দুই Decimal Places দেখিয়েছে।

---

## 20. Practical Example: Result Calculator

```python
name = "Masum"
total_marks = 450
full_marks = 500

percentage = (total_marks / full_marks) * 100

print("Student: %s" % name)
print("Total Marks: %d" % total_marks)
print("Full Marks: %d" % full_marks)
print("Percentage: %.2f%%" % percentage)
```

**Output:**

```text
Student: Masum
Total Marks: 450
Full Marks: 500
Percentage: 90.00%
```

এখানে Marks থেকে Percentage বের করে Old-Style Formatting ব্যবহার করে Display করা হয়েছে।

---

## 21. Old-Style Formatting vs format() vs f-String

Python-এ String Formatting-এর তিনটি গুরুত্বপূর্ণ পদ্ধতি হলো:

1. Old-Style Formatting।
2. `format()` Method।
3. f-String।

### Example 1: Old-Style Formatting

```python
name = "Masum"
age = 23

print("Name: %s, Age: %d" % (name, age))
```

### Example 2: format() Method

```python
name = "Masum"
age = 23

print("Name: {}, Age: {}".format(name, age))
```

### Example 3: f-String

```python
name = "Masum"
age = 23

print(f"Name: {name}, Age: {age}")
```

**Output:**

```text
Name: Masum, Age: 23
Name: Masum, Age: 23
Name: Masum, Age: 23
```

### Main Differences

| Old-Style (%) | format() | f-String |
|---|---|---|
| `%` Operator ব্যবহার করে। | `.format()` ব্যবহার করে। | String-এর আগে `f` ব্যবহার করে। |
| `%s`, `%d`, `%f` ব্যবহার করে। | `{}` ব্যবহার করে। | `{variable}` ব্যবহার করে। |
| তুলনামূলকভাবে পুরোনো পদ্ধতি। | পরবর্তী Formatting পদ্ধতি। | Python 3.6 থেকে পাওয়া যায়। |
| পুরোনো Code-এ দেখা যায়। | অনেক Code-এ এখনো ব্যবহার হয়। | Modern Python Code-এ বেশি ব্যবহার হয়। |

**মনে রাখবে:** নতুন Python Code লেখার ক্ষেত্রে সাধারণত f-String ব্যবহার করা সুবিধাজনক। তবে পুরোনো Code বোঝার জন্য Old-Style Formatting জানা প্রয়োজন।

---

## 22. Important Format Specifiers

| Specifier | কাজ |
|---|---|
| `%s` | String |
| `%d` | Integer |
| `%i` | Integer |
| `%f` | Float |
| `%.2f` | দুই Decimal Places |
| `%e` | Scientific Notation |
| `%x` | Lowercase Hexadecimal |
| `%X` | Uppercase Hexadecimal |
| `%o` | Octal |
| `%%` | Percentage Symbol |
| `%10s` | Right Alignment |
| `%-10s` | Left Alignment |
| `%05d` | Zero Padding |
| `%+d` | Sign Display |

---

## 23. Important Rules to Remember

1. Old-Style Formatting-এ `%` Operator ব্যবহার করা হয়।
2. `%s` String Display করে।
3. `%d` এবং `%i` Integer Display করে।
4. `%f` Floating-Point Number Display করে।
5. `%e` Scientific Notation Display করে।
6. `%x` এবং `%X` Hexadecimal Display করে।
7. `%o` Octal Number Display করে।
8. একাধিক Value ব্যবহার করতে Tuple দেওয়া যায়।
9. Dictionary Key ব্যবহার করেও Value Format করা যায়।
10. `%.2f` Decimal-এর পরে দুইটি Digit দেখায়।
11. `,` Thousands Separator যোগ করে।
12. `%%` একটি Percentage Symbol Display করে।
13. `%15s` Right Alignment করে।
14. `%-15s` Left Alignment করে।
15. `%05d` Zero Padding করে।
16. `%+d` Positive এবং Negative উভয় Number-এর Sign দেখায়।
17. Old-Style Formatting একটি নতুন Formatted String তৈরি করে।
18. এটি Python-এর পুরোনো Formatting পদ্ধতি।

---

## 24. Common Mistakes and Debugging

### Mistake 1: Forgetting the Tuple

```python
name = "Masum"
age = 23

print("Name: %s, Age: %d" % name)
```

**Output:**

```text
TypeError: not enough arguments for format string
```

**সমস্যা:** দুটি Placeholder থাকলেও একাধিক Value সঠিকভাবে দেওয়া হয়নি।

**Correct Code:**

```python
name = "Masum"
age = 23

print("Name: %s, Age: %d" % (name, age))
```

**Output:**

```text
Name: Masum, Age: 23
```

### Mistake 2: Using the Wrong Specifier

```python
name = "Masum"

print("Age: %d" % name)
```

**Output:**

```text
TypeError: %d format: a real number is required, not str
```

**সমস্যা:** String Value-এর জন্য `%d` ব্যবহার করা হয়েছে।

**Correct Code:**

```python
name = "Masum"

print("Name: %s" % name)
```

**Output:**

```text
Name: Masum
```

### Mistake 3: Forgetting Double Percentage

```python
result = 85

print("Result: %d%" % result)
```

**Output:**

```text
ValueError: incomplete format
```

**সমস্যা:** Percentage Symbol Display করার জন্য `%%` ব্যবহার করা হয়নি।

**Correct Code:**

```python
result = 85

print("Result: %d%%" % result)
```

**Output:**

```text
Result: 85%
```

### Mistake 4: Wrong Number of Values

```python
name = "Masum"

print("Name: %s, Age: %d" % (name,))
```

**Output:**

```text
TypeError: not enough arguments for format string
```

**সমস্যা:** দুটি Placeholder-এর জন্য একটি Value দেওয়া হয়েছে।

**Correct Code:**

```python
name = "Masum"
age = 23

print("Name: %s, Age: %d" % (name, age))
```

**Output:**

```text
Name: Masum, Age: 23
```

### Mistake 5: Confusing Precision

```python
number = 12.5678

print("%.2f" % number)
print("%.4f" % number)
```

**Output:**

```text
12.57
12.5678
```

**মনে রাখবে:** `.2f` এবং `.4f` নির্ধারণ করে Decimal-এর পরে কতটি Digit Display হবে।

---

## 25. Practice Exercises

### Exercise 1: Basic String Formatting

নিচের Variable ব্যবহার করে Name Display করো।

```python
name = "Masum"
```

**Expected Output:**

```text
Hello, Masum!
```

### Exercise 2: Integer Formatting

নিচের Variable ব্যবহার করে Age Display করো।

```python
age = 23
```

**Expected Output:**

```text
Age: 23
```

### Exercise 3: Multiple Values

Name এবং Age একসঙ্গে Display করো।

```python
name = "Rahim"
age = 22
```

**Expected Output:**

```text
My name is Rahim and I am 22 years old.
```

### Exercise 4: Decimal Formatting

Number-টিকে দুই Decimal Places-এ Display করো।

```python
number = 45.6789
```

**Expected Output:**

```text
45.68
```

### Exercise 5: Thousands Separator

Number-এ Comma যোগ করো।

```python
number = 5000000
```

**Expected Output:**

```text
5,000,000
```

### Exercise 6: Percentage Formatting

Percentage Symbol ব্যবহার করে Output তৈরি করো।

```python
result = 85
```

**Expected Output:**

```text
Result: 85%
```

### Exercise 7: Left Alignment

Text-কে 15 Width-এর মধ্যে Left Alignment করো।

```python
name = "Python"
```

**Expected Output:**

```text
Python
```

### Exercise 8: Zero Padding

Number-টিকে পাঁচটি Character Width-এর মধ্যে Zero Padding দিয়ে Display করো।

```python
number = 25
```

**Expected Output:**

```text
00025
```

### Exercise 9: Scientific Notation

Number-টিকে Scientific Notation-এ দুই Decimal Places-এ Display করো।

```python
number = 1234567
```

**Expected Output:**

```text
1.23e+06
```

### Exercise 10: Predict the Output

নিচের Code-এর Output নিজে Predict করো।

```python
name = "Masum"
age = 23
marks = 87.567

print("Name: %s" % name)
print("Age: %d" % age)
print("Marks: %.2f" % marks)
print("Result: %d%%" % 85)
```

**Expected Output:**

```text
Name: Masum
Age: 23
Marks: 87.57
Result: 85%
```

### Exercise 11: Predict the Output

```python
number = 12345.678

print("%.1f" % number)
print("%,.2f" % number)
print("%.2e" % number)
print("%05d" % 42)
```

**Expected Output:**

```text
12345.7
12,345.68
1.23e+04
00042
```

### Exercise 12: Practical Programming

Old-Style Formatting ব্যবহার করে একটি Student Information Program তৈরি করো।

Student-এর Name, Department, Semester এবং CGPA Display করতে হবে।

**Expected Output:**

```text
Student Information
---------------------------
Name: Masum
Department: CSE
Semester: 9
CGPA: 3.95
```

---

## 26. Chapter Summary

এই Topic-এ আমরা Python-এর Old-Style String Formatting শিখেছি।

| Topic | Description |
|---|---|
| Old-Style Formatting | `%` Operator ব্যবহার করে Formatting |
| `%s` | String Formatting |
| `%d` | Integer Formatting |
| `%f` | Float Formatting |
| `%e` | Scientific Notation |
| `%x` | Hexadecimal |
| `%o` | Octal |
| `%%` | Percentage Symbol |
| Width | নির্দিষ্ট Character Space |
| Alignment | Left এবং Right Alignment |
| Zero Padding | Number-এর আগে Zero যোগ করা |
| Dictionary Formatting | Dictionary Key ব্যবহার করা |

**মনে রাখবে:**

```python
name = "Masum"
age = 23
cgpa = 3.95

message = "Name: %s, Age: %d, CGPA: %.2f" % (name, age, cgpa)

print(message)
```

**Output:**

```text
Name: Masum, Age: 23, CGPA: 3.95
```

Old-Style Formatting-এর মূল বিষয় হলো `%` Operator এবং বিভিন্ন Format Specifier ব্যবহার করে String-এর মধ্যে Value বসানো।

---

## 27. Self-Assessment Checklist

- [ ] Old-Style String Formatting কী বুঝতে পেরেছি।
- [ ] `%` Operator ব্যবহার করতে পারি।
- [ ] `%s` এবং `%d` ব্যবহার করতে পারি।
- [ ] `%f` দিয়ে Decimal Formatting করতে পারি।
- [ ] Multiple Values Format করতে পারি।
- [ ] Thousands Separator ব্যবহার করতে পারি।
- [ ] Percentage Symbol Display করতে পারি।
- [ ] String Alignment করতে পারি।
- [ ] Zero Padding ব্যবহার করতে পারি।
- [ ] Scientific Notation ব্যবহার করতে পারি।
- [ ] Hexadecimal এবং Octal Formatting বুঝি।
- [ ] Dictionary Formatting করতে পারি।
- [ ] Old-Style Formatting-এর Common Errors বুঝতে পারি।
- [ ] f-String এবং format() Method-এর সঙ্গে পার্থক্য বুঝতে পারি।

---

## 28. Next Topic

পরবর্তী Topic:

**40. String Encoding and Unicode Basics**

পরবর্তী File:

`40_String_Encoding_and_Unicode_Basics.md`

এখানে আমরা Character Encoding, Unicode, ASCII, UTF-8, UTF-16 এবং Python-এ বিভিন্ন Language-এর Text কীভাবে সংরক্ষণ ও কাজ করে তা শিখব।
