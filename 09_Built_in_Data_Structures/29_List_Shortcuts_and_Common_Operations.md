# 29. List Shortcuts and Common Operations in Python

## 1. Introduction to List Shortcuts

Python-এ List নিয়ে কাজ করার সময় কিছু shortcut এবং common operations ব্যবহার করে সহজেই বিভিন্ন কাজ করা যায়।

এগুলোর মাধ্যমে আমরা:

- দুটি List একসাথে যুক্ত করতে পারি।
- List-এর elements repeat করতে পারি।
- List-এর length বের করতে পারি।
- Maximum এবং minimum value খুঁজে বের করতে পারি।
- List-এর elements-এর total sum বের করতে পারি।
- কোনো element List-এ আছে কি না পরীক্ষা করতে পারি।

---

## 2. List Concatenation Using `+`

**List Concatenation** হলো দুটি বা তার বেশি List-কে একসাথে যুক্ত করা।

এক্ষেত্রে `+` operator ব্যবহার করা হয়।

**Syntax:**

```python
new_list = list1 + list2
```

**Example:**

```python
numbers1 = [10, 20, 30]
numbers2 = [40, 50, 60]

result = numbers1 + numbers2

print(result)
```

**Output:**

```text
[10, 20, 30, 40, 50, 60]
```

এখানে `numbers1` এবং `numbers2` একসাথে যুক্ত হয়ে একটি নতুন List তৈরি হয়েছে।

**Important Points:**

- `+` operator দুটি List যুক্ত করে।
- Original List পরিবর্তন হয় না।
- একটি নতুন List তৈরি হয়।

---

## 3. List Repetition Using `*`

একটি List-এর elements একাধিকবার repeat করার জন্য `*` operator ব্যবহার করা হয়।

**Syntax:**

```python
new_list = list * number
```

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

এখানে সম্পূর্ণ List-টি তিনবার repeat হয়েছে।

আরও একটি Example:

```python
fruits = ["Apple", "Mango"]

print(fruits * 2)
```

**Output:**

```text
['Apple', 'Mango', 'Apple', 'Mango']
```

---

## 4. Finding the Length Using `len()`

একটি List-এ মোট কতগুলো element রয়েছে তা জানার জন্য `len()` function ব্যবহার করা হয়।

**Syntax:**

```python
len(list_name)
```

**Example:**

```python
students = ["Masum", "Rahim", "Karim", "Sakib"]

print(len(students))
```

**Output:**

```text
4
```

এখানে List-এ মোট চারটি element রয়েছে।

**Important Point:**

`len()` List-এর মোট element সংখ্যা return করে।

---

## 5. Finding the Maximum Value Using `max()`

একটি List থেকে সবচেয়ে বড় value বের করার জন্য `max()` function ব্যবহার করা হয়।

**Syntax:**

```python
max(list_name)
```

**Example:**

```python
numbers = [10, 50, 20, 80, 30]

print(max(numbers))
```

**Output:**

```text
80
```

এখানে `80` হলো List-এর সবচেয়ে বড় value।

---

## 6. Finding the Minimum Value Using `min()`

একটি List থেকে সবচেয়ে ছোট value বের করার জন্য `min()` function ব্যবহার করা হয়।

**Syntax:**

```python
min(list_name)
```

**Example:**

```python
numbers = [10, 50, 20, 80, 30]

print(min(numbers))
```

**Output:**

```text
10
```

এখানে `10` হলো List-এর সবচেয়ে ছোট value।

---

## 7. Calculating the Sum Using `sum()`

একটি List-এর সব numerical elements-এর যোগফল বের করার জন্য `sum()` function ব্যবহার করা হয়।

**Syntax:**

```python
sum(list_name)
```

**Example:**

```python
numbers = [10, 20, 30, 40]

print(sum(numbers))
```

**Output:**

```text
100
```

এখানে:

```text
10 + 20 + 30 + 40 = 100
```

---

## 8. Checking Elements Using `in` and `not in`

List-এর মধ্যে কোনো নির্দিষ্ট element আছে কি না তা পরীক্ষা করার জন্য `in` এবং `not in` operator ব্যবহার করা হয়।

### 8.1 Using `in`

কোনো element List-এর মধ্যে থাকলে `in` operator `True` return করে।

**Example:**

```python
fruits = ["Apple", "Mango", "Banana"]

print("Mango" in fruits)
print("Orange" in fruits)
```

**Output:**

```text
True
False
```

### 8.2 Using `not in`

কোনো element List-এর মধ্যে না থাকলে `not in` operator `True` return করে।

**Example:**

```python
fruits = ["Apple", "Mango", "Banana"]

print("Orange" not in fruits)
print("Apple" not in fruits)
```

**Output:**

```text
True
False
```

---

## 9. Combining Common List Operations

একই program-এ একাধিক List operation ব্যবহার করা যায়।

**Example:**

```python
numbers = [10, 20, 30, 40, 50]

print("Length:", len(numbers))
print("Maximum:", max(numbers))
print("Minimum:", min(numbers))
print("Sum:", sum(numbers))
print("Is 30 available?", 30 in numbers)
```

**Output:**

```text
Length: 5
Maximum: 50
Minimum: 10
Sum: 150
Is 30 available? True
```

---

## 10. Important Points to Remember

1. `+` operator দিয়ে দুটি List যুক্ত করা যায়।
2. `*` operator দিয়ে List-এর elements repeat করা যায়।
3. `len()` দিয়ে List-এর মোট element সংখ্যা বের করা যায়।
4. `max()` দিয়ে সবচেয়ে বড় value পাওয়া যায়।
5. `min()` দিয়ে সবচেয়ে ছোট value পাওয়া যায়।
6. `sum()` দিয়ে numerical elements-এর যোগফল বের করা যায়।
7. `in` operator element আছে কি না পরীক্ষা করে।
8. `not in` operator element নেই কি না পরীক্ষা করে।
9. List concatenation original List পরিবর্তন করে না।
10. `max()`, `min()` এবং `sum()` ব্যবহার করার সময় compatible elements থাকতে হয়।

---

## 11. Common Beginner Mistakes

### Mistake 1: Using `+` with Different Data Types

```python
numbers = [10, 20, 30]

result = numbers + 5
```

**Output:**

```text
TypeError
```

একটি List-এর সাথে সরাসরি Integer যোগ করা যায় না।

### Mistake 2: Using `sum()` with Strings

```python
names = ["Masum", "Rahim", "Karim"]

print(sum(names))
```

**Output:**

```text
TypeError
```

`sum()` সাধারণ String List-এর জন্য ব্যবহার করা যায় না।

### Mistake 3: Confusing `len()` with Indexing

```python
numbers = [10, 20, 30]

print(len(numbers))
print(numbers[2])
```

**Output:**

```text
3
30
```

`len()` element-এর সংখ্যা return করে, আর indexing নির্দিষ্ট position-এর element return করে।

---

## 12. Practice Exercises

### Exercise 1

দুটি List concatenate করো।

**Solution:**

```python
list1 = [10, 20]
list2 = [30, 40]

result = list1 + list2

print(result)
```

**Output:**

```text
[10, 20, 30, 40]
```

### Exercise 2

একটি List তিনবার repeat করো।

**Solution:**

```python
numbers = [1, 2, 3]

print(numbers * 3)
```

**Output:**

```text
[1, 2, 3, 1, 2, 3, 1, 2, 3]
```

### Exercise 3

একটি List-এর length বের করো।

**Solution:**

```python
fruits = ["Apple", "Mango", "Banana"]

print(len(fruits))
```

**Output:**

```text
3
```

### Exercise 4

একটি List-এর maximum এবং minimum value বের করো।

**Solution:**

```python
numbers = [15, 5, 25, 10, 20]

print(max(numbers))
print(min(numbers))
```

**Output:**

```text
25
5
```

### Exercise 5

একটি List-এর সব numerical elements-এর sum বের করো।

**Solution:**

```python
numbers = [10, 20, 30, 40]

print(sum(numbers))
```

**Output:**

```text
100
```

### Exercise 6

পরীক্ষা করো `"Python"` একটি List-এর মধ্যে আছে কি না।

**Solution:**

```python
languages = ["Java", "Python", "C++"]

print("Python" in languages)
```

**Output:**

```text
True
```

---

## 13. Chapter Summary

এই topic-এ আমরা Python List-এর কিছু গুরুত্বপূর্ণ shortcut এবং common operations শিখেছি।

- `+` দিয়ে List concatenate করা যায়।
- `*` দিয়ে List repeat করা যায়।
- `len()` দিয়ে List-এর length বের করা যায়।
- `max()` এবং `min()` দিয়ে maximum ও minimum value পাওয়া যায়।
- `sum()` দিয়ে numerical elements-এর যোগফল বের করা যায়।
- `in` এবং `not in` দিয়ে element membership পরীক্ষা করা যায়।

এই operations ব্যবহার করে Python List-এর বিভিন্ন কাজ সহজে করা যায়।

---

## 14. Self-Assessment Checklist

নিজে যাচাই করো:

- [ ] `+` operator দিয়ে দুটি List যুক্ত করতে পারি।
- [ ] `*` operator দিয়ে List repeat করতে পারি।
- [ ] `len()` function ব্যবহার করতে পারি।
- [ ] `max()` এবং `min()` ব্যবহার করতে পারি।
- [ ] `sum()` function ব্যবহার করতে পারি।
- [ ] `in` এবং `not in` operator ব্যবহার করতে পারি।
- [ ] Common List operations একসাথে ব্যবহার করতে পারি।
- [ ] Basic errors identify করতে পারি।

---

## 15. Next Topic

**30. Introduction to Tuples in Python**

পরবর্তী topic-এ আমরা Python-এর Tuple কী, কেন ব্যবহার করা হয় এবং List-এর সাথে Tuple-এর basic difference সম্পর্কে বিস্তারিত শিখব।