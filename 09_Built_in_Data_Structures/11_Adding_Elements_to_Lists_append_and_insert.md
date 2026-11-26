# 11. Adding Elements to Lists Using append() and insert() in Python

## 1. Introduction

Python List হলো একটি Mutable Data Structure। তাই List তৈরি করার পরেও এতে নতুন elements যোগ করা যায়।

Python-এ List-এর মধ্যে নতুন elements যোগ করার জন্য দুটি গুরুত্বপূর্ণ method হলো:

1. `append()`
2. `insert()`

**append():** List-এর একদম শেষে নতুন element যোগ করে।

**insert():** List-এর নির্দিষ্ট position বা index-এ নতুন element যোগ করে।

উদাহরণ:

```python
# Using append()
fruits = ["Apple", "Banana"]

fruits.append("Mango")

print(fruits)

# Using insert()
fruits.insert(1, "Orange")

print(fruits)
```

Output:

```text
['Apple', 'Banana', 'Mango']
['Apple', 'Orange', 'Banana', 'Mango']
```

এখানে:

- `append("Mango")` List-এর শেষে Mango যোগ করেছে।
- `insert(1, "Orange")` index 1-এ Orange যোগ করেছে।

## 2. Adding Elements Using append()

`append()` হলো Python List-এর একটি built-in method। এটি List-এর শেষে একটি নতুন element যোগ করে।

Basic Syntax:

```python
list_name.append(element)
```

এখানে:

- `list_name` → যে List-এ element যোগ করতে চাই।
- `element` → যে নতুন value যোগ করতে চাই।

উদাহরণ:

```python
numbers = [10, 20, 30]

numbers.append(40)

print(numbers)
```

Output:

```text
[10, 20, 30, 40]
```

এখানে `40` List-এর শেষে যোগ হয়েছে।

## 3. Adding a String Using append()

`append()` ব্যবহার করে List-এর মধ্যে String যোগ করা যায়।

উদাহরণ:

```python
fruits = ["Apple", "Banana"]

fruits.append("Mango")

print(fruits)
```

Output:

```text
['Apple', 'Banana', 'Mango']
```

এখানে `"Mango"` List-এর শেষে যোগ হয়েছে।

## 4. Adding Different Data Types Using append()

Python List-এ বিভিন্ন Data Type-এর elements রাখা যায়।

তাই `append()` ব্যবহার করে Integer, Float, String এবং Boolean value যোগ করা যায়।

উদাহরণ:

```python
data = [10, "Python", 3.5]

data.append(True)

print(data)
```

Output:

```text
[10, 'Python', 3.5, True]
```

এখানে Boolean value `True` List-এর শেষে যোগ হয়েছে।

## 5. Adding Elements to an Empty List Using append()

Empty List-এর মধ্যে নতুন element যোগ করার জন্যও `append()` ব্যবহার করা যায়।

উদাহরণ:

```python
numbers = []

numbers.append(10)
numbers.append(20)
numbers.append(30)

print(numbers)
```

Output:

```text
[10, 20, 30]
```

এখানে:

- প্রথমে একটি Empty List তৈরি হয়েছে।
- প্রথম `append()` দিয়ে 10 যোগ হয়েছে।
- দ্বিতীয় `append()` দিয়ে 20 যোগ হয়েছে।
- তৃতীয় `append()` দিয়ে 30 যোগ হয়েছে।

## 6. Adding Multiple Elements Using append()

একটি গুরুত্বপূর্ণ বিষয় হলো, `append()` প্রতিবার একটি মাত্র object যোগ করে।

আমরা চাইলে একাধিকবার `append()` ব্যবহার করে একাধিক element যোগ করতে পারি।

উদাহরণ:

```python
numbers = [10, 20]

numbers.append(30)
numbers.append(40)
numbers.append(50)

print(numbers)
```

Output:

```text
[10, 20, 30, 40, 50]
```

এখানে তিনবার `append()` ব্যবহার করে তিনটি নতুন element যোগ করা হয়েছে।

## 7. Adding a List Using append()

`append()` দিয়ে একটি সম্পূর্ণ List যোগ করলে সেটি আলাদা একটি element হিসেবে যুক্ত হয়।

উদাহরণ:

```python
numbers = [10, 20, 30]

numbers.append([40, 50])

print(numbers)
```

Output:

```text
[10, 20, 30, [40, 50]]
```

এখানে `[40, 50]` একটি সম্পূর্ণ List হিসেবে যুক্ত হয়েছে।

অর্থাৎ, এর দুটি element আলাদাভাবে যোগ হয়নি।

এ কারণে List-এর মধ্যে Nested List তৈরি হয়েছে।

## 8. Adding Elements Using insert()

`insert()` হলো Python List-এর একটি built-in method। এটি List-এর নির্দিষ্ট index বা position-এ নতুন element যোগ করে।

Basic Syntax:

```python
list_name.insert(index, element)
```

এখানে:

- `list_name` → যে List-এ element যোগ করতে চাই।
- `index` → যে position-এ element যোগ করতে চাই।
- `element` → যে নতুন value যোগ করতে চাই।

উদাহরণ:

```python
numbers = [10, 20, 40, 50]

numbers.insert(2, 30)

print(numbers)
```

Output:

```text
[10, 20, 30, 40, 50]
```

এখানে:

- `insert(2, 30)` ব্যবহার করা হয়েছে।
- Index 2-তে 30 যোগ হয়েছে।
- আগের elements ডানদিকে সরে গেছে।

## 9. Inserting an Element at the Beginning

List-এর শুরুতে নতুন element যোগ করতে `insert()`-এর index হিসেবে 0 ব্যবহার করতে হয়।

উদাহরণ:

```python
fruits = ["Banana", "Mango", "Orange"]

fruits.insert(0, "Apple")

print(fruits)
```

Output:

```text
['Apple', 'Banana', 'Mango', 'Orange']
```

এখানে `"Apple"` List-এর প্রথম position-এ যোগ হয়েছে।

## 10. Inserting an Element in the Middle

List-এর মাঝখানে নতুন element যোগ করতে নির্দিষ্ট index ব্যবহার করা যায়।

উদাহরণ:

```python
numbers = [10, 20, 40, 50]

numbers.insert(2, 30)

print(numbers)
```

Output:

```text
[10, 20, 30, 40, 50]
```

এখানে index 2-তে `30` যোগ হয়েছে।

## 11. Inserting an Element at the End

`insert()` ব্যবহার করেও List-এর শেষে নতুন element যোগ করা যায়।

উদাহরণ:

```python
numbers = [10, 20, 30]

numbers.insert(3, 40)

print(numbers)
```

Output:

```text
[10, 20, 30, 40]
```

এখানে:

- List-এর length ছিল 3।
- শেষ position-এর পর index 3 ব্যবহার করা হয়েছে।
- তাই 40 List-এর শেষে যোগ হয়েছে।

তবে List-এর শেষে element যোগ করার জন্য `append()` বেশি সহজ এবং উপযুক্ত।

## 12. Using Negative Indexing with insert()

`insert()` method-এ Negative Indexing ব্যবহার করেও element যোগ করা যায়।

উদাহরণ:

```python
numbers = [10, 20, 30, 40]

numbers.insert(-1, 100)

print(numbers)
```

Output:

```text
[10, 20, 30, 100, 40]
```

এখানে:

- `-1` হলো শেষ element-এর position নির্দেশ করে।
- নতুন element `100` শেষ element `40`-এর আগে যোগ হয়েছে।

মনে রাখবে: `insert(-1, value)` ব্যবহার করলে element একদম শেষে নয়, শেষ element-এর আগে যোগ হয়।

## 13. Inserting Elements Using Variables

Variable ব্যবহার করেও `append()` এবং `insert()` method-এর মাধ্যমে নতুন element যোগ করা যায়।

উদাহরণ:

```python
fruits = ["Apple", "Banana"]

new_fruit = "Mango"
position = 1

fruits.insert(position, new_fruit)

print(fruits)
```

Output:

```text
['Apple', 'Mango', 'Banana']
```

এখানে:

- `new_fruit`-এ নতুন value রাখা হয়েছে।
- `position`-এ index রাখা হয়েছে।
- Variable ব্যবহার করে List-এ element যোগ হয়েছে।

## 14. Adding Elements to a List Inside a Loop

Loop ব্যবহার করে একাধিক element একটি List-এ যোগ করা যায়।

উদাহরণ:

```python
numbers = []

for i in range(1, 6):
    numbers.append(i)

print(numbers)
```

Output:

```text
[1, 2, 3, 4, 5]
```

এখানে:

- একটি Empty List তৈরি হয়েছে।
- Loop পাঁচবার চলেছে।
- প্রতিবার `append()` দিয়ে একটি করে number যোগ হয়েছে।

## 15. Difference Between append() and insert()

| append() | insert() |
|---|---|
| List-এর শেষে element যোগ করে। | নির্দিষ্ট position-এ element যোগ করে। |
| একটি argument নেয়। | দুটি argument নেয়। |
| `numbers.append(40)` | `numbers.insert(1, 40)` |
| Position নির্ধারণ করতে হয় না। | Position নির্ধারণ করতে হয়। |

উদাহরণ:

```python
numbers1 = [10, 20, 30]
numbers2 = [10, 20, 30]

numbers1.append(40)
numbers2.insert(1, 40)

print(numbers1)
print(numbers2)
```

Output:

```text
[10, 20, 30, 40]
[10, 40, 20, 30]
```

## 16. Important Rules

- `append()` List-এর শেষে একটি element যোগ করে।
- `insert()` নির্দিষ্ট position-এ একটি element যোগ করে।
- `append()` একটি argument গ্রহণ করে।
- `insert()` দুটি argument গ্রহণ করে।
- `append()` দিয়ে একটি List যোগ করলে সেটি একটি Nested List তৈরি করে।
- Empty List-এর মধ্যেও `append()` এবং `insert()` ব্যবহার করা যায়।
- `insert(0, value)` List-এর শুরুতে element যোগ করে।
- `insert(-1, value)` শেষ element-এর আগে নতুন element যোগ করে।
- `append()` এবং `insert()` Original List পরিবর্তন করে।
- দুটি method-ই `None` return করে।
- `append()` এবং `insert()` ব্যবহার করে List-এর length বাড়ানো যায়।
- List-এর শেষে element যোগ করার জন্য সাধারণত `append()` ব্যবহার করা হয়।

## 17. Common Mistakes

### Mistake 1: Assigning append() to a Variable

ভুল:

```python
numbers = [10, 20, 30]

result = numbers.append(40)

print(result)
```

Output:

```text
None
```

কারণ `append()` নতুন List return করে না। এটি Original List পরিবর্তন করে এবং `None` return করে।

Correct:

```python
numbers = [10, 20, 30]

numbers.append(40)

print(numbers)
```

Output:

```text
[10, 20, 30, 40]
```

### Mistake 2: Confusing append() with insert()

ভুল ধারণা:

```python
numbers = [10, 20, 30]

numbers.append(1, 40)
```

Output:

```text
TypeError: list.append() takes exactly one argument (2 given)
```

কারণ `append()` দুটি argument গ্রহণ করে না।

Correct:

```python
numbers = [10, 20, 30]

numbers.insert(1, 40)

print(numbers)
```

Output:

```text
[10, 40, 20, 30]
```

### Mistake 3: Forgetting the Difference Between append() and Adding Multiple Elements

উদাহরণ:

```python
numbers = [10, 20]

numbers.append([30, 40])

print(numbers)
```

Output:

```text
[10, 20, [30, 40]]
```

এখানে `[30, 40]` একটি Nested List হিসেবে যোগ হয়েছে।

যদি দুটি element আলাদাভাবে যোগ করতে চাও, তাহলে:

```python
numbers = [10, 20]

numbers.append(30)
numbers.append(40)

print(numbers)
```

Output:

```text
[10, 20, 30, 40]
```

### Mistake 4: Using the Wrong Position in insert()

উদাহরণ:

```python
numbers = [10, 20, 30, 40]

numbers.insert(2, 100)

print(numbers)
```

Output:

```text
[10, 20, 100, 30, 40]
```

অনেকে মনে করে `100` index 2-এর পুরোনো value পরিবর্তন করবে।

কিন্তু `insert()` পুরোনো value পরিবর্তন করে না। এটি নতুন element যোগ করে এবং পরবর্তী elements-গুলো ডানদিকে সরিয়ে দেয়।

## 18. Practice Exercises

### Exercise 1: Predict the Output

নিচের code-এর output কী হবে?

```python
numbers = [10, 20, 30]

numbers.append(40)

print(numbers)
```

Solution:

```text
[10, 20, 30, 40]
```

### Exercise 2: Add an Element at the Beginning

একটি List-এর শুরুতে `"Python"` যোগ করো।

Solution:

```python
languages = ["Java", "C++", "JavaScript"]

languages.insert(0, "Python")

print(languages)
```

Output:

```text
['Python', 'Java', 'C++', 'JavaScript']
```

### Exercise 3: Add an Element in the Middle

নিচের List-এর index 2-তে `300` যোগ করো।

Solution:

```python
numbers = [100, 200, 400, 500]

numbers.insert(2, 300)

print(numbers)
```

Output:

```text
[100, 200, 300, 400, 500]
```

### Exercise 4: Add Elements Using a Loop

Loop ব্যবহার করে 1 থেকে 5 পর্যন্ত numbers একটি Empty List-এ যোগ করো।

Solution:

```python
numbers = []

for i in range(1, 6):
    numbers.append(i)

print(numbers)
```

Output:

```text
[1, 2, 3, 4, 5]
```

### Exercise 5: Use Both append() and insert()

নিচের List-এর শেষে `"PHP"` যোগ করো এবং index 1-এ `"Python"` যোগ করো।

Solution:

```python
languages = ["C", "C++", "Java"]

languages.append("PHP")
languages.insert(1, "Python")

print(languages)
```

Output:

```text
['C', 'Python', 'C++', 'Java', 'PHP']
```

## 19. Chapter Summary

এই topic-এ আমরা শিখেছি:

- `append()` method কী।
- `insert()` method কী।
- List-এর শেষে নতুন element যোগ করা।
- List-এর শুরুতে element যোগ করা।
- List-এর মাঝখানে element যোগ করা।
- Different Data Types-এর elements যোগ করা।
- Empty List-এ element যোগ করা।
- List-এর মধ্যে Nested List তৈরি করা।
- Variable ব্যবহার করে element যোগ করা।
- Loop ব্যবহার করে একাধিক element যোগ করা।
- `append()` এবং `insert()`-এর পার্থক্য।
- Common Errors এবং তাদের সমাধান।

## 20. Self-Assessment Checklist

- [ ] `append()` method-এর কাজ বুঝি।
- [ ] `insert()` method-এর কাজ বুঝি।
- [ ] `append()` দিয়ে List-এর শেষে element যোগ করতে পারি।
- [ ] `insert()` দিয়ে নির্দিষ্ট position-এ element যোগ করতে পারি।
- [ ] Empty List-এ elements যোগ করতে পারি।
- [ ] Different Data Types-এর elements যোগ করতে পারি।
- [ ] Nested List তৈরি করতে পারি।
- [ ] Loop ব্যবহার করে List-এ elements যোগ করতে পারি।
- [ ] `append()` এবং `insert()`-এর পার্থক্য বুঝি।
- [ ] এই methods-এর Common Errors বুঝতে পারি।

## 21. Next Topic

**12. Extending Lists with extend() in Python**

পরবর্তী topic-এ আমরা শিখব কীভাবে `extend()` method ব্যবহার করে একটি List-এর মধ্যে অন্য List বা Iterable-এর একাধিক elements আলাদাভাবে যোগ করতে হয়।