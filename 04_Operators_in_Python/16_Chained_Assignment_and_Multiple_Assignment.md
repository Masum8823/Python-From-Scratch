# 16. Chained Assignment and Multiple Assignment in Python

## 1. Introduction

Python-এ একাধিক Variable-এ Value Assign করার জন্য **Chained Assignment** এবং **Multiple Assignment** ব্যবহার করা যায়।

দুটির উদ্দেশ্য কাছাকাছি হলেও কাজ করার পদ্ধতি আলাদা।

- **Chained Assignment:** একই Value একাধিক Variable-এ Assign করা।
- **Multiple Assignment:** একাধিক Variable-এ একসঙ্গে আলাদা Value Assign করা।

এই দুটি পদ্ধতি ব্যবহার করলে Code আরও সংক্ষিপ্ত ও সহজে পড়ার উপযোগী হয়।

---

## 2. Chained Assignment

Chained Assignment ব্যবহার করে একই Value একাধিক Variable-এ Assign করা যায়।

### Syntax

```python
variable1 = variable2 = value
```

এখানে একই Value উভয় Variable-এ Assign হবে।

### Example 1: Basic Chained Assignment

```python
a = b = 10

print(a)
print(b)
```

Output:

```text
10
10
```

ব্যাখ্যা:

- `a`-এর Value `10`।
- `b`-এর Value `10`।

দুটি Variable-এই একই Integer Value Assign হয়েছে।

### Example 2: Three Variables

```python
x = y = z = 100

print(x)
print(y)
print(z)
```

Output:

```text
100
100
100
```

এখানে একটি Value তিনটি Variable-এ Assign হয়েছে।

### Example 3: Updating One Variable

```python
a = b = 10

a = 20

print(a)
print(b)
```

Output:

```text
20
10
```

ব্যাখ্যা:

প্রথমে `a` এবং `b`-এর Value ছিল `10`। পরে `a = 20` করার ফলে শুধু `a`-এর Assignment পরিবর্তিত হয়েছে। `b`-এর Value `10`-ই আছে।

**মনে রাখবে:** Chained Assignment-এর মাধ্যমে একই Value Assign করা হলেও সাধারণ Immutable Value-এর ক্ষেত্রে Variable-গুলো পরস্পরের সঙ্গে স্থায়ীভাবে বাঁধা থাকে না।

---

## 3. How Chained Assignment Works

নিচের Code দেখো:

```python
x = y = z = 5
```

এটিকে বোঝার একটি সহজ উপায় হলো:

```python
z = 5
y = z
x = y
```

ফলে তিনটি Variable-এই `5` পাওয়া যায়।

```python
x = y = z = 5

print(x == y == z)
```

Output:

```text
True
```

এখানে `==` দিয়ে তিনটি Value সমান কি না পরীক্ষা করা হয়েছে।

তবে Chained Assignment-এ প্রতিটি Variable-এ Value Assign করা হয়; এটি একাধিক Variable-এর Value স্বয়ংক্রিয়ভাবে একসঙ্গে পরিবর্তন করে না।

---

## 4. Multiple Assignment

Multiple Assignment ব্যবহার করে একাধিক Variable-এ একসঙ্গে আলাদা Value Assign করা যায়।

### Syntax

```python
variable1, variable2 = value1, value2
```

প্রতিটি Variable সংশ্লিষ্ট Value পায়।

### Example 1: Basic Multiple Assignment

```python
a, b = 10, 20

print(a)
print(b)
```

Output:

```text
10
20
```

ব্যাখ্যা:

- `a` পেয়েছে `10`।
- `b` পেয়েছে `20`।

### Example 2: Three Variables

```python
name, age, cgpa = "Masum", 22, 3.95

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

এখানে একসঙ্গে তিনটি Variable-এ তিনটি আলাদা Value Assign হয়েছে।

### Example 3: Different Data Types

```python
name, age, is_student = "Rahim", 21, True

print(name)
print(age)
print(is_student)
```

Output:

```text
Rahim
21
True
```

Multiple Assignment-এ বিভিন্ন Data Type-এর Value ব্যবহার করা যায়।

---

## 5. How Multiple Assignment Works

নিচের Code দেখো:

```python
a, b = 10, 20
```

Python প্রথমে ডান পাশের Value-গুলো প্রস্তুত করে, তারপর বাম পাশের Variable-গুলোতে Assign করে।

এটিকে ধারণাগতভাবে এভাবে বোঝা যায়:

```python
a = 10
b = 20
```

তবে Multiple Assignment-এর বিশেষ সুবিধা হলো, একাধিক Variable-এর Value একসঙ্গে পরিবর্তন করা যায়।

### Example

```python
x, y = 5, 10

x, y = 20, 30

print(x)
print(y)
```

Output:

```text
20
30
```

এখানে দ্বিতীয় Assignment-এ উভয় Variable-এর Value পরিবর্তন হয়েছে।

---

## 6. Swapping Variables

Python-এর Multiple Assignment-এর একটি গুরুত্বপূর্ণ ব্যবহার হলো দুটি Variable-এর Value Swap করা।

**Swapping** অর্থ হলো দুটি Variable-এর Value পরস্পরের মধ্যে বিনিময় করা।

### Traditional Method

অনেক Programming Language-এ Temporary Variable ব্যবহার করা হয়।

```python
a = 10
b = 20

temp = a
a = b
b = temp

print(a)
print(b)
```

Output:

```text
20
10
```

এখানে `temp` Variable ব্যবহার করে Value বিনিময় করা হয়েছে।

### Python Method

Python-এ Multiple Assignment ব্যবহার করে আরও সহজে Swap করা যায়।

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

ব্যাখ্যা:

- প্রথমে `a = 10` এবং `b = 20`।
- `a, b = b, a`-তে ডান পাশের Value-গুলো আগে মূল্যায়ন করা হয়।
- এরপর `a` পায় `20` এবং `b` পায় `10`।

**মনে রাখবে:** Python-এ দুটি Variable Swap করার জন্য সাধারণত Temporary Variable প্রয়োজন হয় না।

---

## 7. Assigning Values from Expressions

Multiple Assignment-এর ডান পাশে Expression ব্যবহার করা যায়।

### Example 1

```python
a, b = 5 + 5, 10 * 2

print(a)
print(b)
```

Output:

```text
10
20
```

### Example 2

```python
x, y = 8 ** 2, 15 % 4

print(x)
print(y)
```

Output:

```text
64
3
```

এখানে:

- `8 ** 2 = 64`
- `15 % 4 = 3`

### Example 3

```python
a, b, c = 10, 20 + 5, 6 * 3

print(a, b, c)
```

Output:

```text
10 25 18
```

প্রতিটি Expression-এর Result সংশ্লিষ্ট Variable-এ Assign হয়েছে।

---

## 8. Unpacking with Multiple Assignment

Python-এ কোনো Sequence-এর Value আলাদা Variable-এ Assign করার পদ্ধতিকে **Unpacking** বলা হয়।

### Example 1: Tuple Unpacking

```python
student = ("Masum", 22, 3.95)

name, age, cgpa = student

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

এখানে Tuple-এর তিনটি Value তিনটি Variable-এ Assign হয়েছে।

### Example 2: List Unpacking

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

List-এর Value-ও Unpacking করা যায়।

### Example 3: String Unpacking

```python
a, b, c = "ABC"

print(a)
print(b)
print(c)
```

Output:

```text
A
B
C
```

String-এর প্রতিটি Character একটি করে Variable-এ Assign হয়েছে।

**সতর্কতা:** সাধারণ Unpacking-এ বাম পাশের Variable-এর সংখ্যা এবং ডান পাশের Iterable-এর Element-এর সংখ্যা সমান হতে হবে।

---

## 9. Extended Unpacking with `*`

Python-এ `*` ব্যবহার করে Unpacking-এর সময় একাধিক Element একটি List-এ সংগ্রহ করা যায়।

### Example 1

```python
a, *b = [10, 20, 30, 40]

print(a)
print(b)
```

Output:

```text
10
[20, 30, 40]
```

ব্যাখ্যা:

- `a` প্রথম Element পেয়েছে।
- `b` বাকি Element-গুলো একটি List হিসেবে পেয়েছে।

### Example 2

```python
first, *middle, last = [1, 2, 3, 4, 5]

print(first)
print(middle)
print(last)
```

Output:

```text
1
[2, 3, 4]
5
```

এখানে:

- `first` প্রথম Element পেয়েছে।
- `middle` মাঝের Element-গুলো পেয়েছে।
- `last` শেষ Element পেয়েছে।

### Example 3: Collecting Remaining Values

```python
a, b, *rest = [5, 10, 15, 20, 25]

print(a)
print(b)
print(rest)
```

Output:

```text
5
10
[15, 20, 25]
```

`*rest` অবশিষ্ট Element-গুলো সংগ্রহ করেছে।

---

## 10. Variable Count Must Match

সাধারণ Multiple Assignment-এ দুই পাশের Value-এর সংখ্যা মিলতে হবে।

### Correct Example

```python
a, b, c = 10, 20, 30

print(a, b, c)
```

Output:

```text
10 20 30
```

### Incorrect Example

```python
# a, b = 10, 20, 30
```

এখানে দুইটি Variable-এর জন্য তিনটি Value দেওয়া হয়েছে। ফলে `ValueError` হবে।

আরেকটি ভুল:

```python
# a, b, c = 10, 20
```

এখানে তিনটি Variable-এর জন্য মাত্র দুটি Value দেওয়া হয়েছে। এখানেও `ValueError` হবে।

Extended Unpacking-এ `*` ব্যবহার করে এই নিয়মের কিছুটা নমনীয়তা পাওয়া যায়।

---

## 11. Chained Assignment vs Multiple Assignment

| বিষয় | Chained Assignment | Multiple Assignment |
|---|---|---|
| উদ্দেশ্য | একই Value একাধিক Variable-এ Assign করা | একাধিক Variable-এ আলাদা Value Assign করা |
| Syntax | `a = b = 10` | `a, b = 10, 20` |
| Result | `a = 10`, `b = 10` | `a = 10`, `b = 20` |
| প্রধান ব্যবহার | একই প্রাথমিক Value দেওয়া | একাধিক Value Assign করা |
| Swap করা | সরাসরি এর উদ্দেশ্য নয় | সহজে Swap করা যায় |

### Example

```python
# Chained Assignment
a = b = 5

# Multiple Assignment
x, y = 5, 10

print(a, b)
print(x, y)
```

Output:

```text
5 5
5 10
```

---

## 12. Common Mistakes

### Mistake 1: Mismatched Number of Values

```python
# a, b = 10, 20, 30
```

দুইটি Variable-এর জন্য তিনটি Value দেওয়া হয়েছে। তাই `ValueError` হবে।

### Mistake 2: Incorrect Swapping

```python
a = 10
b = 20

a = b
b = a

print(a, b)
```

Output:

```text
20 20
```

এটি ভুল Swap।

কারণ `a = b` করার পর `a`-এর আগের Value হারিয়ে যায়। এরপর `b = a` করলে `b`-ও `20` হয়।

সঠিক পদ্ধতি:

```python
a = 10
b = 20

a, b = b, a

print(a, b)
```

Output:

```text
20 10
```

### Mistake 3: Confusing Chained and Multiple Assignment

```python
a = b = 10
```

এখানে উভয় Variable-এ `10` Assign হবে।

কিন্তু:

```python
a, b = 10, 20
```

এখানে `a` পাবে `10` এবং `b` পাবে `20`।

### Mistake 4: Incorrect Unpacking

```python
# a, b, c = [10, 20]
```

তিনটি Variable-এর জন্য দুটি Element দেওয়া হয়েছে। তাই `ValueError` হবে।

---

## 13. Practice Exercises

### Basic Level

1. Chained Assignment ব্যবহার করে `a`, `b` এবং `c`-তে `100` Assign করো।
2. Multiple Assignment ব্যবহার করে `x = 10`, `y = 20` এবং `z = 30` Assign করো।
3. `name`, `age` এবং `cgpa`-তে আলাদা Value Assign করে Print করো।
4. `a = 5` এবং `b = 10` দিয়ে তাদের Value Swap করো।

### Intermediate Level

5. `[10, 20, 30]` List Unpack করে তিনটি Variable-এ Assign করো।
6. `a, *b = [1, 2, 3, 4]`-এর Output নির্ণয় করো।
7. `first, *middle, last = [10, 20, 30, 40, 50]`-এর Output নির্ণয় করো।
8. `x, y = 5 + 5, 20 // 3`-এর Output নির্ণয় করো।

### Output Prediction

```python
a = b = 10

a = 20

print(a, b)

x, y = 5, 15

x, y = y, x

print(x, y)

first, *rest = [1, 2, 3, 4]

print(first)
print(rest)
```

### Answers

```text
20 10
15 5
1
[2, 3, 4]
```

---

## 14. Chapter Summary

- **Chained Assignment** একই Value একাধিক Variable-এ Assign করে।
- **Multiple Assignment** একাধিক Variable-এ আলাদা Value Assign করতে পারে।
- Multiple Assignment দিয়ে সহজে Variable Swap করা যায়।
- Unpacking-এর মাধ্যমে List, Tuple ও String-এর Element আলাদা Variable-এ Assign করা যায়।
- `*` ব্যবহার করে Extended Unpacking করা যায়।
- সাধারণ Unpacking-এ Variable এবং Value-এর সংখ্যা সমান হতে হয়।
- দুই পাশের সংখ্যা না মিললে সাধারণত `ValueError` হয়।

## 15. Self-Assessment Checklist

- [ ] Chained Assignment-এর Syntax বুঝি।
- [ ] Multiple Assignment ব্যবহার করতে পারি।
- [ ] Chained ও Multiple Assignment-এর পার্থক্য বুঝি।
- [ ] Multiple Assignment দিয়ে Variable Swap করতে পারি।
- [ ] List ও Tuple Unpacking করতে পারি।
- [ ] `*` দিয়ে Extended Unpacking করতে পারি।
- [ ] Assignment-সংক্রান্ত Error শনাক্ত করতে পারি।

**Next Topic:** `17_Walrus_Operator.md`