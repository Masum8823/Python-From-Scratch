
# 37. Formatting Numbers inside Strings in Python

## 1. Introduction to Number Formatting

Python-এ Number-কে সুন্দরভাবে এবং নির্দিষ্ট Format-এ Display করার পদ্ধতিকে **Number Formatting** বলা হয়।

Number Formatting ব্যবহার করে আমরা:

- Decimal Places নির্দিষ্ট করতে পারি।
- বড় Number-এ Comma ব্যবহার করতে পারি।
- Percentage দেখাতে পারি।
- Number-এর আগে বা পরে Symbol বসাতে পারি।
- Number-কে নির্দিষ্ট Width-এর মধ্যে সাজাতে পারি।

Python-এ f-String ব্যবহার করে খুব সহজে Number Formatting করা যায়।

### Example

```python
price = 125.5678

print(f"Price: {price:.2f}")
```

**Output:**

```text
Price: 125.57
```

এখানে `.2f` ব্যবহার করে Decimal-এর পরে দুইটি digit দেখানো হয়েছে।

---

## 2. Formatting Decimal Places

Decimal Number-এর পরে কতটি digit দেখানো হবে, তা নির্ধারণ করতে `.nf` ব্যবহার করা হয়।

এখানে `n` হলো Decimal Places-এর সংখ্যা।

### Syntax

```python
f"{number:.nf}"
```

### Example 1: Two Decimal Places

```python
price = 99.5678

print(f"{price:.2f}")
```

**Output:**

```text
99.57
```

### Example 2: Three Decimal Places

```python
number = 12.345678

print(f"{number:.3f}")
```

**Output:**

```text
12.346
```

### Example 3: No Decimal Places

```python
number = 45.89

print(f"{number:.0f}")
```

**Output:**

```text
46
```

এখানে `.0f` ব্যবহার করায় Decimal-এর পরে কোনো digit দেখানো হয়নি।

**মনে রাখবে:** Number Formatting-এর সময় প্রয়োজন অনুযায়ী rounding করা হয়।

---

## 3. Thousands Separator

বড় Number সহজে পড়ার জন্য Comma (`,`) ব্যবহার করা যায়।

### Syntax

```python
f"{number:,}"
```

### Example 1: Integer

```python
number = 1000000

print(f"{number:,}")
```

**Output:**

```text
1,000,000
```

### Example 2: Float

```python
number = 1234567.89

print(f"{number:,.2f}")
```

**Output:**

```text
1,234,567.89
```

এখানে:

- `,` Thousands Separator যোগ করেছে।
- `.2f` Decimal-এর পরে দুইটি digit দেখিয়েছে।

---

## 4. Formatting Percentage

কোনো Decimal Value-কে Percentage হিসেবে Display করতে `%` ব্যবহার করা হয়।

### Syntax

```python
f"{number:.2%}"
```

### Example 1

```python
result = 0.85

print(f"Percentage: {result:.2%}")
```

**Output:**

```text
Percentage: 85.00%
```

### Example 2

```python
marks = 0.7568

print(f"Result: {marks:.1%}")
```

**Output:**

```text
Result: 75.7%
```

**ব্যাখ্যা:**

- `0.85` কে `85%` হিসেবে দেখানো হয়েছে।
- `.2%` Decimal-এর পরে দুইটি digit দেখিয়েছে।
- `.1%` Decimal-এর পরে একটি digit দেখিয়েছে।

**Important:** Percentage Formatting নিজেই Number-কে `100` দিয়ে গুণ করে `%` যোগ করে।

---

## 5. Formatting Numbers with Fixed Width

Number-কে নির্দিষ্ট Width-এর মধ্যে Display করতে Width Specifier ব্যবহার করা যায়।

### Syntax

```python
f"{number:width}"
```

### Example

```python
number = 42

print(f"{number:5}")
print(f"{number:10}")
```

**Output:**

```text
   42
        42
```

এখানে Number-এর বাম পাশে Space যোগ করে নির্দিষ্ট Width তৈরি করা হয়েছে।

---

## 6. Number Alignment

f-String ব্যবহার করে Number-কে Left, Right অথবা Center Alignment করা যায়।

### Example 1: Left Alignment

```python
number = 42

print(f"{number:<10}")
```

**Output:**

```text
42
```

এখানে Number বাম পাশে থাকে এবং ডান পাশে Space যোগ হয়।

### Example 2: Right Alignment

```python
number = 42

print(f"{number:>10}")
```

**Output:**

```text
        42
```

এখানে Number ডান পাশে থাকে এবং বাম পাশে Space যোগ হয়।

### Example 3: Center Alignment

```python
number = 42

print(f"{number:^10}")
```

**Output:**

```text
    42
```

এখানে Number মাঝখানে থাকে।

| Symbol | কাজ |
|---|---|
| `<` | Left Alignment |
| `>` | Right Alignment |
| `^` | Center Alignment |

---

## 7. Formatting Numbers with Custom Fill Characters

Alignment-এর পাশাপাশি Padding Character-ও নির্ধারণ করা যায়।

### Example 1: Using *

```python
number = 42

print(f"{number:*<10}")
print(f"{number:*>10}")
print(f"{number:*^10}")
```

**Output:**

```text
42********
********42
****42****
```

এখানে:

- `*<10` → ডান পাশে `*` যোগ করে।
- `*>10` → বাম পাশে `*` যোগ করে।
- `*^10` → দুই পাশে `*` যোগ করে Center Alignment করে।

### Example 2: Using Zero

```python
number = 42

print(f"{number:0>5}")
```

**Output:**

```text
00042
```

এখানে Number-এর বাম পাশে Zero যোগ হয়েছে।

---

## 8. Formatting Positive and Negative Signs

Number-এর আগে Positive বা Negative Sign দেখানোর জন্য `+` এবং `-` ব্যবহার করা যায়।

### Example 1: Always Show Sign

```python
a = 25
b = -25

print(f"{a:+}")
print(f"{b:+}")
```

**Output:**

```text
+25
-25
```

এখানে `+` ব্যবহার করায় Positive এবং Negative উভয় Number-এর Sign দেখানো হয়েছে।

### Example 2: Show Negative Sign Only

```python
a = 25
b = -25

print(f"{a:-}")
print(f"{b:-}")
```

**Output:**

```text
25
-25
```

এখানে Positive Number-এর আগে কোনো Sign দেখানো হয়নি।

---

## 9. Formatting Large Numbers

বড় Number-কে Scientific Notation-এ Display করা যায়।

এক্ষেত্রে `e` ব্যবহার করা হয়।

### Example

```python
number = 1234567

print(f"{number:e}")
```

**Output:**

```text
1.234567e+06
```

Decimal Places নির্দিষ্ট করেও Scientific Notation ব্যবহার করা যায়।

```python
number = 1234567

print(f"{number:.2e}")
```

**Output:**

```text
1.23e+06
```

এখানে `.2e` ব্যবহার করে Decimal-এর পরে দুইটি digit দেখানো হয়েছে।

---

## 10. Formatting Currency Values

টাকার Amount সুন্দরভাবে Display করতে Number Formatting ব্যবহার করা যায়।

### Example

```python
price = 125000.567

print(f"Price: Tk {price:,.2f}")
```

**Output:**

```text
Price: Tk 125,000.57
```

এখানে:

- `Tk` Currency Label হিসেবে ব্যবহার হয়েছে।
- `,` Thousands Separator যোগ করেছে।
- `.2f` Decimal-এর পরে দুইটি digit দেখিয়েছে।

---

## 11. Combining Multiple Formatting Options

একটি Format Specifier-এর মধ্যে একাধিক Formatting Option ব্যবহার করা যায়।

### General Syntax

```python
f"{number:fill alignment sign width separator precision type}"
```

সব Option একসঙ্গে ব্যবহার করতে হবে এমন নয়। প্রয়োজন অনুযায়ী ব্যবহার করা যায়।

### Example

```python
number = 12345.678

print(f"{number:*>15,.2f}")
```

**Output:**

```text
*****12,345.68
```

এখানে:

- `*` Padding Character।
- `>` Right Alignment।
- `15` Total Width।
- `,` Thousands Separator।
- `.2f` দুই Decimal Places।

---

## 12. Practical Example: Student Result

```python
name = "Masum"
marks = 87.567
percentage = 0.87567

print(f"Student: {name}")
print(f"Marks: {marks:.2f}")
print(f"Percentage: {percentage:.2%}")
```

**Output:**

```text
Student: Masum
Marks: 87.57
Percentage: 87.57%
```

এখানে Student-এর Marks এবং Percentage সুন্দরভাবে Format করা হয়েছে।

---

## 13. Practical Example: Product Price List

```python
products = [
    ("Keyboard", 1250.567),
    ("Mouse", 750.5),
    ("Monitor", 12500.999)
]

print("Product".ljust(15), "Price".rjust(12))
print("-" * 27)

for name, price in products:
    print(name.ljust(15), f"{price:>12,.2f}")
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

- `ljust()` Product Name সাজিয়েছে।
- `>12` Price-কে Right Alignment করেছে।
- `,` Thousands Separator যোগ করেছে।
- `.2f` দুই Decimal Places দেখিয়েছে।

---

## 14. Important Format Specifiers

| Format Specifier | কাজ |
|---|---|
| `.2f` | দুই Decimal Places |
| `.3f` | তিন Decimal Places |
| `,` | Thousands Separator |
| `.2%` | Percentage |
| `>10` | Right Alignment |
| `<10` | Left Alignment |
| `^10` | Center Alignment |
| `0>5` | Zero Padding |
| `+` | সব Number-এর Sign দেখায় |
| `e` | Scientific Notation |

---

## 15. Important Rules

1. f-String-এর মধ্যে Formatting করতে Colon (`:`) ব্যবহার করতে হয়।
2. `.2f` Decimal-এর পরে দুইটি digit দেখায়।
3. `,` বড় Number-এ Thousands Separator যোগ করে।
4. `%` Decimal Value-কে Percentage-এ রূপান্তর করে।
5. `<` Left Alignment করে।
6. `>` Right Alignment করে।
7. `^` Center Alignment করে।
8. Custom Padding Character ব্যবহার করা যায়।
9. `+` Positive এবং Negative উভয় Number-এর Sign দেখায়।
10. `.2e` Scientific Notation-এ দুই Decimal Places দেখায়।
11. Number Formatting করলে Original Variable-এর Value পরিবর্তন হয় না।
12. Formatting-এর ফলে তৈরি Output একটি String হয়।

---

## 16. Common Mistakes

### Mistake 1: Confusing Decimal Places

```python
number = 12.5678

print(f"{number:.2f}")
print(f"{number:.4f}")
```

**Output:**

```text
12.57
12.5678
```

**মনে রাখবে:** `.2f` এবং `.4f`-এর মধ্যে পার্থক্য হলো Decimal-এর পরে কতটি digit দেখানো হবে।

### Mistake 2: Forgetting Percentage Conversion

```python
value = 0.75

print(f"{value:.2f}")
print(f"{value:.2%}")
```

**Output:**

```text
0.75
75.00%
```

**ব্যাখ্যা:** `.2%` নিজেই Value-কে `100` দিয়ে গুণ করে Percentage তৈরি করে।

### Mistake 3: Using Wrong Alignment Symbol

```python
number = 50

print(f"{number:<8}")
print(f"{number:>8}")
```

**Output:**

```text
50
      50
```

**মনে রাখবে:**

- `<` = Left
- `>` = Right

### Mistake 4: Using Comma Incorrectly

```python
number = 1000000

print(f"{number:,}")
```

**Output:**

```text
1,000,000
```

Comma ব্যবহারের জন্য Format Specifier-এর মধ্যে `,` দিতে হবে।

---

## 17. Practice Exercises

### Exercise 1: Decimal Formatting

নিচের Number-কে দুই Decimal Places-এ দেখাও।

```python
number = 45.6789
```

**Expected Output:**

```text
45.68
```

### Exercise 2: Thousands Separator

নিচের Number-এ Comma যোগ করো।

```python
number = 5000000
```

**Expected Output:**

```text
5,000,000
```

### Exercise 3: Percentage Formatting

নিচের Value-কে Percentage হিসেবে দেখাও।

```python
result = 0.8567
```

**Expected Output:**

```text
85.67%
```

### Exercise 4: Zero Padding

Number-টিকে পাঁচটি digit-এর Format-এ দেখাও।

```python
number = 25
```

**Expected Output:**

```text
00025
```

### Exercise 5: Currency Formatting

নিচের Price-কে Comma এবং দুই Decimal Places ব্যবহার করে Display করো।

```python
price = 125000.567
```

**Expected Output:**

```text
Tk 125,000.57
```

### Exercise 6: Predict the Output

```python
number = 12345.678

print(f"{number:.1f}")
print(f"{number:,.2f}")
print(f"{number:.2%}")
print(f"{number:*>12,.1f}")
```

**Expected Output:**

```text
12345.7
12,345.68
1234567.80%
*****12,345.7
```

---

## 18. Chapter Summary

এই topic-এ আমরা Python-এর f-String ব্যবহার করে Number Formatting শিখেছি।

| Formatting | Example | কাজ |
|---|---|---|
| Decimal | `:.2f` | দুই Decimal Places |
| Thousands | `:,` | Comma যোগ করে |
| Percentage | `:.2%` | Percentage দেখায় |
| Left | `:<10` | বাম পাশে রাখে |
| Right | `:>10` | ডান পাশে রাখে |
| Center | `:^10` | মাঝখানে রাখে |
| Zero Padding | `:0>5` | Zero যোগ করে |
| Scientific | `:.2e` | Scientific Notation |

**মনে রাখবে:**

```python
price = 125000.567

print(f"Tk {price:,.2f}")
```

**Output:**

```text
Tk 125,000.57
```

---

## 19. Self-Assessment Checklist

- [ ] Number Formatting কী বুঝতে পেরেছি।
- [ ] Decimal Places Format করতে পারি।
- [ ] Thousands Separator ব্যবহার করতে পারি।
- [ ] Percentage Format করতে পারি।
- [ ] Number Alignment করতে পারি।
- [ ] Custom Padding ব্যবহার করতে পারি।
- [ ] Positive এবং Negative Sign Format করতে পারি।
- [ ] Scientific Notation ব্যবহার করতে পারি।
- [ ] Currency Value Format করতে পারি।
- [ ] একাধিক Formatting Option একসঙ্গে ব্যবহার করতে পারি।

---

## 20. Next Topic

পরবর্তী topic:

**38. String format() Method in Python**

এখানে আমরা `format()` method-এর Syntax, Placeholder `{}`, Positional Arguments, Keyword Arguments এবং Number Formatting শিখব।
