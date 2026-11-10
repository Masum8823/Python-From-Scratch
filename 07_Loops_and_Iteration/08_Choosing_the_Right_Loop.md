# 08. Choosing the Right Loop

## 1. Introduction

Python-এ প্রধানত দুই ধরনের loop ব্যবহার করা হয়:

1. `for` loop
2. `while` loop

দুটিই repeated task সম্পন্ন করতে পারে। তবে problem-এর ধরন অনুযায়ী একটি loop অন্যটির চেয়ে বেশি উপযুক্ত হতে পারে।

উদাহরণস্বরূপ:

- ১ থেকে ১০ পর্যন্ত number print করতে `for` loop সহজ।
- User সঠিক password না দেওয়া পর্যন্ত input নিতে `while` loop সুবিধাজনক।
- একটি list-এর সব item process করতে `for` loop ব্যবহার করা যায়।
- কোনো condition পূরণ না হওয়া পর্যন্ত কাজ চালাতে `while` loop ব্যবহার করা যায়।

**মূল কথা:** Problem-এর repetition কীভাবে নির্ধারিত হচ্ছে, সেটি দেখে loop নির্বাচন করতে হবে।

## 2. When Should You Use a `for` Loop?

**Definition:** A `for` loop is generally used when iterating over a sequence or other iterable, or when the items to process are known.

সহজ ভাষায়, যখন কোনো sequence বা iterable-এর item একে একে process করতে হবে, তখন `for` loop সাধারণত সবচেয়ে উপযুক্ত।

### Example 1: Printing Numbers

```python
for number in range(1, 6):
    print(number)
```

Output:

```text
1
2
3
4
5
```

এখানে `range(1, 6)` থেকে নির্দিষ্ট সংখ্যক value পাওয়া যাচ্ছে। তাই `for` loop উপযুক্ত।

### Example 2: Processing a List

```python
fruits = ["Apple", "Mango", "Banana"]

for fruit in fruits:
    print(fruit)
```

Output:

```text
Apple
Mango
Banana
```

এখানে list-এর প্রতিটি item একবার করে process করা হচ্ছে।

### Example 3: Calculating a Sum

```python
total = 0

for number in range(1, 6):
    total += number

print("Total:", total)
```

Output:

```text
Total: 15
```

এখানে নির্দিষ্ট range-এর number নিয়ে calculation করা হচ্ছে।

### Use `for` When

- কোনো list, tuple, string, set বা dictionary-এর item process করতে হবে।
- `range()` দিয়ে নির্দিষ্ট সংখ্যক iteration করতে হবে।
- প্রতিটি item-এর ওপর একই operation চালাতে হবে।
- Iterable-এর item একে একে পড়তে হবে।

## 3. When Should You Use a `while` Loop?

**Definition:** A `while` loop is generally used when repetition should continue as long as a condition remains true.

সহজ ভাষায়, কোনো condition `True` থাকা পর্যন্ত কাজ চালাতে চাইলে `while` loop সাধারণত উপযুক্ত।

### Example 1: User Input Validation

```python
password = ""

while password != "python123":
    password = input("Enter password: ")

print("Access granted")
```

এখানে সঠিক password না দেওয়া পর্যন্ত loop চলবে।

**Note:** এটি শুধু শেখার উদাহরণ। বাস্তব authentication system-এ password নিরাপদভাবে সংরক্ষণ ও যাচাই করতে হয়।

### Example 2: Countdown

```python
count = 5

while count > 0:
    print(count)
    count -= 1

print("Finished")
```

Output:

```text
5
4
3
2
1
Finished
```

এখানে `count > 0` condition `True` থাকা পর্যন্ত loop চলে।

### Example 3: Repeating a Menu

```python
choice = ""

while choice != "3":
    print("1. Start")
    print("2. Help")
    print("3. Exit")

    choice = input("Choose an option: ")

print("Program ended")
```

User `3` না দেওয়া পর্যন্ত menu দেখানো হবে।

### Use `while` When

- কোনো condition পূরণ না হওয়া পর্যন্ত repetition দরকার।
- User-এর input অনুযায়ী loop চলবে কি না নির্ধারিত হবে।
- কোনো value পরিবর্তনের সঙ্গে সঙ্গে condition যাচাই করতে হবে।
- Iteration-এর নির্দিষ্ট সংখ্যা আগে থেকে জানা নেই।

## 4. Main Differences Between `for` and `while`

| বিষয় | `for` loop | `while` loop |
|---|---|---|
| সাধারণ ব্যবহার | Iterable-এর item process করা | Condition অনুযায়ী repeat করা |
| Iteration | Iterable-এর item অনুযায়ী চলে | Condition `True` থাকা পর্যন্ত চলে |
| Variable update | Iterable-এর পরবর্তী item স্বয়ংক্রিয়ভাবে পাওয়া যায় | প্রয়োজন হলে variable নিজে update করতে হয় |
| সাধারণ উদাহরণ | List-এর item print করা | সঠিক input না পাওয়া পর্যন্ত input নেওয়া |
| Infinite loop-এর ঝুঁকি | সাধারণ iteration-এ তুলনামূলক কম | Update বা condition ভুল হলে বেশি |
| উপযুক্ত পরিস্থিতি | Item বা iteration-এর উৎস জানা | Condition-নির্ভর repetition |

মনে রাখবে, এই পার্থক্যগুলো সাধারণ ব্যবহারের নিয়ম। `for` ও `while` দিয়ে অনেক ক্ষেত্রে একই problem solve করা সম্ভব।

## 5. Solving the Same Problem with Both Loops

ধরো, ১ থেকে ৫ পর্যন্ত number print করতে হবে।

### Using `for`

```python
for number in range(1, 6):
    print(number)
```

### Using `while`

```python
number = 1

while number <= 5:
    print(number)
    number += 1
```

দুটির output একই:

```text
1
2
3
4
5
```

তবে এই problem-এ `for` loop বেশি সহজ, কারণ `range()` নিজেই পরপর value সরবরাহ করে।

`while` loop-এ আমাদের আলাদাভাবে:

- Initial value দিতে হয়েছে।
- Condition লিখতে হয়েছে।
- Variable update করতে হয়েছে।

তাই নির্দিষ্ট range-এর জন্য `for` সাধারণত বেশি readable।

## 6. Choosing a Loop Based on the Problem

নিচের উদাহরণগুলো দেখে উপযুক্ত loop নির্বাচন করো।

| Problem | Recommended Loop | কারণ |
|---|---|---|
| ১ থেকে ১০ পর্যন্ত print | `for` | নির্দিষ্ট range |
| List-এর সব item print | `for` | প্রতিটি item process করতে হবে |
| String-এর প্রতিটি character print | `for` | String iterable |
| ১০টি number-এর যোগফল | `for` | নির্দিষ্ট সংখ্যক item |
| সঠিক input না পাওয়া পর্যন্ত repeat | `while` | Condition নির্ভর |
| Menu-তে Exit নির্বাচন না করা পর্যন্ত চলা | `while` | Exit condition নির্ভর |
| Countdown | `while` বা `for` | দুটো দিয়েই করা যায় |
| Data-এর প্রতিটি row process | `for` | Iterable-এর item process করা |
| কোনো condition পূরণ না হওয়া পর্যন্ত retry | `while` | Retry condition নির্ভর |

## 7. Can We Use `for` for Condition-Based Problems?

হ্যাঁ, কিছু condition-based problem-ও `for` loop দিয়ে সমাধান করা যায়, যদি উপযুক্ত iterable বা সীমা নির্ধারণ করা সম্ভব হয়।

উদাহরণ:

```python
numbers = [3, 7, 10, 15, 20]

for number in numbers:
    if number > 10:
        print("First number greater than 10:", number)
        break
```

Output:

```text
First number greater than 10: 15
```

এখানে list-এর item পরীক্ষা করা হচ্ছে। প্রথম উপযুক্ত number পাওয়া গেলে `break` loop শেষ করে।

অর্থাৎ, `for` loop ব্যবহার করেও condition অনুযায়ী মাঝপথে repetition বন্ধ করা যায়।

## 8. Can We Use `while` for a Fixed Number of Iterations?

হ্যাঁ। নির্দিষ্ট সংখ্যক iteration-এর জন্যও `while` ব্যবহার করা যায়।

```python
count = 0

while count < 3:
    print("Hello")
    count += 1
```

Output:

```text
Hello
Hello
Hello
```

তবে এই সাধারণ problem-এর জন্য `for` loop সাধারণত বেশি সহজ:

```python
for count in range(3):
    print("Hello")
```

## 9. A Simple Decision-Making Rule

Loop নির্বাচন করার সময় নিজেকে এই প্রশ্নগুলো করো:

**Question 1:** কোনো iterable-এর item একে একে process করতে হবে?

- হ্যাঁ → সাধারণত `for` ব্যবহার করো।

**Question 2:** কোনো condition `True` থাকা পর্যন্ত repetition চালাতে হবে?

- হ্যাঁ → সাধারণত `while` ব্যবহার করো।

**Question 3:** নির্দিষ্ট সংখ্যক repetition দরকার?

- হ্যাঁ → `for` এবং `range()` সাধারণত সহজ।

**Question 4:** Repetition কখন শেষ হবে তা user input বা পরিবর্তনশীল condition-এর ওপর নির্ভর করছে?

- হ্যাঁ → `while` সাধারণত সুবিধাজনক।

এগুলো নির্দেশনা, বাধ্যতামূলক নিয়ম নয়। যে loop দিয়ে code সবচেয়ে পরিষ্কার ও নিরাপদভাবে লেখা যায়, সেটি বেছে নাও।

## 10. Common Mistakes

### Mistake 1: সব Problem-এ `while` ব্যবহার করা

নির্দিষ্ট range-এর জন্য অপ্রয়োজনীয়ভাবে `while` ব্যবহার করলে initialization, condition ও update আলাদাভাবে লিখতে হয়।

### Mistake 2: `while` Loop-এ Update ভুলে যাওয়া

```python
count = 1

while count <= 5:
    print(count)
```

এখানে `count` পরিবর্তিত হচ্ছে না। ফলে condition `True`-ই থাকবে এবং loop শেষ হবে না।

### Mistake 3: `for` Loop-এ `range()`-এর Stop Value ভুল বোঝা

```python
for number in range(1, 5):
    print(number)
```

Output:

```text
1
2
3
4
```

`range()`-এর stop value `5` অন্তর্ভুক্ত হয় না।

### Mistake 4: ধরে নেওয়া যে `for` সবসময় নির্দিষ্ট সংখ্যক বার চলবে

`for` loop কতবার চলবে তা iterable-এর ওপর নির্ভর করে। Iterable খালি হলে loop body একবারও execute হবে না।

## 11. Practice Exercises

### Exercise 1

১ থেকে ১০০ পর্যন্ত number print করার জন্য কোন loop সাধারণত বেশি উপযুক্ত?

### Exercise 2

একটি list-এর প্রতিটি item process করার জন্য কোন loop সাধারণত ব্যবহার করবে?

### Exercise 3

User `exit` না লেখা পর্যন্ত input নিতে কোন loop বেশি উপযুক্ত?

### Exercise 4

নিচের code-এর output কী হবে?

```python
for number in range(2, 5):
    print(number)
```

### Exercise 5

নিচের code-এ কী সমস্যা রয়েছে?

```python
count = 1

while count <= 3:
    print(count)
```

### Exercise 6

নিচের problem-এর জন্য উপযুক্ত loop নির্বাচন করো:

একটি list-এর সব সংখ্যার যোগফল বের করতে হবে।

### Exercise 7

`for` ও `while` loop কি একই problem সমাধান করতে পারে? একটি উদাহরণ দাও।

## 12. Answer Key

**Exercise 1:** `for` loop, কারণ নির্দিষ্ট range-এর number print করতে হবে।

**Exercise 2:** `for` loop, কারণ list-এর প্রতিটি item process করতে হবে।

**Exercise 3:** `while` loop, কারণ repetition user-এর input-এর ওপর নির্ভর করছে।

**Exercise 4:**

```text
2
3
4
```

**Exercise 5:** `count` update করা হয়নি। `count += 1` যোগ করতে হবে।

**Exercise 6:** সাধারণত `for` loop।

```python
numbers = [10, 20, 30, 40]
total = 0

for number in numbers:
    total += number

print(total)
```

Output:

```text
100
```

**Exercise 7:** হ্যাঁ। যেমন ১ থেকে ৫ পর্যন্ত print করা যায় `for` এবং `while`—দুটো দিয়েই।

## 13. Chapter Progress Checklist

- [ ] `for` loop কখন ব্যবহার করতে হয় বুঝেছি।
- [ ] `while` loop কখন ব্যবহার করতে হয় বুঝেছি।
- [ ] দুটো loop-এর পার্থক্য বলতে পারি।
- [ ] একই problem দুই ধরনের loop দিয়ে solve করতে পারি।
- [ ] Problem দেখে উপযুক্ত loop নির্বাচন করতে পারি।
- [ ] `range()`-এর stop value-এর নিয়ম জানি।
- [ ] Infinite loop-এর সাধারণ কারণ বুঝেছি।

## 14. Summary

- `for` loop সাধারণত iterable-এর item process করার জন্য উপযুক্ত।
- `while` loop সাধারণত condition-নির্ভর repetition-এর জন্য উপযুক্ত।
- নির্দিষ্ট range-এর জন্য `for` ও `range()` সাধারণত সহজ।
- `while` loop-এ condition পরিবর্তনের জন্য প্রয়োজনীয় update নিশ্চিত করতে হয়।
- একই problem দুই ধরনের loop দিয়েই সমাধান করা সম্ভব হতে পারে।
- Loop নির্বাচন করার সময় readability, correctness ও problem-এর requirement বিবেচনা করতে হবে।

**Next Topic:** `09_Introduction_to_the_while_Loop.md`
