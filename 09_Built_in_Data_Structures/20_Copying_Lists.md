# 20. Copying Lists in Python

## 1. What Is Copying a List?

Python-এ **Copying a List** বলতে একটি List-এর element-গুলো অন্য একটি List-এ কপি করে রাখাকে বোঝায়।

অনেক সময় আমাদের একটি List-এর data অন্য একটি List-এ ব্যবহার করতে হয়। তখন List copy করা প্রয়োজন হয়।

Python-এ List copy করার বিভিন্ন উপায় রয়েছে।

**Example:**

```python
original = [10, 20, 30, 40]

copied = original.copy()

print(original)
print(copied)
```

**Output:**

```text
[10, 20, 30, 40]
[10, 20, 30, 40]
```

এখানে `original` List-এর element-গুলো `copied` List-এ কপি করা হয়েছে।

দুটি List-এর data একই হলেও এগুলো আলাদা List object।

---

## 2. Copying a List Using `copy()`

Python-এর `copy()` method ব্যবহার করে সহজেই একটি List-এর copy তৈরি করা যায়।

**Syntax:**

```python
new_list = original_list.copy()
```

**Example:**

```python
fruits = ["Apple", "Banana", "Mango"]

new_fruits = fruits.copy()

print(new_fruits)
```

**Output:**

```text
['Apple', 'Banana', 'Mango']
```

এখানে `copy()` method ব্যবহার করে `fruits` List-এর একটি copy তৈরি করা হয়েছে।

### Important Points

- `copy()` একটি নতুন List তৈরি করে।
- Original List পরিবর্তন হয় না।
- নতুন List স্বাধীনভাবে modify করা যায়।
- এটি একটি Shallow Copy তৈরি করে।

---

## 3. Copying a List Using Slicing `[:]`

Slicing ব্যবহার করেও একটি List-এর copy তৈরি করা যায়।

এর জন্য `[:]` syntax ব্যবহার করা হয়।

**Syntax:**

```python
new_list = original_list[:]
```

এখানে কোনো start, stop বা step নির্দিষ্ট করা হয়নি। তাই সম্পূর্ণ List copy হয়ে যায়।

**Example:**

```python
numbers = [10, 20, 30, 40]

copied_numbers = numbers[:]

print(copied_numbers)
```

**Output:**

```text
[10, 20, 30, 40]
```

এখানে `numbers[:]` ব্যবহার করে Original List-এর একটি নতুন copy তৈরি করা হয়েছে।

### Important Points

- `[:]` একটি নতুন List তৈরি করে।
- Original List পরিবর্তন হয় না।
- এটি একটি Shallow Copy তৈরি করে।

---

## 4. Copying a List Using `list()`

Python-এর built-in `list()` function ব্যবহার করেও একটি List-এর copy তৈরি করা যায়।

**Syntax:**

```python
new_list = list(original_list)
```

**Example:**

```python
numbers = [10, 20, 30, 40]

copied_numbers = list(numbers)

print(copied_numbers)
```

**Output:**

```text
[10, 20, 30, 40]
```

এখানে `list()` function ব্যবহার করে একটি নতুন List তৈরি করা হয়েছে।

### Important Points

- `list()` একটি নতুন List তৈরি করে।
- Original List পরিবর্তন হয় না।
- এটি একটি Shallow Copy তৈরি করে।
- অন্য iterable থেকেও List তৈরি করা যায়।

---

## 5. Difference Between Assignment and Copying

Python-এ Assignment এবং Copying এক বিষয় নয়।

Assignment ব্যবহার করলে নতুন List তৈরি হয় না। বরং দুটি variable একই List object-কে reference করে।

অন্যদিকে Copying ব্যবহার করলে একটি নতুন List object তৈরি হয়।

**Example 1: Using Assignment**

```python
original = [10, 20, 30]

copied = original

copied.append(40)

print(original)
print(copied)
```

**Output:**

```text
[10, 20, 30, 40]
[10, 20, 30, 40]
```

এখানে `copied = original` করার কারণে দুটি variable একই List object-কে reference করছে।

তাই একটি List পরিবর্তন করলে অন্য variable দিয়েও সেই পরিবর্তন দেখা যায়।

**Example 2: Using Copying**

```python
original = [10, 20, 30]

copied = original.copy()

copied.append(40)

print(original)
print(copied)
```

**Output:**

```text
[10, 20, 30]
[10, 20, 30, 40]
```

এখানে `copy()` ব্যবহার করে আলাদা List তৈরি করা হয়েছে।

তাই `copied` পরিবর্তন করলেও `original` পরিবর্তন হয়নি।

### Comparison

| Feature | Assignment | Copying |
|---|---|---|
| Syntax | `b = a` | `b = a.copy()` |
| New List | No | Yes |
| Object | Same | Different |
| Changes | Both affected | Outer List independent |

**Remember:** Assignment একটি নতুন reference তৈরি করে, কিন্তু Copying একটি নতুন List object তৈরি করে।

---

## 6. Understanding Shallow Copy

Python-এ `copy()`, `[:]` এবং `list()` ব্যবহার করলে Shallow Copy তৈরি হয়।

Shallow Copy বলতে এমন একটি copy-কে বোঝায়, যেখানে নতুন outer List তৈরি হয়, কিন্তু nested object-গুলোর আলাদা copy তৈরি হয় না।

**Example:**

```python
original = [[10, 20], [30, 40]]

copied = original.copy()

copied[0].append(50)

print(original)
print(copied)
```

**Output:**

```text
[[10, 20, 50], [30, 40]]
[[10, 20, 50], [30, 40]]
```

এখানে:

- `original` এবং `copied` দুটি আলাদা outer List।
- কিন্তু nested List-গুলো একই object-কে reference করছে।
- তাই nested List পরিবর্তন করলে উভয় List-এ পরিবর্তন দেখা যায়।

**Note:** Shallow Copy এবং Deep Copy সম্পর্কে বিস্তারিত আমরা পরবর্তী Advanced Concepts topic-এ শিখব।

---

## 7. Checking Whether Two Lists Are the Same Object

Python-এ `is` operator ব্যবহার করে দুটি variable একই object-কে reference করছে কি না তা পরীক্ষা করা যায়।

**Example:**

```python
original = [10, 20, 30]

copied = original.copy()

assigned = original

print(original is copied)
print(original is assigned)
```

**Output:**

```text
False
True
```

এখানে:

- `original is copied` এর ফলাফল `False`, কারণ দুটি আলাদা List object।
- `original is assigned` এর ফলাফল `True`, কারণ দুটি variable একই List object-কে reference করছে।

**Remember:**

- `==` দুটি List-এর value তুলনা করে।
- `is` দুটি variable একই object কি না তা পরীক্ষা করে।

---

## 8. Different Ways to Copy a List

Python-এ একটি List copy করার কয়েকটি সহজ পদ্ধতি রয়েছে।

| Method | Syntax | Result |
|---|---|---|
| `copy()` | `a.copy()` | New List |
| Slicing | `a[:]` | New List |
| `list()` | `list(a)` | New List |
| Assignment | `b = a` | Same Object |

**Example:**

```python
numbers = [10, 20, 30]

copy1 = numbers.copy()
copy2 = numbers[:]
copy3 = list(numbers)
copy4 = numbers

print(copy1)
print(copy2)
print(copy3)
print(copy4)
```

**Output:**

```text
[10, 20, 30]
[10, 20, 30]
[10, 20, 30]
[10, 20, 30]
```

দেখতে সবগুলোর output একই হলেও `copy4` ছাড়া বাকি তিনটি নতুন List object তৈরি করেছে।

---

## 9. Common Beginner Mistakes

### Mistake 1: Thinking Assignment Creates a New List

**Incorrect Understanding:**

```python
numbers = [10, 20, 30]

new_numbers = numbers

new_numbers.append(40)

print(numbers)
```

**Output:**

```text
[10, 20, 30, 40]
```

কারণ Assignment ব্যবহার করলে নতুন List তৈরি হয় না। দুটি variable একই List object-কে reference করে।

### Mistake 2: Confusing `copy()` with Deep Copy

```python
original = [[1, 2], [3, 4]]

copied = original.copy()

copied[0].append(5)

print(original)
```

**Output:**

```text
[[1, 2, 5], [3, 4]]
```

কারণ `copy()` একটি Shallow Copy তৈরি করে। Nested List-গুলোর আলাদা copy তৈরি হয় না।

### Mistake 3: Thinking Two Equal Lists Are the Same Object

```python
a = [10, 20, 30]
b = [10, 20, 30]

print(a == b)
print(a is b)
```

**Output:**

```text
True
False
```

কারণ দুটি List-এর value একই হলেও তারা আলাদা object।

---

## 10. Important Points to Remember

1. List copy করলে একটি নতুন List object তৈরি হয়।
2. `copy()` method দিয়ে List copy করা যায়।
3. `[:]` slicing দিয়েও List copy করা যায়।
4. `list()` function ব্যবহার করেও List copy করা যায়।
5. Assignment (`b = a`) নতুন List তৈরি করে না।
6. Assignment করলে দুটি variable একই List object-কে reference করে।
7. `copy()`, `[:]` এবং `list()` Shallow Copy তৈরি করে।
8. Shallow Copy-তে নতুন outer List তৈরি হয়।
9. Nested object-গুলোর আলাদা copy তৈরি হয় না।
10. `==` value তুলনা করে।
11. `is` object identity পরীক্ষা করে।

---

## 11. Practice Exercises

### Exercise 1

`copy()` method ব্যবহার করে নিচের List-এর একটি copy তৈরি করো।

```python
numbers = [10, 20, 30, 40]
```

**Solution:**

```python
numbers = [10, 20, 30, 40]

copied_numbers = numbers.copy()

print(copied_numbers)
```

**Output:**

```text
[10, 20, 30, 40]
```

### Exercise 2

Slicing ব্যবহার করে একটি List copy করো।

```python
fruits = ["Apple", "Banana", "Mango"]
```

**Solution:**

```python
fruits = ["Apple", "Banana", "Mango"]

new_fruits = fruits[:]

print(new_fruits)
```

**Output:**

```text
['Apple', 'Banana', 'Mango']
```

### Exercise 3

`list()` function ব্যবহার করে একটি List copy করো।

```python
numbers = [5, 10, 15, 20]
```

**Solution:**

```python
numbers = [5, 10, 15, 20]

new_numbers = list(numbers)

print(new_numbers)
```

**Output:**

```text
[5, 10, 15, 20]
```

### Exercise 4

নিচের code-এর output কী হবে?

```python
a = [10, 20, 30]

b = a

b.append(40)

print(a)
print(b)
```

**Solution:**

```text
[10, 20, 30, 40]
[10, 20, 30, 40]
```

### Exercise 5

নিচের code-এর output কী হবে?

```python
a = [10, 20, 30]

b = a.copy()

b.append(40)

print(a)
print(b)
```

**Solution:**

```text
[10, 20, 30]
[10, 20, 30, 40]
```

### Exercise 6

নিচের code-এর output কী হবে?

```python
a = [1, 2, 3]
b = [1, 2, 3]

print(a == b)
print(a is b)
```

**Solution:**

```text
True
False
```

### Exercise 7

নিচের code-এর output কী হবে?

```python
a = [[10, 20], [30, 40]]

b = a.copy()

b[0].append(50)

print(a)
print(b)
```

**Solution:**

```text
[[10, 20, 50], [30, 40]]
[[10, 20, 50], [30, 40]]
```

---

## 12. Chapter Summary

এই topic-এ আমরা Python-এ List copy করার বিভিন্ন পদ্ধতি শিখেছি।

- `copy()` method দিয়ে List copy করা যায়।
- `[:]` slicing ব্যবহার করেও copy তৈরি করা যায়।
- `list()` function দিয়েও List copy করা যায়।
- Assignment এবং Copying এক বিষয় নয়।
- Assignment একই object-এর reference তৈরি করে।
- Copying একটি নতুন outer List তৈরি করে।
- উপরের তিনটি copying method Shallow Copy তৈরি করে।
- `==` value এবং `is` object identity পরীক্ষা করে।

---

## 13. Self-Assessment Checklist

নিজে যাচাই করো:

- [ ] List copying কী তা বুঝতে পেরেছি।
- [ ] `copy()` method ব্যবহার করতে পারি।
- [ ] Slicing ব্যবহার করে List copy করতে পারি।
- [ ] `list()` function দিয়ে List copy করতে পারি।
- [ ] Assignment এবং Copying-এর পার্থক্য বুঝতে পেরেছি।
- [ ] Shallow Copy-এর basic ধারণা বুঝতে পেরেছি।
- [ ] `==` এবং `is`-এর পার্থক্য বুঝতে পেরেছি।
- [ ] Copying সম্পর্কিত common mistakes বুঝতে পেরেছি।

---

## 14. Next Topic

**21. List Concatenation and Repetition**

পরবর্তী topic-এ আমরা শিখব কীভাবে `+` operator ব্যবহার করে দুটি List একসাথে যুক্ত করতে হয় এবং `*` operator ব্যবহার করে List-এর element বারবার repeat করতে হয়।