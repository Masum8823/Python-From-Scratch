# 30. Introduction to Tuples in Python

## 1. What Is a Tuple?

**Tuple** হলো Python-এর একটি Built-in Data Structure, যেখানে একটি variable-এর মধ্যে একাধিক value সংরক্ষণ করা যায়।

Tuple দেখতে List-এর মতো হলেও এর প্রধান পার্থক্য হলো, Tuple-এর elements পরিবর্তন করা যায় না (Immutable)।

**Important Features:**

- Tuple তৈরি করতে Parentheses `()` ব্যবহার করা হয়।
- Tuple Ordered, অর্থাৎ elements-এর নির্দিষ্ট position থাকে।
- Tuple Immutable, অর্থাৎ তৈরি করার পর elements পরিবর্তন করা যায় না।
- Duplicate values রাখা যায়।
- Tuple-এর elements বিভিন্ন data type-এর হতে পারে।
- Tuple Indexing এবং Slicing support করে।

**Example:**

```python
fruits = ("Apple", "Banana", "Mango")

print(fruits)
```

**Output:**

```text
('Apple', 'Banana', 'Mango')
```

এখানে `fruits` একটি Tuple, যেখানে তিনটি fruit-এর নাম সংরক্ষণ করা হয়েছে।

---

## 2. Why Do We Use Tuples?

Programming-এ কিছু data থাকে যেগুলো পরিবর্তন করার প্রয়োজন হয় না।

এ ধরনের data সংরক্ষণের জন্য Tuple ব্যবহার করা যায়।

**Examples:**

- একজন শিক্ষার্থীর স্থায়ী registration information।
- কোনো location-এর coordinates।
- সপ্তাহের দিনের নাম।
- RGB color values।
- নির্দিষ্ট configuration data।

**Example:**

```python
coordinates = (10, 20)

print(coordinates)
```

**Output:**

```text
(10, 20)
```

এখানে `coordinates` Tuple ব্যবহার করে দুটি coordinate value সংরক্ষণ করা হয়েছে।

---

## 3. Tuple Syntax

Tuple তৈরি করতে সাধারণত Parentheses `()` ব্যবহার করা হয়।

**Syntax:**

```python
tuple_name = (value1, value2, value3)
```

**Example:**

```python
numbers = (10, 20, 30, 40)

print(numbers)
```

**Output:**

```text
(10, 20, 30, 40)
```

এখানে `numbers` একটি Tuple।

---

## 4. Main Characteristics of Tuples

### 4.1 Ordered

Tuple-এর elements নির্দিষ্ট order অনুযায়ী সংরক্ষিত থাকে।

প্রতিটি element-এর একটি নির্দিষ্ট index থাকে।

**Example:**

```python
colors = ("Red", "Green", "Blue")

print(colors)
```

**Output:**

```text
('Red', 'Green', 'Blue')
```

এখানে elements-এর order বজায় রয়েছে।

### 4.2 Immutable

Tuple তৈরি করার পর এর elements সরাসরি পরিবর্তন করা যায় না।

**Example:**

```python
numbers = (10, 20, 30)

numbers[0] = 100

print(numbers)
```

**Output:**

```text
TypeError
```

কারণ Tuple Immutable।

### 4.3 Allows Duplicate Values

Tuple-এর মধ্যে একই value একাধিকবার রাখা যায়।

**Example:**

```python
numbers = (10, 20, 10, 30, 20)

print(numbers)
```

**Output:**

```text
(10, 20, 10, 30, 20)
```

এখানে `10` এবং `20` একাধিকবার রয়েছে।

### 4.4 Supports Different Data Types

একটি Tuple-এর মধ্যে বিভিন্ন ধরনের data রাখা যায়।

**Example:**

```python
student = ("Masum", 22, 3.95, True)

print(student)
```

**Output:**

```text
('Masum', 22, 3.95, True)
```

এখানে String, Integer, Float এবং Boolean value রয়েছে।

### 4.5 Supports Indexing and Slicing

Tuple-এর elements Indexing এবং Slicing ব্যবহার করে access করা যায়।

**Example:**

```python
fruits = ("Apple", "Banana", "Mango")

print(fruits[0])
print(fruits[1:3])
```

**Output:**

```text
Apple
('Banana', 'Mango')
```

---

## 5. Difference Between List and Tuple

List এবং Tuple দেখতে প্রায় একই রকম হলেও এদের মধ্যে কিছু গুরুত্বপূর্ণ পার্থক্য রয়েছে।

| Feature | List | Tuple |
|---|---|---|
| Symbol | `[]` | `()` |
| Ordered | Yes | Yes |
| Mutable | Yes | No |
| Duplicate Values | Yes | Yes |
| Indexing | Supported | Supported |
| Slicing | Supported | Supported |
| Modification | Allowed | Not Allowed |

**Example:**

```python
# List
fruits_list = ["Apple", "Banana", "Mango"]

# Tuple
fruits_tuple = ("Apple", "Banana", "Mango")

print(fruits_list)
print(fruits_tuple)
```

**Output:**

```text
['Apple', 'Banana', 'Mango']
('Apple', 'Banana', 'Mango')
```

---

## 6. Simple Real-Life Examples

| Tuple Example | Use |
|---|---|
| `(10, 20)` | Coordinates |
| `("Red", "Green", "Blue")` | RGB color names |
| `("Monday", "Tuesday")` | Days of the week |
| `(23.8103, 90.4125)` | Location coordinates |

এ ধরনের data সাধারণত একটি নির্দিষ্ট collection হিসেবে সংরক্ষণ করা যায়।

---

## 7. Important Points to Remember

1. Tuple হলো Python-এর একটি Built-in Data Structure।
2. Tuple তৈরি করতে সাধারণত `()` ব্যবহার করা হয়।
3. Tuple Ordered।
4. Tuple Immutable।
5. Tuple-এ Duplicate Values রাখা যায়।
6. Tuple বিভিন্ন Data Type support করে।
7. Tuple Indexing এবং Slicing support করে।
8. Tuple-এর elements সরাসরি পরিবর্তন করা যায় না।
9. Tuple List-এর মতো একাধিক value সংরক্ষণ করতে পারে।
10. Tuple-এর elements access করার জন্য Index ব্যবহার করা যায়।

---

## 8. Common Beginner Mistakes

### Mistake 1: Using Square Brackets for a Tuple

```python
numbers = [10, 20, 30]

print(numbers)
```

**Output:**

```text
[10, 20, 30]
```

এটি Tuple নয়, এটি একটি List।

Tuple তৈরি করতে Parentheses ব্যবহার করতে হয়।

```python
numbers = (10, 20, 30)

print(numbers)
```

**Output:**

```text
(10, 20, 30)
```

### Mistake 2: Trying to Modify a Tuple

```python
numbers = (10, 20, 30)

numbers[1] = 100
```

**Output:**

```text
TypeError
```

Tuple Immutable হওয়ায় এর elements সরাসরি পরিবর্তন করা যায় না।

### Mistake 3: Forgetting the Comma in a Single-Element Tuple

```python
numbers = (10)

print(type(numbers))
```

**Output:**

```text
<class 'int'>
```

এটি Tuple নয়, কারণ একটি value-এর Tuple তৈরি করতে comma ব্যবহার করতে হয়।

**Correct Example:**

```python
numbers = (10,)

print(type(numbers))
```

**Output:**

```text
<class 'tuple'>
```

---

## 9. Practice Exercises

### Exercise 1

তিনটি fruit-এর নাম দিয়ে একটি Tuple তৈরি করো।

**Solution:**

```python
fruits = ("Apple", "Banana", "Mango")

print(fruits)
```

**Output:**

```text
('Apple', 'Banana', 'Mango')
```

### Exercise 2

নিচের Tuple-এ Duplicate Value রয়েছে কি না দেখো।

```python
numbers = (10, 20, 10, 30)

print(numbers)
```

**Solution:**

```text
(10, 20, 10, 30)
```

হ্যাঁ, Tuple-এ Duplicate Value রাখা যায়।

### Exercise 3

নিচের Tuple-এর প্রথম element access করো।

**Solution:**

```python
colors = ("Red", "Green", "Blue")

print(colors[0])
```

**Output:**

```text
Red
```

### Exercise 4

একটি Single-element Tuple তৈরি করো।

**Solution:**

```python
number = (100,)

print(type(number))
```

**Output:**

```text
<class 'tuple'>
```

### Exercise 5

নিচের code-এর output কী হবে?

```python
numbers = (10, 20, 30)

print(numbers[1])
```

**Solution:**

```text
20
```

---

## 10. Chapter Summary

এই topic-এ আমরা Python Tuple-এর basic ধারণা শিখেছি।

- Tuple হলো একটি Built-in Data Structure।
- Tuple তৈরি করতে Parentheses `()` ব্যবহার করা হয়।
- Tuple Ordered এবং Immutable।
- Tuple-এ Duplicate Values রাখা যায়।
- Tuple বিভিন্ন Data Type support করে।
- Tuple Indexing এবং Slicing support করে।
- List-এর মতো Tuple-এও একাধিক value সংরক্ষণ করা যায়।

---

## 11. Self-Assessment Checklist

নিজে যাচাই করো:

- [ ] Tuple কী তা বুঝতে পেরেছি।
- [ ] Tuple কেন ব্যবহার করা হয় তা বুঝতে পেরেছি।
- [ ] Tuple-এর basic syntax জানি।
- [ ] Tuple Ordered বিষয়টি বুঝতে পেরেছি।
- [ ] Tuple Immutable বিষয়টি বুঝতে পেরেছি।
- [ ] Tuple-এ Duplicate Values রাখতে পারি।
- [ ] Tuple-এর মধ্যে Different Data Types রাখতে পারি।
- [ ] List এবং Tuple-এর পার্থক্য বুঝতে পেরেছি।
- [ ] Single-element Tuple তৈরি করতে পারি।

---

## 12. Next Topic

**31. Creating Tuples in Python**

পরবর্তী topic-এ আমরা Python-এ বিভিন্নভাবে Tuple তৈরি করা, Empty Tuple, Single-element Tuple এবং বিভিন্ন Data Type ব্যবহার করে Tuple তৈরি করা শিখব।