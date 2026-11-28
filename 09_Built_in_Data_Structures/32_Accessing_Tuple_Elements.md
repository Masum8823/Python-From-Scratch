# **32. Accessing Tuple Elements in Python**

## 1. Introduction

Python-এ Tuple-এর মধ্যে থাকা প্রতিটি element আলাদাভাবে access করা যায় **Index Number** ব্যবহার করে।

প্রতিটি element-এর একটি নির্দিষ্ট index থাকে, যার মাধ্যমে আমরা সহজেই সেই element বের করতে পারি।

```python
fruits = ("Apple", "Banana", "Mango", "Orange")

print(fruits[0])
print(fruits[1])
```

**Output:**
```text
Apple
Banana
```

এখানে `fruits[0]` প্রথম element এবং `fruits[1]` দ্বিতীয় element access করেছে।

## 2. Accessing Elements Using Positive Indexing

Positive indexing ব্যবহার করে বাম দিক থেকে element access করা হয়।

Index সবসময় `0` থেকে শুরু হয়।

```python
colors = ("Red", "Green", "Blue", "Yellow")

print(colors[0])
print(colors[1])
print(colors[2])
print(colors[3])
```

**Output:**
```text
Red
Green
Blue
Yellow
```

**Index Position:**

| Element | Index |
|---|---:|
| Red | 0 |
| Green | 1 |
| Blue | 2 |
| Yellow | 3 |

## 3. Accessing Elements Using Negative Indexing

Negative indexing ব্যবহার করে ডান দিক থেকে element access করা যায়।

শেষ element-এর index হলো `-1`।

```python
fruits = ("Apple", "Banana", "Mango", "Orange")

print(fruits[-1])
print(fruits[-2])
print(fruits[-3])
print(fruits[-4])
```

**Output:**
```text
Orange
Mango
Banana
Apple
```

**Negative Index Position:**

| Element | Index |
|---|---:|
| Apple | -4 |
| Banana | -3 |
| Mango | -2 |
| Orange | -1 |

## 4. Accessing the First and Last Elements

Tuple-এর প্রথম এবং শেষ element সহজেই access করা যায়।

```python
numbers = (10, 20, 30, 40, 50)

first = numbers[0]
last = numbers[-1]

print("First Element:", first)
print("Last Element:", last)
```

**Output:**
```text
First Element: 10
Last Element: 50
```

## 5. Accessing Elements Using Variables

Index number একটি variable-এর মধ্যেও রাখা যায়।

```python
subjects = ("Python", "Java", "C++", "JavaScript")

index = 2

print(subjects[index])
```

**Output:**
```text
C++
```

এখানে `index` variable-এর value `2`, তাই তৃতীয় element access হয়েছে।

## 6. Accessing Elements Using len()

`len()` function ব্যবহার করে Tuple-এর মোট element সংখ্যা জানা যায়।

শেষ element access করার জন্য `len()` ব্যবহার করা যায়।

```python
numbers = (10, 20, 30, 40, 50)

last_index = len(numbers) - 1

print(numbers[last_index])
```

**Output:**
```text
50
```

**Explanation:**

- `len(numbers)` = 5
- `last_index = 5 - 1 = 4`
- `numbers[4]` = 50

## 7. IndexError in Tuple

Tuple-এর মধ্যে যতগুলো element আছে, তার বাইরের কোনো index access করতে গেলে Python `IndexError` দেখায়।

```python
numbers = (10, 20, 30)

print(numbers[5])
```

**Output:**
```text
IndexError: tuple index out of range
```

কারণ Tuple-এ মাত্র 3টি element আছে এবং valid positive index হলো `0`, `1`, `2`।

## 8. Important Rules

1. Tuple indexing সবসময় `0` থেকে শুরু হয়।
2. Positive indexing বাম দিক থেকে কাজ করে।
3. Negative indexing ডান দিক থেকে কাজ করে।
4. শেষ element-এর negative index হলো `-1`।
5. Index ব্যবহার করে নির্দিষ্ট element access করা যায়।
6. Invalid index ব্যবহার করলে `IndexError` হয়।
7. Tuple-এর element access করা যায়, কিন্তু সরাসরি পরিবর্তন করা যায় না।

## 9. Common Mistakes

**Mistake 1: Starting index from 1**

```python
numbers = (10, 20, 30)

print(numbers[1])
```

**Output:**
```text
20
```

মনে রাখতে হবে, `numbers[1]` দ্বিতীয় element, প্রথমটি নয়।

**Mistake 2: Using an invalid index**

```python
numbers = (10, 20, 30)

print(numbers[3])
```

এখানে `IndexError` হবে, কারণ শেষ valid index হলো `2`।

**Mistake 3: Confusing negative indexing**

```python
numbers = (10, 20, 30)

print(numbers[-1])
```

**Output:**
```text
30
```

মনে রাখতে হবে, `-1` হলো শেষ element।

## 10. Practice Exercises

**Exercise 1:** নিচের Tuple থেকে প্রথম element print করো।

```python
animals = ("Cat", "Dog", "Tiger", "Lion")
```

**Solution:**
```python
animals = ("Cat", "Dog", "Tiger", "Lion")

print(animals[0])
```

**Output:**
```text
Cat
```

**Exercise 2:** Negative indexing ব্যবহার করে শেষ element print করো।

```python
numbers = (5, 10, 15, 20, 25)
```

**Solution:**
```python
numbers = (5, 10, 15, 20, 25)

print(numbers[-1])
```

**Output:**
```text
25
```

**Exercise 3:** Variable ব্যবহার করে তৃতীয় element print করো।

```python
languages = ("Python", "Java", "C", "C++")
```

**Solution:**
```python
languages = ("Python", "Java", "C", "C++")

index = 2

print(languages[index])
```

**Output:**
```text
C
```

**Exercise 4:** `len()` ব্যবহার করে Tuple-এর শেষ element print করো।

```python
marks = (70, 80, 85, 90, 95)
```

**Solution:**
```python
marks = (70, 80, 85, 90, 95)

print(marks[len(marks) - 1])
```

**Output:**
```text
95
```

## 11. Chapter Summary

- Tuple elements index ব্যবহার করে access করা যায়।
- Positive indexing `0` থেকে শুরু হয়।
- Negative indexing `-1` থেকে শুরু হয়।
- `len()` দিয়ে Tuple-এর মোট element সংখ্যা জানা যায়।
- Invalid index ব্যবহার করলে `IndexError` হয়।

## 12. Self-Assessment Checklist

- [ ] Tuple element access করতে পারি।
- [ ] Positive indexing বুঝি।
- [ ] Negative indexing বুঝি।
- [ ] First এবং last element access করতে পারি।
- [ ] Variable ব্যবহার করে element access করতে পারি।
- [ ] `len()` ব্যবহার করে last element বের করতে পারি।
- [ ] `IndexError` বুঝতে পারি।

## 13. Next Topic

**33. Tuple Indexing and Slicing in Python**

পরবর্তী topic-এ Tuple-এর indexing এবং slicing আরও বিস্তারিতভাবে শিখব।