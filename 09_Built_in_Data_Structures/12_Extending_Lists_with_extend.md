# 12. Extending Lists with extend() in Python

## 1. Introduction

Python List-এর মধ্যে অন্য কোনো List বা Iterable-এর একাধিক elements যোগ করার জন্য `extend()` method ব্যবহার করা হয়।

`extend()` হলো Python List-এর একটি built-in method। এটি একটি Iterable-এর প্রতিটি element আলাদাভাবে Original List-এর শেষে যোগ করে।

উদাহরণ:

```python
numbers = [10, 20, 30]

numbers.extend([40, 50, 60])

print(numbers)
```

Output:

```text
[10, 20, 30, 40, 50, 60]
```

এখানে:

- প্রথমে `numbers` নামে একটি List তৈরি করা হয়েছে।
- `extend()` দিয়ে `[40, 50, 60]`-এর elements যোগ করা হয়েছে।
- প্রতিটি element আলাদাভাবে Original List-এর শেষে যুক্ত হয়েছে।

অর্থাৎ, `extend()` ব্যবহার করে একটি List-এর মধ্যে অন্য Iterable-এর elements যোগ করা যায়।

## 2. Basic Syntax of extend()

`extend()` method-এর Basic Syntax:

```python
list_name.extend(iterable)
```

এখানে:

- `list_name` → যে List-এর মধ্যে elements যোগ করতে চাই।
- `iterable` → যে Iterable-এর elements যোগ করতে চাই।

Iterable-এর উদাহরণ:

- List
- Tuple
- Set
- String
- Range

উদাহরণ:

```python
numbers = [10, 20]

numbers.extend([30, 40])

print(numbers)
```

Output:

```text
[10, 20, 30, 40]
```

এখানে `[30, 40]`-এর দুটি element আলাদাভাবে `numbers` List-এ যোগ হয়েছে।

## 3. Extending a List with Another List

একটি List-এর মধ্যে অন্য List-এর elements যোগ করার জন্য `extend()` ব্যবহার করা হয়।

উদাহরণ:

```python
fruits = ["Apple", "Banana"]

more_fruits = ["Mango", "Orange"]

fruits.extend(more_fruits)

print(fruits)
```

Output:

```text
['Apple', 'Banana', 'Mango', 'Orange']
```

এখানে:

- `fruits` হলো Original List।
- `more_fruits` হলো অন্য একটি List।
- `extend()` ব্যবহার করে `more_fruits`-এর elements Original List-এ যোগ করা হয়েছে।

মনে রাখবে: `extend()` Original List পরিবর্তন করে।

## 4. Extending an Empty List

Empty List-এর মধ্যেও `extend()` ব্যবহার করে একাধিক element যোগ করা যায়।

উদাহরণ:

```python
numbers = []

numbers.extend([10, 20, 30, 40])

print(numbers)
```

Output:

```text
[10, 20, 30, 40]
```

এখানে প্রথমে একটি Empty List তৈরি করা হয়েছে। পরে `extend()` ব্যবহার করে চারটি element যোগ করা হয়েছে।

## 5. Extending a List with a Tuple

`extend()` শুধু List-এর সঙ্গে কাজ করে না। এটি Tuple-এর elements-ও List-এর মধ্যে যোগ করতে পারে।

উদাহরণ:

```python
numbers = [10, 20]

more_numbers = (30, 40, 50)

numbers.extend(more_numbers)

print(numbers)
```

Output:

```text
[10, 20, 30, 40, 50]
```

এখানে:

- `more_numbers` একটি Tuple।
- `extend()` Tuple-এর প্রতিটি element আলাদাভাবে Original List-এ যোগ করেছে।

## 6. Extending a List with a Set

Set-এর elements ব্যবহার করেও List extend করা যায়।

উদাহরণ:

```python
numbers = [10, 20]

more_numbers = {30, 40, 50}

numbers.extend(more_numbers)

print(numbers)
```

Possible Output:

```text
[10, 20, 30, 40, 50]
```

এখানে:

- `more_numbers` একটি Set।
- `extend()` Set-এর elements List-এ যোগ করেছে।

**Important:** Set-এর কোনো fixed positional order নেই। তাই Set-এর elements List-এ যোগ হওয়ার নির্দিষ্ট order নিশ্চিত নয়।

## 7. Extending a List with a String

String-ও একটি Iterable। তাই `extend()` ব্যবহার করে String-এর characters আলাদাভাবে List-এ যোগ করা যায়।

উদাহরণ:

```python
letters = ["A", "B"]

letters.extend("CDE")

print(letters)
```

Output:

```text
['A', 'B', 'C', 'D', 'E']
```

এখানে:

- `"CDE"` একটি String।
- Python String-এর প্রতিটি character আলাদাভাবে নিয়েছে।
- তাই `C`, `D` এবং `E` আলাদা elements হিসেবে যোগ হয়েছে।

## 8. Extending a List with range()

`range()` ব্যবহার করেও List extend করা যায়।

উদাহরণ:

```python
numbers = [10, 20]

numbers.extend(range(1, 4))

print(numbers)
```

Output:

```text
[10, 20, 1, 2, 3]
```

এখানে:

- `range(1, 4)` থেকে 1, 2 এবং 3 পাওয়া যায়।
- প্রতিটি number আলাদাভাবে List-এ যোগ হয়েছে।

## 9. Extending a List with Multiple Data Types

Python List-এ বিভিন্ন Data Type-এর elements রাখা যায়। তাই `extend()` ব্যবহার করেও বিভিন্ন Data Type-এর elements যোগ করা সম্ভব।

উদাহরণ:

```python
data = [10, "Python"]

more_data = [3.5, True, "Programming"]

data.extend(more_data)

print(data)
```

Output:

```text
[10, 'Python', 3.5, True, 'Programming']
```

এখানে Integer, String, Float এবং Boolean values একই List-এ সংরক্ষণ করা হয়েছে।

## 10. Difference Between append() and extend()

`append()` এবং `extend()` দুটিই List-এর শেষে elements যোগ করে। কিন্তু এদের কাজের মধ্যে গুরুত্বপূর্ণ পার্থক্য রয়েছে।

| append() | extend() |
|---|---|
| একটি object যোগ করে। | Iterable-এর elements আলাদাভাবে যোগ করে। |
| একটি argument গ্রহণ করে। | একটি iterable argument গ্রহণ করে। |
| List দিলে সম্পূর্ণ List-টি একটি element হয়। | List দিলে এর elements আলাদাভাবে যোগ হয়। |
| Nested List তৈরি করতে পারে। | সাধারণত elements আলাদাভাবে যোগ করে। |

উদাহরণ:

```python
numbers1 = [10, 20]
numbers2 = [10, 20]

numbers1.append([30, 40])
numbers2.extend([30, 40])

print(numbers1)
print(numbers2)
```

Output:

```text
[10, 20, [30, 40]]
[10, 20, 30, 40]
```

এখানে:

- `append()` সম্পূর্ণ `[30, 40]` List-কে একটি element হিসেবে যোগ করেছে।
- `extend()` দুটি element আলাদাভাবে যোগ করেছে।

## 11. extend() Returns None

`extend()` Original List পরিবর্তন করে, কিন্তু এটি নতুন List return করে না।

এটি `None` return করে।

উদাহরণ:

```python
numbers = [10, 20, 30]

result = numbers.extend([40, 50])

print(result)
print(numbers)
```

Output:

```text
None
[10, 20, 30, 40, 50]
```

এখানে:

- `extend()` Original List পরিবর্তন করেছে।
- `result`-এর মধ্যে `None` সংরক্ষিত হয়েছে।
- নতুন List return হয়নি।

## 12. Using extend() Inside a Loop

Loop ব্যবহার করে একাধিক List-এর elements একটি List-এর মধ্যে যোগ করা যায়।

উদাহরণ:

```python
numbers = []

lists = [[10, 20], [30, 40], [50, 60]]

for item in lists:
    numbers.extend(item)

print(numbers)
```

Output:

```text
[10, 20, 30, 40, 50, 60]
```

এখানে:

- `lists`-এর মধ্যে তিনটি List রয়েছে।
- Loop প্রতিটি List access করেছে।
- `extend()` দিয়ে প্রতিটি List-এর elements `numbers`-এ যোগ হয়েছে।

## 13. Extending a List with Itself

একটি List-কে নিজেই নিজের মধ্যে `extend()` করা যায়।

এতে Original List-এর elements আবার শেষে যোগ হয়।

উদাহরণ:

```python
numbers = [10, 20, 30]

numbers.extend(numbers)

print(numbers)
```

Output:

```text
[10, 20, 30, 10, 20, 30]
```

এখানে:

- Original List-এ তিনটি element ছিল।
- একই elements আবার শেষে যোগ হয়েছে।
- তাই List-এ মোট ছয়টি element হয়েছে।

## 14. Extending a List with an Empty List

একটি Empty List দিয়ে অন্য List extend করলে কোনো নতুন element যোগ হয় না।

উদাহরণ:

```python
numbers = [10, 20, 30]

numbers.extend([])

print(numbers)
```

Output:

```text
[10, 20, 30]
```

এখানে Empty List-এর কোনো element নেই। তাই Original List অপরিবর্তিত রয়েছে।

## 15. Difference Between append(), insert() and extend()

| Method | কাজ | Example |
|---|---|---|
| append() | শেষে একটি object যোগ করে। | `numbers.append(40)` |
| insert() | নির্দিষ্ট position-এ একটি object যোগ করে। | `numbers.insert(1, 40)` |
| extend() | Iterable-এর elements শেষে যোগ করে। | `numbers.extend([40, 50])` |

উদাহরণ:

```python
numbers1 = [10, 20]
numbers2 = [10, 20]
numbers3 = [10, 20]

numbers1.append(30)
numbers2.insert(1, 30)
numbers3.extend([30, 40])

print(numbers1)
print(numbers2)
print(numbers3)
```

Output:

```text
[10, 20, 30]
[10, 30, 20]
[10, 20, 30, 40]
```

## 16. Important Rules

- `extend()` একটি List-এর মধ্যে অন্য Iterable-এর elements যোগ করে।
- এর Syntax হলো `list_name.extend(iterable)`।
- `extend()` প্রতিটি element আলাদাভাবে যোগ করে।
- List, Tuple, Set, String এবং Range দিয়ে List extend করা যায়।
- `extend()` Original List পরিবর্তন করে।
- `extend()` নতুন List return করে না।
- `extend()`-এর return value হলো `None`।
- String extend করলে প্রতিটি character আলাদা element হিসেবে যোগ হয়।
- Set extend করলে elements-এর order নিশ্চিত নয়।
- Empty Iterable দিয়ে extend করলে List পরিবর্তন হয় না।
- একটি List-কে নিজেই নিজের মধ্যে extend করা যায়।
- `append()` সম্পূর্ণ object যোগ করে, কিন্তু `extend()` Iterable-এর elements যোগ করে।

## 17. Common Mistakes

### Mistake 1: Assigning extend() to a Variable

ভুল:

```python
numbers = [10, 20]

result = numbers.extend([30, 40])

print(result)
```

Output:

```text
None
```

কারণ `extend()` নতুন List return করে না।

Correct:

```python
numbers = [10, 20]

numbers.extend([30, 40])

print(numbers)
```

Output:

```text
[10, 20, 30, 40]
```

### Mistake 2: Confusing append() with extend()

ভুল ধারণা:

```python
numbers = [10, 20]

numbers.append([30, 40])

print(numbers)
```

Output:

```text
[10, 20, [30, 40]]
```

এখানে দুটি element আলাদাভাবে যোগ হয়নি।

Correct:

```python
numbers = [10, 20]

numbers.extend([30, 40])

print(numbers)
```

Output:

```text
[10, 20, 30, 40]
```

### Mistake 3: Using an Integer with extend()

ভুল:

```python
numbers = [10, 20]

numbers.extend(30)
```

Output:

```text
TypeError: 'int' object is not iterable
```

কারণ Integer একটি Iterable নয়।

Correct:

```python
numbers = [10, 20]

numbers.extend([30])

print(numbers)
```

Output:

```text
[10, 20, 30]
```

### Mistake 4: Expecting a String to Be Added as One Element

উদাহরণ:

```python
letters = ["A", "B"]

letters.extend("Python")

print(letters)
```

Output:

```text
['A', 'B', 'P', 'y', 't', 'h', 'o', 'n']
```

এখানে `"Python"` একটি সম্পূর্ণ String হিসেবে যোগ হয়নি। এর প্রতিটি character আলাদাভাবে যোগ হয়েছে।

যদি সম্পূর্ণ String-কে একটি element হিসেবে যোগ করতে চাও, তাহলে `append()` ব্যবহার করতে হবে।

Correct:

```python
letters = ["A", "B"]

letters.append("Python")

print(letters)
```

Output:

```text
['A', 'B', 'Python']
```

## 18. Practice Exercises

### Exercise 1: Predict the Output

নিচের code-এর output কী হবে?

```python
numbers = [10, 20, 30]

numbers.extend([40, 50])

print(numbers)
```

Solution:

```text
[10, 20, 30, 40, 50]
```

### Exercise 2: Extend a List with Another List

দুটি List-এর elements একটি List-এর মধ্যে যোগ করো।

Solution:

```python
fruits = ["Apple", "Banana"]

more_fruits = ["Mango", "Orange"]

fruits.extend(more_fruits)

print(fruits)
```

Output:

```text
['Apple', 'Banana', 'Mango', 'Orange']
```

### Exercise 3: Extend a List with a Tuple

নিচের Tuple-এর elements একটি List-এ যোগ করো।

Solution:

```python
numbers = [10, 20]

values = (30, 40, 50)

numbers.extend(values)

print(numbers)
```

Output:

```text
[10, 20, 30, 40, 50]
```

### Exercise 4: Extend a List Using range()

`range()` ব্যবহার করে 1 থেকে 5 পর্যন্ত numbers একটি List-এ যোগ করো।

Solution:

```python
numbers = [0]

numbers.extend(range(1, 6))

print(numbers)
```

Output:

```text
[0, 1, 2, 3, 4, 5]
```

### Exercise 5: Difference Between append() and extend()

নিচের code-এর output predict করো।

```python
numbers1 = [10, 20]
numbers2 = [10, 20]

numbers1.append([30, 40])
numbers2.extend([30, 40])

print(numbers1)
print(numbers2)
```

Solution:

```text
[10, 20, [30, 40]]
[10, 20, 30, 40]
```

## 19. Chapter Summary

এই topic-এ আমরা শিখেছি:

- `extend()` method কী।
- `extend()`-এর Basic Syntax।
- অন্য List দিয়ে একটি List extend করা।
- Empty List extend করা।
- Tuple এবং Set দিয়ে List extend করা।
- String দিয়ে List extend করা।
- Range দিয়ে List extend করা।
- Different Data Types-এর elements যোগ করা।
- Loop ব্যবহার করে List extend করা।
- একটি List-কে নিজেই নিজের মধ্যে extend করা।
- `append()`, `insert()` এবং `extend()`-এর পার্থক্য।
- Common Errors এবং তাদের সমাধান।

## 20. Self-Assessment Checklist

- [ ] `extend()` method কী বুঝি।
- [ ] `extend()`-এর Syntax লিখতে পারি।
- [ ] একটি List দিয়ে অন্য List extend করতে পারি।
- [ ] Tuple এবং Set দিয়ে List extend করতে পারি।
- [ ] String এবং Range দিয়ে List extend করতে পারি।
- [ ] Loop ব্যবহার করে List extend করতে পারি।
- [ ] `append()` এবং `extend()`-এর পার্থক্য বুঝি।
- [ ] `insert()` এবং `extend()`-এর পার্থক্য বুঝি।
- [ ] `extend()` কেন `None` return করে বুঝি।
- [ ] Common Errors identify করতে পারি।

## 21. Next Topic

**13. Removing Elements from Lists in Python**

পরবর্তী topic-এ আমরা শিখব কীভাবে Python List থেকে elements remove বা delete করতে হয় এবং বিভিন্ন উপায়ে List-এর elements মুছে ফেলতে হয়।