# 19. Reversing Lists in Python

## 1. What Is Reversing a List?

Python-এ **Reversing a List** বলতে List-এর element-গুলোর order উল্টো করে দেওয়াকে বোঝায়।

অর্থাৎ, List-এর প্রথম element শেষ position-এ চলে যায় এবং শেষ element প্রথম position-এ চলে আসে।

**Example:**

```python
numbers = [10, 20, 30, 40, 50]

numbers.reverse()

print(numbers)
```

**Output:**

```text
[50, 40, 30, 20, 10]
```

এখানে List-এর element-গুলোর order উল্টো হয়ে গেছে।

Python-এ List reverse করার দুটি সহজ উপায় রয়েছে:

1. `reverse()` method
2. `[::-1]` slicing

এছাড়া `reversed()` function ব্যবহার করেও reverse order-এ element পাওয়া যায়।

---

## 2. Reversing a List Using `reverse()`

Python-এর `reverse()` method ব্যবহার করে সহজেই একটি List-এর element-গুলোর order উল্টো করা যায়।

**Syntax:**

```python
list_name.reverse()
```

এটি মূল List-টিকেই পরিবর্তন করে।

**Example:**

```python
fruits = ["Apple", "Banana", "Mango", "Orange"]

fruits.reverse()

print(fruits)
```

**Output:**

```text
['Orange', 'Mango', 'Banana', 'Apple']
```

এখানে `reverse()` method মূল List-এর element-গুলোর order পরিবর্তন করেছে।

### Important Points

- `reverse()` মূল List পরিবর্তন করে।
- এটি কোনো নতুন List তৈরি করে না।
- এটি কোনো value return করে না; return value হলো `None`।
- এটি List-এর element-গুলোকে উল্টো করে সাজায়।

---

## 3. Reversing a List Using Slicing `[::-1]`

Python-এ slicing ব্যবহার করেও List reverse করা যায়।

এর জন্য `[::-1]` syntax ব্যবহার করা হয়।

**Syntax:**

```python
list_name[::-1]
```

এখানে:

- `start` নির্দিষ্ট করা হয়নি।
- `stop` নির্দিষ্ট করা হয়নি।
- `step = -1` দেওয়া হয়েছে।

Negative step ব্যবহার করার কারণে List-এর element-গুলো শেষ থেকে শুরু পর্যন্ত পাওয়া যায়।

**Example:**

```python
numbers = [10, 20, 30, 40, 50]

reversed_numbers = numbers[::-1]

print(reversed_numbers)
print(numbers)
```

**Output:**

```text
[50, 40, 30, 20, 10]
[10, 20, 30, 40, 50]
```

এখানে:

- `numbers[::-1]` একটি নতুন reversed List তৈরি করেছে।
- Original List পরিবর্তন হয়নি।
- `reversed_numbers`-এ reversed List সংরক্ষিত হয়েছে।

### Important Points

- `[::-1]` একটি নতুন List return করে।
- Original List অপরিবর্তিত থাকে।
- Original List reverse না করেও reversed copy পাওয়া যায়।

---

## 4. Reversing a List Using `reversed()`

Python-এর built-in `reversed()` function ব্যবহার করেও List-এর element-গুলো reverse order-এ পাওয়া যায়।

**Syntax:**

```python
reversed(list_name)
```

`reversed()` সরাসরি নতুন List return করে না। এটি একটি reverse iterator return করে।

List হিসেবে পেতে `list()` ব্যবহার করতে হয়।

**Example:**

```python
numbers = [10, 20, 30, 40, 50]

reversed_numbers = list(reversed(numbers))

print(reversed_numbers)
print(numbers)
```

**Output:**

```text
[50, 40, 30, 20, 10]
[10, 20, 30, 40, 50]
```

এখানে:

- `reversed(numbers)` reverse iterator তৈরি করেছে।
- `list()` iterator-টিকে List-এ convert করেছে।
- Original List পরিবর্তন হয়নি।

### Important Points

- `reversed()` একটি iterator return করে।
- `list()` ব্যবহার করে নতুন List তৈরি করা যায়।
- Original List পরিবর্তন হয় না।

---

## 5. Difference Between `reverse()`, `[::-1]` and `reversed()`

Python-এ এই তিনটি পদ্ধতিতেই List reverse করা যায়। তবে এদের কাজের মধ্যে কিছু পার্থক্য রয়েছে।

| Feature | `reverse()` | `[::-1]` | `reversed()` |
|---|---|---|---|
| Type | List Method | Slicing | Built-in Function |
| Original List | Changes | Unchanged | Unchanged |
| Returns | `None` | New List | Iterator |
| New List | No | Yes | With `list()` |
| Usage | `a.reverse()` | `a[::-1]` | `reversed(a)` |

**Note:** Original List পরিবর্তন করতে চাইলে `reverse()` ব্যবহার করা যায়। অন্যদিকে Original List অপরিবর্তিত রেখে reversed List পেতে `[::-1]` ব্যবহার করা যায়।

---

## 6. Reversing a List Using a Loop

`for` loop ব্যবহার করেও একটি List-এর element reverse order-এ print করা যায়।

**Example:**

```python
numbers = [10, 20, 30, 40, 50]

for number in reversed(numbers):
    print(number)
```

**Output:**

```text
50
40
30
20
10
```

এখানে `reversed()` function-এর সাহায্যে List-এর element-গুলো শেষ থেকে শুরু পর্যন্ত print করা হয়েছে।

**Another Example:**

```python
numbers = [10, 20, 30, 40, 50]

for i in range(len(numbers) - 1, -1, -1):
    print(numbers[i])
```

**Output:**

```text
50
40
30
20
10
```

এখানে `range()` ব্যবহার করে শেষ index থেকে প্রথম index পর্যন্ত loop চালানো হয়েছে।

---

## 7. Reversing a String Inside a List

একটি List-এর মধ্যে String থাকলেও List reverse করা যায়।

**Example:**

```python
names = ["Masum", "Rahim", "Karim"]

names.reverse()

print(names)
```

**Output:**

```text
['Karim', 'Rahim', 'Masum']
```

এখানে String-গুলোর character পরিবর্তন হয়নি। শুধু List-এর element-গুলোর order উল্টো হয়েছে।

**Remember:** List reverse করা এবং String reverse করা দুটি আলাদা বিষয়।

---

## 8. Common Beginner Mistakes

### Mistake 1: Assigning `reverse()` to Another Variable

**Incorrect:**

```python
numbers = [10, 20, 30]

reversed_numbers = numbers.reverse()

print(reversed_numbers)
```

**Output:**

```text
None
```

কারণ `reverse()` কোনো List return করে না। এটি মূল List পরিবর্তন করে এবং `None` return করে।

**Correct:**

```python
numbers = [10, 20, 30]

numbers.reverse()

print(numbers)
```

**Output:**

```text
[30, 20, 10]
```

### Mistake 2: Thinking `reversed()` Returns a List

```python
numbers = [10, 20, 30]

result = reversed(numbers)

print(result)
```

**Output:**

```text
<list_reverseiterator object at ...>
```

কারণ `reversed()` একটি iterator return করে।

List হিসেবে পেতে:

```python
result = list(reversed(numbers))

print(result)
```

**Output:**

```text
[30, 20, 10]
```

### Mistake 3: Thinking `[::-1]` Changes the Original List

```python
numbers = [10, 20, 30]

numbers[::-1]

print(numbers)
```

**Output:**

```text
[10, 20, 30]
```

কারণ slicing একটি নতুন reversed List তৈরি করে, কিন্তু এখানে সেটি কোথাও সংরক্ষণ করা হয়নি।

**Correct:**

```python
numbers = [10, 20, 30]

numbers = numbers[::-1]

print(numbers)
```

**Output:**

```text
[30, 20, 10]
```

---

## 9. Important Points to Remember

1. List reverse করার জন্য `reverse()`, `[::-1]` এবং `reversed()` ব্যবহার করা যায়।
2. `reverse()` মূল List পরিবর্তন করে।
3. `reverse()` কোনো value return করে না; এটি `None` return করে।
4. `[::-1]` একটি নতুন reversed List তৈরি করে।
5. `[::-1]` ব্যবহার করলে Original List পরিবর্তন হয় না।
6. `reversed()` একটি reverse iterator return করে।
7. `list(reversed())` ব্যবহার করে নতুন List তৈরি করা যায়।
8. `for` loop ব্যবহার করে reverse order-এ element access করা যায়।
9. List reverse করলে element-এর value পরিবর্তন হয় না, শুধু order পরিবর্তন হয়।

---

## 10. Practice Exercises

### Exercise 1

নিচের List-টি `reverse()` method ব্যবহার করে reverse করো।

```python
numbers = [10, 20, 30, 40]
```

**Solution:**

```python
numbers = [10, 20, 30, 40]

numbers.reverse()

print(numbers)
```

**Output:**

```text
[40, 30, 20, 10]
```

### Exercise 2

Slicing ব্যবহার করে একটি নতুন reversed List তৈরি করো।

```python
fruits = ["Apple", "Banana", "Mango"]
```

**Solution:**

```python
fruits = ["Apple", "Banana", "Mango"]

reversed_fruits = fruits[::-1]

print(reversed_fruits)
```

**Output:**

```text
['Mango', 'Banana', 'Apple']
```

### Exercise 3

`reversed()` function ব্যবহার করে একটি List reverse করো।

```python
numbers = [5, 10, 15, 20]
```

**Solution:**

```python
numbers = [5, 10, 15, 20]

result = list(reversed(numbers))

print(result)
```

**Output:**

```text
[20, 15, 10, 5]
```

### Exercise 4

নিচের code-এর output কী হবে?

```python
numbers = [1, 2, 3, 4, 5]

numbers.reverse()

print(numbers)
```

**Solution:**

```text
[5, 4, 3, 2, 1]
```

### Exercise 5

নিচের code-এর output কী হবে?

```python
numbers = [10, 20, 30]

result = numbers[::-1]

print(numbers)
print(result)
```

**Solution:**

```text
[10, 20, 30]
[30, 20, 10]
```

### Exercise 6

নিচের code-এর output কী হবে?

```python
numbers = [1, 2, 3]

result = numbers.reverse()

print(result)
print(numbers)
```

**Solution:**

```text
None
[3, 2, 1]
```

### Exercise 7

`for` loop ব্যবহার করে নিচের List-এর element-গুলো reverse order-এ print করো।

```python
numbers = [10, 20, 30, 40, 50]
```

**Solution:**

```python
numbers = [10, 20, 30, 40, 50]

for number in reversed(numbers):
    print(number)
```

**Output:**

```text
50
40
30
20
10
```

---

## 11. Chapter Summary

এই topic-এ আমরা Python-এ List reverse করার বিভিন্ন পদ্ধতি শিখেছি।

- `reverse()` method মূল List পরিবর্তন করে।
- `[::-1]` slicing একটি নতুন reversed List তৈরি করে।
- `reversed()` একটি reverse iterator return করে।
- `list()` ব্যবহার করে iterator-কে List-এ convert করা যায়।
- `for` loop ব্যবহার করে reverse order-এ element access করা যায়।
- List reverse করলে শুধু element-এর order পরিবর্তন হয়।

---

## 12. Self-Assessment Checklist

নিজে যাচাই করো:

- [ ] List reversing কী তা বুঝতে পেরেছি।
- [ ] `reverse()` method ব্যবহার করতে পারি।
- [ ] `[::-1]` slicing ব্যবহার করতে পারি।
- [ ] `reversed()` function ব্যবহার করতে পারি।
- [ ] `reverse()` এবং `reversed()`-এর পার্থক্য বুঝতে পেরেছি।
- [ ] Original List কখন পরিবর্তন হয় তা বুঝতে পেরেছি।
- [ ] Loop ব্যবহার করে reverse order-এ element print করতে পারি।
- [ ] Reversing সম্পর্কিত common mistakes বুঝতে পেরেছি।

---

## 13. Next Topic

**20. Copying Lists in Python**

পরবর্তী topic-এ আমরা শিখব কীভাবে Python-এ একটি List-এর copy তৈরি করতে হয় এবং Assignment ও Copy-এর মধ্যে পার্থক্য কী।