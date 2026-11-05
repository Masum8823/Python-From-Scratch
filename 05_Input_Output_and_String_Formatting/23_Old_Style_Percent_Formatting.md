# 23. Old-Style Percent Formatting in Python

## 1. Introduction to `%` Formatting

Python-এ string-এর মধ্যে variable বা value বসানোর একটি পুরোনো পদ্ধতি হলো **percent (`%`) formatting**।

এই পদ্ধতিতে string-এর মধ্যে `%s`, `%d`, `%f`-এর মতো format specifier ব্যবহার করা হয়। পরে `%` operator-এর মাধ্যমে value দেওয়া হয়।

### Example

```python
name = "Masum"
age = 22

print("My name is %s and I am %d years old." % (name, age))
```

Output:

```text
My name is Masum and I am 22 years old.
```

এখানে:

- `%s` string value বসিয়েছে।
- `%d` integer value বসিয়েছে।
- `% (name, age)` value-গুলো সরবরাহ করেছে।

**মনে রাখবে:** `%` formatting পুরোনো পদ্ধতি। নতুন Python code-এ সাধারণত f-string বেশি সহজ ও readable।

## 2. Basic Syntax

### Syntax

```python
"format string" % values
```

এখানে:

- Format string-এর মধ্যে format specifier থাকে।
- `%` operator-এর পরে value দেওয়া হয়।
- একাধিক value হলে সাধারণত tuple ব্যবহার করা হয়।

### Example

```python
name = "Python"

print("I am learning %s." % name)
```

Output:

```text
I am learning Python.
```

একটি value থাকলে এখানে tuple প্রয়োজন হয়নি।

### Multiple Values

```python
name = "Masum"
department = "CSE"

print("Name: %s, Department: %s" % (name, department))
```

Output:

```text
Name: Masum, Department: CSE
```

একাধিক value-এর ক্ষেত্রে tuple-এর value-গুলো format specifier-এর ক্রম অনুযায়ী বসে।

## 3. Common Format Specifiers

Percent formatting-এ বিভিন্ন data type-এর জন্য বিভিন্ন specifier ব্যবহার করা হয়।

| Specifier | ব্যবহার |
|---|---|
| `%s` | String representation |
| `%d` | Integer বা decimal integer |
| `%i` | Integer |
| `%f` | Floating-point number |
| `%e` | Scientific notation |
| `%g` | General numeric formatting |
| `%x` | Hexadecimal, lowercase |
| `%X` | Hexadecimal, uppercase |
| `%o` | Octal |
| `%%` | Literal `%` character |

### Example

```python
name = "Masum"
age = 22
price = 125.5

print("Name: %s" % name)
print("Age: %d" % age)
print("Price: %f" % price)
```

Output:

```text
Name: Masum
Age: 22
Price: 125.500000
```

`%f` সাধারণত decimal point-এর পরে ছয়টি digit দেখায়, যদি precision নির্দিষ্ট না করা হয়।

## 4. Formatting Strings with `%s`

`%s` string representation বসানোর জন্য ব্যবহৃত হয়।

### Example 1: String Variable

```python
name = "Masum"

print("Hello, %s!" % name)
```

Output:

```text
Hello, Masum!
```

### Example 2: Multiple Strings

```python
first_name = "Abdulla"
last_name = "Masum"

print("Name: %s %s" % (first_name, last_name))
```

Output:

```text
Name: Abdulla Masum
```

### Example 3: Other Data Types

`%s` string representation ব্যবহার করতে পারে, তাই শুধু string variable-ই দিতে হবে এমন নয়।

```python
marks = 95

print("Marks: %s" % marks)
```

Output:

```text
Marks: 95
```

তবে integer-এর জন্য `%d` এবং floating-point value-এর জন্য `%f` ব্যবহার করলে code-এর উদ্দেশ্য আরও পরিষ্কার হয়।

## 5. Formatting Integers with `%d` and `%i`

`%d` ও `%i` integer value format করার জন্য ব্যবহৃত হয়।

### Example

```python
age = 22
marks = 95

print("Age: %d" % age)
print("Marks: %i" % marks)
```

Output:

```text
Age: 22
Marks: 95
```

### Negative Integer

```python
number = -45

print("Number: %d" % number)
```

Output:

```text
Number: -45
```

**সতর্কতা:** `%d`-এর জন্য integer-compatible value দিতে হবে। যেমন, `%d` দিয়ে float format করার চেষ্টা করলে Python integer conversion করতে পারে; তবে এমন আচরণের ওপর নির্ভর না করে প্রয়োজন হলে আগে স্পষ্টভাবে `int()` ব্যবহার করো।

## 6. Formatting Floating-Point Numbers with `%f`

`%f` floating-point number format করে।

### Example 1

```python
price = 125.5

print("Price: %f" % price)
```

Output:

```text
Price: 125.500000
```

### Example 2: Two Decimal Places

```python
price = 125.5678

print("Price: %.2f" % price)
```

Output:

```text
Price: 125.57
```

### Example 3: Three Decimal Places

```python
number = 12.34567

print("%.3f" % number)
```

Output:

```text
12.346
```

এখানে `.2f` দুইটি এবং `.3f` তিনটি decimal places দেখায়।

**মনে রাখবে:** Formatting-এর কারণে মূল variable-এর value পরিবর্তন হয় না। শুধু output-এর representation তৈরি হয়।

## 7. Field Width and Precision

Percent formatting-এ field width এবং precision একসঙ্গে ব্যবহার করা যায়।

### Syntax

```python
%[width].[precision]f
```

এখানে:

- `width` হলো output field-এর minimum width।
- `precision` হলো floating-point number-এর decimal places।

### Example 1: Width

```python
number = 42

print("|%10d|" % number)
```

Output:

```text
|        42|
```

এখানে field width 10, তাই সংখ্যাটি ডানদিকে align হয়েছে।

### Example 2: Precision

```python
number = 12.34567

print("%.2f" % number)
```

Output:

```text
12.35
```

### Example 3: Width and Precision

```python
number = 12.34567

print("|%10.2f|" % number)
```

Output:

```text
|     12.35|
```

এখানে field width 10 এবং decimal places 2।

## 8. Left Alignment and Right Alignment

Percent formatting-এ সাধারণভাবে value right-aligned থাকে। বামদিকে align করতে `-` flag ব্যবহার করা যায়।

### Example

```python
name = "Python"

print("|%10s|" % name)
print("|%-10s|" % name)
```

Output:

```text
|    Python|
|Python    |
```

এখানে:

- `%10s` → width 10, right alignment
- `%-10s` → width 10, left alignment

এই পদ্ধতি table বা column সাজানোর কাজে ব্যবহার করা যায়।

## 9. Zero Padding

Integer-এর আগে zero দেখাতে width-এর আগে `0` ব্যবহার করা যায়।

### Example

```python
number = 42

print("%05d" % number)
```

Output:

```text
00042
```

এখানে `5` হলো field width এবং `0` হলো zero-padding flag।

### Another Example

```python
number = 87

print("%06d" % number)
```

Output:

```text
000087
```

Zero padding মূল number পরিবর্তন করে না; শুধু output-এর format পরিবর্তন করে।

## 10. Sign Formatting

Number-এর sign স্পষ্টভাবে দেখানোর জন্য `+` flag ব্যবহার করা যায়।

### Example

```python
positive = 42
negative = -42

print("%+d" % positive)
print("%+d" % negative)
```

Output:

```text
+42
-42
```

### Space for Positive Numbers

```python
print("% d" % 42)
print("% d" % -42)
```

Output:

```text
 42
-42
```

এখানে space flag positive number-এর আগে একটি space রাখে; negative number-এর ক্ষেত্রে minus sign দেখায়।

## 11. Thousand Separators

বড় সংখ্যাকে comma দিয়ে group করার জন্য `,` flag ব্যবহার করা যায়।

### Example

```python
population = 1250000

print("%,d" % population)
```

Output:

```text
1,250,000
```

### Float Example

```python
amount = 1234567.891

print("%,.2f" % amount)
```

Output:

```text
1,234,567.89
```

এখানে comma দিয়ে thousand grouping এবং `.2f` দিয়ে দুই decimal places দেখানো হয়েছে।

## 12. Scientific Notation

খুব বড় বা খুব ছোট number scientific notation-এ দেখানো যায়।

### Example

```python
number = 1234567.89

print("%e" % number)
print("%.2e" % number)
```

Output:

```text
1.234568e+06
1.23e+06
```

`%e` scientific notation ব্যবহার করে। `%.2e` decimal point-এর পরে দুইটি digit দেখায়।

### Uppercase Scientific Notation

```python
number = 1234567.89

print("%.2E" % number)
```

Output:

```text
1.23E+06
```

`%E` uppercase `E` ব্যবহার করে।

## 13. General Numeric Formatting with `%g`

`%g` significant digits-এর ভিত্তিতে number format করে। প্রয়োজন অনুযায়ী এটি fixed-point অথবা scientific notation বেছে নিতে পারে।

### Example

```python
number = 123.456

print("%g" % number)
print("%.4g" % number)
```

Output:

```text
123.456
123.5
```

এখানে `%.4g` মোট চারটি significant digit ব্যবহার করে।

**পার্থক্য:**

- `%.2f` → decimal point-এর পরে দুইটি digit।
- `%.4g` → মোট চারটি significant digit।

## 14. Formatting Percentages

Percent formatting-এ percentage দেখানোর জন্য value-কে আগে 100 দিয়ে গুণ করে `%` character যোগ করা যায়।

### Example

```python
score = 0.875

print("Percentage: %.2f%%" % (score * 100))
```

Output:

```text
Percentage: 87.50%
```

এখানে:

- `%.2f` দুই decimal places দেখায়।
- `%%` literal `%` character দেখায়।
- `score * 100` ratio-কে percentage value-তে রূপান্তর করে।

**গুরুত্বপূর্ণ:** `%` formatting-এ `%.2%` নামে percentage format specifier নেই। তাই ratio-কে percentage হিসেবে দেখাতে সাধারণত 100 দিয়ে গুণ করে `%%` ব্যবহার করতে হয়।

## 15. Formatting Hexadecimal and Octal Numbers

Integer-কে বিভিন্ন number system-এ দেখানো যায়।

### Hexadecimal

```python
number = 255

print("%x" % number)
print("%X" % number)
```

Output:

```text
ff
FF
```

### Octal

```python
number = 10

print("%o" % number)
```

Output:

```text
12
```

এখানে:

- `%x` → lowercase hexadecimal
- `%X` → uppercase hexadecimal
- `%o` → octal

## 16. Using `%%` for a Literal Percent Sign

Format string-এর মধ্যে সরাসরি `%` character দেখাতে `%%` ব্যবহার করতে হয়।

### Example

```python
discount = 20

print("Discount: %d%%" % discount)
```

Output:

```text
Discount: 20%
```

এখানে প্রথম `%d` integer বসিয়েছে এবং `%%` একটি literal percent sign দেখিয়েছে।

## 17. Using Multiple Values

একাধিক value format করার সময় সাধারণত tuple ব্যবহার করা হয়।

### Example

```python
name = "Masum"
age = 22
cgpa = 3.95

print("Name: %s, Age: %d, CGPA: %.2f" % (name, age, cgpa))
```

Output:

```text
Name: Masum, Age: 22, CGPA: 3.95
```

প্রতিটি value format specifier-এর ক্রম অনুযায়ী বসেছে।

### Common Mistake

```python
# print("%s %d" % ("Masum"))
```

এখানে দুটি specifier থাকলেও value দেওয়া হয়েছে একটি। তাই `TypeError` হবে।

Correct version:

```python
print("%s %d" % ("Masum", 22))
```

Output:

```text
Masum 22
```

## 18. Practical Program: Student Result

```python
name = "Masum"
obtained = 425
total = 500

percentage = (obtained / total) * 100

print("=" * 35)
print("%25s" % "STUDENT RESULT")
print("=" * 35)
print("%-15s %s" % ("Name:", name))
print("%-15s %d/%d" % ("Marks:", obtained, total))
print("%-15s %.2f%%" % ("Percentage:", percentage))
print("=" * 35)
```

Output:

```text
===================================
          STUDENT RESULT
===================================
Name:           Masum
Marks:          425/500
Percentage:     85.00%
===================================
```

এই program-এ `%s`, `%d`, `%.2f`, `%%` এবং alignment একসঙ্গে ব্যবহার করা হয়েছে।

## 19. Common Errors and Pitfalls

### Error 1: Wrong Number of Values

```python
# print("%s %d" % ("Masum"))
```

দুটি specifier-এর জন্য প্রয়োজনীয় value না থাকায় `TypeError` হবে।

### Error 2: Wrong Data Type

```python
# print("%d" % "Python")
```

`"Python"` integer নয়, তাই `%d` দিয়ে format করলে `TypeError` হবে।

### Error 3: Forgetting the Tuple

```python
name = "Masum"
age = 22

print("%s %d" % (name, age))
```

একাধিক value হলে tuple ব্যবহার করা সহজ ও পরিষ্কার।

### Error 4: Forgetting `%%`

```python
discount = 20

print("%d%%" % discount)
```

Literal `%` character দেখানোর সঠিক পদ্ধতি হলো `%%`।

### Error 5: Confusing `%` Formatting with `%` Arithmetic

```python
print("%d" % 10)
print(10 % 3)
```

Output:

```text
10
1
```

প্রথম লাইনে `%` formatting-এর অংশ। দ্বিতীয় লাইনে `%` হলো modulo operator, যা remainder বের করে।

## 20. `%` Formatting vs `.format()` vs f-Strings

| Feature | `%` formatting | `.format()` | f-string |
|---|---|---|---|
| Example | `"%s" % name` | `"{}".format(name)` | `f"{name}"` |
| Readability | পুরোনো style | তুলনামূলক flexible | সাধারণত সবচেয়ে সহজ |
| Multiple values | Tuple প্রায়ই ব্যবহৃত হয় | Positional/named arguments | সরাসরি variable |
| Numeric formatting | Supported | Supported | Supported |
| Recommended for new code | সাধারণত নয় | প্রয়োজন অনুযায়ী | সাধারণত হ্যাঁ |

### Same Output in Three Ways

```python
name = "Masum"
marks = 95

# Percent formatting
print("Name: %s, Marks: %d" % (name, marks))

# str.format()
print("Name: {}, Marks: {}".format(name, marks))

# f-string
print(f"Name: {name}, Marks: {marks}")
```

তিনটি statement-ই একই output দেয়:

```text
Name: Masum, Marks: 95
Name: Masum, Marks: 95
Name: Masum, Marks: 95
```

**Recommendation:** নতুন project-এ সাধারণত f-string ব্যবহার করো। তবে পুরোনো code বুঝতে `%` formatting সম্পর্কে ধারণা রাখো।

## 21. Practice Exercises

### Exercise 1: Basic String

`name = "Masum"` ব্যবহার করে `%s` দিয়ে greeting দেখাও।

### Exercise 2: Integer and Float

`age = 22` এবং `cgpa = 3.956` ব্যবহার করে integer ও float format করো।

### Exercise 3: Decimal Places

`price = 125.6789`-কে দুই decimal places-এ দেখাও।

### Exercise 4: Zero Padding

`number = 42`-কে পাঁচ character width-এ zero padding দিয়ে দেখাও।

### Exercise 5: Alignment

`"Python"`-কে 10-character width-এ left এবং right-align করো।

### Exercise 6: Percentage

`score = 0.875`-কে `87.50%` হিসেবে দেখাও।

### Exercise 7: Thousand Separator

`population = 2500000`-কে comma separator দিয়ে দেখাও।

### Exercise 8: Output Prediction

```python
name = "Ritu"
marks = 95

print("%s scored %d" % (name, marks))
print("%.2f" % 12.345)
print("%05d" % 42)
print("%d%%" % 20)
```

Output কী হবে?

### Exercise 9: Scientific Notation

`number = 1234567.89`-কে দুই decimal places-সহ scientific notation-এ দেখাও।

### Exercise 10: Mini Challenge

একটি student result তৈরি করো, যাতে student name, obtained marks, total marks এবং percentage থাকবে। `%` formatting ব্যবহার করে percentage দুই decimal places-এ দেখাও।

## 22. Practice Answer Key

### Answer 1

```python
name = "Masum"

print("Hello, %s!" % name)
```

### Answer 2

```python
age = 22
cgpa = 3.956

print("Age: %d" % age)
print("CGPA: %.2f" % cgpa)
```

### Answer 3

```python
price = 125.6789

print("%.2f" % price)
```

Output:

```text
125.68
```

### Answer 4

```python
number = 42

print("%05d" % number)
```

Output:

```text
00042
```

### Answer 5

```python
name = "Python"

print("|%-10s|" % name)
print("|%10s|" % name)
```

### Answer 6

```python
score = 0.875

print("%.2f%%" % (score * 100))
```

Output:

```text
87.50%
```

### Answer 7

```python
population = 2500000

print("%,d" % population)
```

Output:

```text
2,500,000
```

### Answer 8

Output:

```text
Ritu scored 95
12.35
00042
20%
```

### Answer 9

```python
number = 1234567.89

print("%.2e" % number)
```

Output:

```text
1.23e+06
```

### Answer 10

```python
name = "Masum"
obtained = 425
total = 500

percentage = (obtained / total) * 100

print("Student: %s" % name)
print("Marks: %d/%d" % (obtained, total))
print("Percentage: %.2f%%" % percentage)
```

Output:

```text
Student: Masum
Marks: 425/500
Percentage: 85.00%
```

## 23. Chapter Summary

- `%` formatting Python-এর পুরোনো string formatting পদ্ধতি।
- `%s` string representation এবং `%d` integer format করতে ব্যবহৃত হয়।
- `%f` floating-point number format করে।
- `%.2f` দুই decimal places দেখায়।
- `%10s` right alignment এবং `%-10s` left alignment করে।
- `%05d` zero padding ব্যবহার করে।
- `%,d` বড় integer-এ comma separator দেখাতে পারে।
- `%%` literal percent sign দেখায়।
- `%e` scientific notation এবং `%x` hexadecimal format করতে পারে।
- নতুন Python code-এ সাধারণত f-string বেশি readable।

## 24. Self-Assessment Checklist

- [ ] `%` formatting-এর basic syntax বুঝি।
- [ ] `%s`, `%d` এবং `%f` ব্যবহার করতে পারি।
- [ ] Precision ও field width ব্যবহার করতে পারি।
- [ ] Left/right alignment ও zero padding করতে পারি।
- [ ] Percentage ও thousand separator format করতে পারি।
- [ ] `%%` দিয়ে literal percent sign দেখাতে পারি।
- [ ] `%` formatting এবং modulo operator-এর পার্থক্য বুঝি।
- [ ] `%` formatting, `.format()` ও f-string-এর পার্থক্য বুঝি।

**Next Topic:** `24_Formatting_Percentages_Currency_and_Large_Numbers.md` — এখানে percentage, currency এবং বড় number বাস্তব program-এ কীভাবে পরিষ্কারভাবে format করতে হয়, তা শিখব।