# 21. List Concatenation and Repetition in Python

## 1. What Is List Concatenation?

Python-এ **List Concatenation** বলতে দুটি বা তার বেশি List একসাথে যুক্ত করাকে বোঝায়।

এর জন্য `+` operator ব্যবহার করা হয়।

**Syntax:**

```python
new_list = list1 + list2
```

**Example:**

```python
list1 = [10, 20, 30]
list2 = [40, 50, 60]

result = list1 + list2

print(result)
```

**Output:**

```text
[10, 20, 30, 40, 50, 60]
```

এখানে `+` operator ব্যবহার করে দুটি List একসাথে যুক্ত করা হয়েছে।

### Important Points

- `+` operator দিয়ে দুটি List যুক্ত করা যায়।
- এটি একটি নতুন List তৈরি করে।
- Original List পরিবর্তন হয় না।
- List-এর element-গুলোর original order বজায় থাকে।

---

## 2. Concatenating Multiple Lists

আমরা চাইলে দুটি List-এর বেশি List-ও একসাথে যুক্ত করতে পারি।

**Example:**

```python
list1 = [10, 20]
list2 = [30, 40]
list3 = [50, 60]

result = list1 + list2 + list3

print(result)
```

**Output:**

```text
[10, 20, 30, 40, 50, 60]
```

এখানে তিনটি List একসাথে যুক্ত করা হয়েছে।

---

## 3. Concatenating Lists with Different Data Types

Python List-এ বিভিন্ন ধরনের data রাখা যায়। তাই ভিন্ন data type-এর element থাকা দুটি List-ও concatenate করা যায়।

**Example:**

```python
list1 = [10, 20, 30]
list2 = ["Python", "Java", "C++"]

result = list1 + list2

print(result)
```

**Output:**

```text
[10, 20, 30, 'Python', 'Java', 'C++']
```

এখানে একটি List-এ Integer এবং অন্য List-এ String রয়েছে।

তবুও দুটি List সফলভাবে যুক্ত হয়েছে।

---

## 4. What Is List Repetition?

Python-এ **List Repetition** বলতে একটি List-এর element-গুলোকে নির্দিষ্ট সংখ্যক বার repeat করাকে বোঝায়।

এর জন্য `*` operator ব্যবহার করা হয়।

**Syntax:**

```python
new_list = list_name * number
```

এখানে `number` নির্ধারণ করে List কতবার repeat হবে।

**Example:**

```python
numbers = [10, 20, 30]

result = numbers * 3

print(result)
```

**Output:**

```text
[10, 20, 30, 10, 20, 30, 10, 20, 30]
```

এখানে সম্পূর্ণ List তিনবার repeat হয়েছে।

### Important Points

- `*` operator দিয়ে List repeat করা যায়।
- এটি একটি নতুন List তৈরি করে।
- Original List পরিবর্তন হয় না।
- Repeat করার জন্য Integer ব্যবহার করতে হয়।

---

## 5. Repeating a List with Different Numbers

List-কে বিভিন্ন সংখ্যক বার repeat করা যায়।

**Example:**

```python
fruits = ["Apple", "Banana"]

print(fruits * 2)
print(fruits * 3)
print(fruits * 4)
```

**Output:**

```text
['Apple', 'Banana', 'Apple', 'Banana']
['Apple', 'Banana', 'Apple', 'Banana', 'Apple', 'Banana']
['Apple', 'Banana', 'Apple', 'Banana', 'Apple', 'Banana', 'Apple', 'Banana']
```

এখানে প্রতিবার `*` operator-এর সংখ্যার ওপর ভিত্তি করে List repeat হয়েছে।

---

## 6. Using Zero and Negative Numbers with Repetition

List repetition-এর ক্ষেত্রে Zero এবং Negative Number ব্যবহার করলেও কোনো error হয় না।

**Example:**

```python
numbers = [10, 20, 30]

print(numbers * 0)
print(numbers * -2)
```

**Output:**

```text
[]
[]
```

এখানে:

- `numbers * 0` একটি Empty List তৈরি করেছে।
- `numbers * -2`-ও একটি Empty List তৈরি করেছে।

কারণ Zero বা Negative Number দিয়ে List repeat করলে কোনো element পাওয়া যায় না।

---

## 7. Difference Between Concatenation and Repetition

Concatenation এবং Repetition দুটি আলাদা operation।

| Feature | Concatenation | Repetition |
|---|---|---|
| Operator | `+` | `*` |
| Purpose | Lists যুক্ত করা | List repeat করা |
| Example | `a + b` | `a * 3` |
| Result | Combined List | Repeated List |

**Example:**

```python
numbers = [10, 20]

print(numbers + [30, 40])
print(numbers * 3)
```

**Output:**

```text
[10, 20, 30, 40]
[10, 20, 10, 20, 10, 20]
```

---

## 8. Important Difference Between `+` and `append()`

`+` এবং `append()` উভয় ব্যবহার করে List-এ data যোগ করা যায়। তবে এদের কাজের মধ্যে পার্থক্য রয়েছে।

**Example 1: Using `+`**

```python
numbers = [10, 20, 30]

result = numbers + [40, 50]

print(result)
```

**Output:**

```text
[10, 20, 30, 40, 50]
```

এখানে দুটি List যুক্ত করে একটি নতুন List তৈরি হয়েছে।

**Example 2: Using `append()`**

```python
numbers = [10, 20, 30]

numbers.append([40, 50])

print(numbers)
```

**Output:**

```text
[10, 20, 30, [40, 50]]
```

এখানে `append()` পুরো `[40, 50]` List-টিকে একটি single element হিসেবে যোগ করেছে।

**Remember:**

- `+` দুটি List concatenate করে।
- `append()` একটি element যোগ করে।
- `append()` ব্যবহার করলে List-এর শেষে নতুন element যুক্ত হয়।

---

## 9. Concatenation and Repetition with Nested Lists

Nested List-এর ক্ষেত্রেও Concatenation এবং Repetition ব্যবহার করা যায়।

**Example 1: Concatenation**

```python
list1 = [[10, 20], [30, 40]]
list2 = [[50, 60]]

result = list1 + list2

print(result)
```

**Output:**

```text
[[10, 20], [30, 40], [50, 60]]
```

**Example 2: Repetition**

```python
numbers = [[10, 20], [30, 40]]

result = numbers * 2

print(result)
```

**Output:**

```text
[[10, 20], [30, 40], [10, 20], [30, 40]]
```

**Note:** Nested List repetition করলে একই nested object-এর reference repeat হয়। তাই একটি nested List পরিবর্তন করলে একই reference-এর অন্য অবস্থানেও পরিবর্তন দেখা যেতে পারে।

---

## 10. Common Beginner Mistakes

### Mistake 1: Adding an Integer Directly to a List

**Incorrect:**

```python
numbers = [10, 20, 30]

result = numbers + 40

print(result)
```

**Output:**

```text
TypeError
```

কারণ `+` operator দিয়ে List-এর সাথে সরাসরি Integer যোগ করা যায় না।

**Correct:**

```python
numbers = [10, 20, 30]

result = numbers + [40]

print(result)
```

**Output:**

```text
[10, 20, 30, 40]
```

### Mistake 2: Confusing `append()` with Concatenation

```python
numbers = [10, 20]

numbers.append([30, 40])

print(numbers)
```

**Output:**

```text
[10, 20, [30, 40]]
```

এখানে সম্পূর্ণ List-টি একটি element হিসেবে যুক্ত হয়েছে।

দুটি List একসাথে যুক্ত করতে `+` operator ব্যবহার করতে হবে।

### Mistake 3: Thinking Repetition Changes the Original List

```python
numbers = [10, 20]

result = numbers * 3

print(numbers)
print(result)
```

**Output:**

```text
[10, 20]
[10, 20, 10, 20, 10, 20]
```

কারণ Repetition একটি নতুন List তৈরি করে। Original List পরিবর্তন হয় না।

### Mistake 4: Using a Float for Repetition

**Incorrect:**

```python
numbers = [10, 20, 30]

print(numbers * 2.5)
```

**Output:**

```text
TypeError
```

কারণ List repetition-এর জন্য Integer প্রয়োজন।

---

## 11. Important Points to Remember

1. List Concatenation-এর জন্য `+` operator ব্যবহার করা হয়।
2. List Repetition-এর জন্য `*` operator ব্যবহার করা হয়।
3. Concatenation দুটি বা তার বেশি List যুক্ত করে।
4. Repetition একটি List-কে নির্দিষ্ট সংখ্যক বার repeat করে।
5. `+` এবং `*` উভয়ই নতুন List তৈরি করে।
6. Original List পরিবর্তন হয় না।
7. Zero দিয়ে repeat করলে Empty List পাওয়া যায়।
8. Negative Number দিয়েও repeat করলে Empty List পাওয়া যায়।
9. `append()` একটি element যোগ করে।
10. `+` operator দিয়ে দুটি List concatenate করা যায়।
11. Nested List repetition-এ একই nested object-এর reference repeat হতে পারে।

---

## 12. Practice Exercises

### Exercise 1

নিচের দুটি List concatenate করো।

```python
list1 = [10, 20, 30]
list2 = [40, 50, 60]
```

**Solution:**

```python
list1 = [10, 20, 30]
list2 = [40, 50, 60]

result = list1 + list2

print(result)
```

**Output:**

```text
[10, 20, 30, 40, 50, 60]
```

### Exercise 2

একটি List-কে তিনবার repeat করো।

```python
numbers = [1, 2, 3]
```

**Solution:**

```python
numbers = [1, 2, 3]

result = numbers * 3

print(result)
```

**Output:**

```text
[1, 2, 3, 1, 2, 3, 1, 2, 3]
```

### Exercise 3

তিনটি List একসাথে concatenate করো।

```python
a = [10, 20]
b = [30, 40]
c = [50, 60]
```

**Solution:**

```python
a = [10, 20]
b = [30, 40]
c = [50, 60]

result = a + b + c

print(result)
```

**Output:**

```text
[10, 20, 30, 40, 50, 60]
```

### Exercise 4

নিচের code-এর output কী হবে?

```python
numbers = [10, 20]

print(numbers * 0)
print(numbers * 2)
```

**Solution:**

```text
[]
[10, 20, 10, 20]
```

### Exercise 5

নিচের code-এর output কী হবে?

```python
numbers = [1, 2, 3]

result = numbers + [4, 5]

print(numbers)
print(result)
```

**Solution:**

```text
[1, 2, 3]
[1, 2, 3, 4, 5]
```

### Exercise 6

নিচের code-এর output কী হবে?

```python
numbers = [10, 20]

numbers.append([30, 40])

print(numbers)
```

**Solution:**

```text
[10, 20, [30, 40]]
```

### Exercise 7

নিচের code-এর output কী হবে?

```python
numbers = [1, 2]

result = numbers * 3

result.append(3)

print(numbers)
print(result)
```

**Solution:**

```text
[1, 2]
[1, 2, 1, 2, 1, 2, 3]
```

### Exercise 8

নিচের code-এর output কী হবে?

```python
a = [10, 20]
b = [30, 40]

result = (a + b) * 2

print(result)
```

**Solution:**

```text
[10, 20, 30, 40, 10, 20, 30, 40]
```

---

## 13. Chapter Summary

এই topic-এ আমরা Python-এ List Concatenation এবং Repetition শিখেছি।

- `+` operator ব্যবহার করে দুটি বা তার বেশি List যুক্ত করা যায়।
- `*` operator ব্যবহার করে List repeat করা যায়।
- Concatenation এবং Repetition নতুন List তৈরি করে।
- Original List পরিবর্তন হয় না।
- `append()` এবং `+` operator-এর কাজ আলাদা।
- Zero এবং Negative Number দিয়ে repeat করলে Empty List পাওয়া যায়।
- Nested List repetition-এর ক্ষেত্রে একই nested object-এর reference repeat হতে পারে।

---

## 14. Self-Assessment Checklist

নিজে যাচাই করো:

- [ ] List Concatenation কী তা বুঝতে পেরেছি।
- [ ] `+` operator ব্যবহার করে List যুক্ত করতে পারি।
- [ ] একাধিক List concatenate করতে পারি।
- [ ] List Repetition কী তা বুঝতে পেরেছি।
- [ ] `*` operator ব্যবহার করে List repeat করতে পারি।
- [ ] Zero এবং Negative Number দিয়ে repetition-এর ফলাফল বুঝতে পারি।
- [ ] `append()` এবং Concatenation-এর পার্থক্য বুঝতে পেরেছি।
- [ ] Nested List-এর Concatenation এবং Repetition বুঝতে পেরেছি।
- [ ] Common mistakes শনাক্ত করতে পারি।

---

## 15. Next Topic

**22. List Iteration with `for` and `while` Loops**

পরবর্তী topic-এ আমরা শিখব কীভাবে `for` এবং `while` loop ব্যবহার করে List-এর প্রতিটি element access, read এবং process করতে হয়।