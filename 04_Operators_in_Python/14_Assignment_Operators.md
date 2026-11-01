# 14. Assignment Operators in Python

## 1. Introduction to Assignment Operators

Python-এ **Assignment Operator** ব্যবহার করে কোনো Variable-এ Value Assign করা হয়।

সবচেয়ে সাধারণ Assignment Operator হলো `=`।

Example:

```python
name = "Masum"
age = 22
marks = 90

print(name)
print(age)
print(marks)
```

Output:

```text
Masum
22
90
```

ব্যাখ্যা:

- `name = "Masum"` → `name` Variable-এ `"Masum"` Assign করা হয়েছে।
- `age = 22` → `age` Variable-এ `22` Assign করা হয়েছে।
- `marks = 90` → `marks` Variable-এ `90` Assign করা হয়েছে।

**মনে রাখবে:** Python-এ `=` হলো Assignment Operator, Equality Comparison Operator নয়। দুটি Value সমান কি না পরীক্ষা করতে `==` ব্যবহার করা হয়।

---

## 2. The Basic Assignment Operator (`=`)

`=` Operator ডান পাশের Expression Evaluate করে তার Result বাম পাশের Target-এ Assign করে।

Syntax:

```python
variable = value
```

Example:

```python
x = 10
y = x

print(x)
print(y)
```

Output:

```text
10
10
```

ব্যাখ্যা:

1. প্রথমে `x`-এ `10` Assign করা হয়েছে।
2. এরপর `y = x`-এর মাধ্যমে `x`-এর বর্তমান Value `y`-তে Assign করা হয়েছে।
3. তাই `x` এবং `y` উভয়ের Value `10`।

### Assignment Is Not Equality

```python
x = 5
print(x == 5)
```

Output:

```text
True
```

এখানে:

- `x = 5` → Assignment।
- `x == 5` → Equality Comparison।

দুটির কাজ আলাদা।

---

## 3. Reassigning a Variable

একই Variable-এ পরে নতুন Value Assign করা যায়। একে Reassignment বলা হয়।

Example:

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

ব্যাখ্যা:

- প্রথমে `score`-এর Value `50`।
- পরে নতুন করে `80` Assign করায় Variable-এর বর্তমান Value `80` হয়েছে।

Python-এ Variable-এর Data Type-ও পরিবর্তিত হতে পারে।

```python
value = 100
print(value)

value = "Python"
print(value)
```

Output:

```text
100
Python
```

প্রথমে `value`-তে Integer ছিল, পরে String Assign করা হয়েছে।

---

## 4. Assignment Using Expressions

Assignment Operator-এর ডান পাশে সরাসরি Value ছাড়াও Expression ব্যবহার করা যায়।

Example:

```python
a = 10
b = 5

result = a + b

print(result)
```

Output:

```text
15
```

এখানে `a + b` প্রথমে Evaluate হয়েছে। তারপর Result `15`, `result` Variable-এ Assign হয়েছে।

আরও একটি Example:

```python
price = 100
quantity = 3

total = price * quantity

print(total)
```

Output:

```text
300
```

এই পদ্ধতি Calculation-ভিত্তিক Program-এ নিয়মিত ব্যবহৃত হয়।

---

## 5. Overview of Assignment Operators

Python-এ Basic এবং Augmented Assignment Operator রয়েছে।

| Operator | অর্থ | Example |
|---|---|---|
| `=` | Value Assign | `x = 10` |
| `+=` | যোগ করে Assign | `x += 5` |
| `-=` | বিয়োগ করে Assign | `x -= 5` |
| `*=` | গুণ করে Assign | `x *= 5` |
| `/=` | ভাগ করে Assign | `x /= 5` |
| `//=` | Floor Division করে Assign | `x //= 5` |
| `%=` | Modulo করে Assign | `x %= 5` |
| `**=` | Power করে Assign | `x **= 5` |
| `&=` | Bitwise AND করে Assign | `x &= 5` |
| `\|=` | Bitwise OR করে Assign | `x \|= 5` |
| `^=` | Bitwise XOR করে Assign | `x ^= 5` |
| `>>=` | Right Shift করে Assign | `x >>= 1` |
| `<<=` | Left Shift করে Assign | `x <<= 1` |
| `@=` | Matrix Multiplication করে Assign | `x @= matrix` |

এ ছাড়া `:=` নামে Walrus Operator রয়েছে, যা Assignment Expression তৈরি করে। এটি সাধারণ `=` Assignment-এর মতো নয় এবং আলাদা Topic-এ আলোচনা করা হবে।

---

## 6. Assignment Operator with Arithmetic Expressions

Assignment Operator-এর মাধ্যমে Arithmetic Expression-এর Result Variable-এ রাখা যায়।

Example:

```python
a = 20
b = 4

sum_result = a + b
difference = a - b
product = a * b
quotient = a / b

print(sum_result)
print(difference)
print(product)
print(quotient)
```

Output:

```text
24
16
80
5.0
```

ব্যাখ্যা:

- `a + b` → `24`
- `a - b` → `16`
- `a * b` → `80`
- `a / b` → `5.0`

Python-এ `/` ব্যবহার করলে সাধারণত Result Float হয়, এমনকি ভাগশেষ না থাকলেও।

---

## 7. Assignment with Strings

Assignment Operator শুধু Number-এর জন্য নয়, String-এর ক্ষেত্রেও ব্যবহার করা যায়।

Example:

```python
name = "Abdulla"
message = "Hello, "

message = message + name

print(message)
```

Output:

```text
Hello, Abdulla
```

এখানে String Concatenation-এর মাধ্যমে নতুন String তৈরি করে `message`-এ Assign করা হয়েছে।

String-এর সঙ্গে `+=` ব্যবহার করা যায়:

```python
message = "Hello"
message += " Python"

print(message)
```

Output:

```text
Hello Python
```

এখানে:

```python
message += " Python"
```

সাধারণ String Variable-এর ক্ষেত্রে নিচের Expression-এর মতো কাজ করে:

```python
message = message + " Python"
```

---

## 8. Assignment with Lists

List-এর ক্ষেত্রেও Assignment করা যায়।

Example:

```python
numbers = [10, 20, 30]
numbers = [40, 50]

print(numbers)
```

Output:

```text
[40, 50]
```

এখানে Variable `numbers`-কে নতুন List-এর সঙ্গে Reassign করা হয়েছে।

List-এর সঙ্গে `+=` ব্যবহার করেও Element যোগ করা যায়।

```python
numbers = [10, 20]
numbers += [30, 40]

print(numbers)
```

Output:

```text
[10, 20, 30, 40]
```

List-এর ক্ষেত্রে `+=` সাধারণত List-এর Element-গুলোকে বিদ্যমান List-এ যোগ করে।

তবে Assignment Operator-এর সুনির্দিষ্ট আচরণ Data Type অনুযায়ী ভিন্ন হতে পারে। তাই সব Type-এর জন্য `x += y`-কে সব সময় `x = x + y`-এর সম্পূর্ণ সমতুল্য ধরে নেওয়া ঠিক নয়।

---

## 9. Assignment and Object References

Python-এ Variable সাধারণত Object-কে Reference করে। তাই একটি Variable থেকে অন্য Variable-এ Value Assign করার সময় Mutable Object-এর ক্ষেত্রে বিশেষ সতর্ক থাকতে হয়।

Example:

```python
a = [1, 2, 3]
b = a

b.append(4)

print(a)
print(b)
```

Output:

```text
[1, 2, 3, 4]
[1, 2, 3, 4]
```

ব্যাখ্যা:

- `a` একটি List Object-কে Reference করছে।
- `b = a` করার ফলে `b` একই List Object-কে Reference করছে।
- `b.append(4)` করার ফলে সেই একই List পরিবর্তিত হয়েছে।
- তাই `a` এবং `b` উভয় Variable-এর মাধ্যমে পরিবর্তিত List দেখা যাচ্ছে।

এটি সাধারণ Reassignment থেকে আলাদা। Mutable ও Immutable Object নিয়ে পরবর্তী Chapter-এ আরও বিস্তারিত আলোচনা করা হবে।

---

## 10. Common Assignment Errors

### Mistake 1: Using `==` Instead of `=`

ভুল:

```python
# x == 10
```

এটি `x`-এ `10` Assign করে না। এটি `x` এবং `10` সমান কি না পরীক্ষা করে। `x` আগে Define করা না থাকলে `NameError` হতে পারে।

সঠিক:

```python
x = 10
print(x)
```

Output:

```text
10
```

### Mistake 2: Using an Undefined Variable

```python
# print(score)
```

যদি `score` আগে Define করা না থাকে, তাহলে `NameError` হবে।

সঠিক:

```python
score = 90
print(score)
```

Output:

```text
90
```

### Mistake 3: Confusing Assignment with Comparison in a Condition

```python
x = 10

if x == 10:
    print("Value is 10")
```

Output:

```text
Value is 10
```

এখানে `if`-এর Condition-এ `==` ব্যবহার করা হয়েছে, কারণ Value Compare করতে হবে।

### Mistake 4: Assigning an Incompatible Value

```python
age = "twenty"
```

এই Assignment বৈধ। Python Variable-এ String Assign করতে দেয়। কিন্তু পরে Numeric Operation করতে গেলে সমস্যা হতে পারে।

```python
age = "twenty"

# print(age + 5)  # TypeError
```

Numeric Calculation করতে চাইলে সঠিক Numeric Value Assign বা Convert করতে হবে।

---

## 11. Practice Exercises

### Basic Level

1. `x = 25` Statement-এ কোন Operator ব্যবহার হয়েছে?
2. Assignment এবং Equality Comparison-এর পার্থক্য কী?
3. `score = 50`-এর পর `score = 90` হলে বর্তমান Value কত?
4. `total = 10 + 20` হলে `total`-এর Value কত?
5. `name = "Python"`-এর পরে `name = "Java"` করলে কী হবে?

### Intermediate Level

6. দুটি Variable-এর যোগফল তৃতীয় Variable-এ Assign করো।
7. একটি Variable-এ String Assign করে তার সঙ্গে আরেকটি String যোগ করো।
8. একটি List-এ নতুন Element যোগ করতে `+=` ব্যবহার করো।
9. Variable Reassignment-এর একটি উদাহরণ লেখো।
10. `a = [1, 2]` এবং `b = a` হলে `b.append(3)` করার পর `a`-এর Value কী হবে?

### Output Prediction

```python
x = 10
y = x

x = 20

print(x)
print(y)

message = "Hello"
message += " Python"

print(message)
```

### Answers

```text
20
10
Hello Python
```

ব্যাখ্যা:

- `x`-কে পরে `20` Assign করা হয়েছে।
- `y`-তে আগের Integer Value `10` Assign করা হয়েছিল, তাই `y`-এর Value `10`-ই থাকে।
- `message += " Python"` String-এর সঙ্গে নতুন অংশ যোগ করেছে।

---

## 12. Chapter Summary

- Assignment Operator `=` দিয়ে Variable-এ Value Assign করা হয়।
- Reassignment-এর মাধ্যমে Variable-এর Value পরিবর্তন করা যায়।
- Assignment-এর ডান পাশে Value বা Expression থাকতে পারে।
- `=` এবং `==`-এর কাজ আলাদা।
- Assignment Operator Number, String, List এবং অন্যান্য Object-এর সঙ্গে ব্যবহার করা যায়।
- Augmented Assignment Operator-এর মাধ্যমে Value Update করা যায়।
- Mutable Object-এর ক্ষেত্রে একাধিক Variable একই Object Reference করতে পারে।
- Undefined Variable ব্যবহার করলে `NameError` হতে পারে।
- Assignment-এর পর Variable-এর Data Type পরিবর্তিত হতে পারে।

## 13. Self-Assessment Checklist

- [ ] Assignment Operator `=`-এর কাজ বুঝি।
- [ ] Assignment এবং Equality Comparison-এর পার্থক্য বুঝি।
- [ ] Variable Reassignment করতে পারি।
- [ ] Expression-এর Result Variable-এ Assign করতে পারি।
- [ ] String ও List-এর সঙ্গে Assignment ব্যবহার করতে পারি।
- [ ] Mutable Object Reference-এর Basic ধারণা বুঝি।
- [ ] সাধারণ Assignment Error চিহ্নিত করতে পারি।

**Next Topic:** `15_Augmented_Assignment_Operators.md`