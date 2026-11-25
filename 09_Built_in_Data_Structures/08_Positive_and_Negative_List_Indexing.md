# 08. Modifying List Elements Using Indexing in Python

## 1. Introduction

Python List হলো একটি **Mutable Data Structure**। এর মানে হলো, List তৈরি করার পরেও এর elements পরিবর্তন করা যায়।

Indexing ব্যবহার করে আমরা List-এর নির্দিষ্ট কোনো element-এর value পরিবর্তন করতে পারি।

উদাহরণ:

```python
fruits = ["Apple", "Banana", "Mango"]

fruits[1] = "Orange"

print(fruits)
```

**Output:**

```text
['Apple', 'Orange', 'Mango']
```

এখানে:

- `fruits[1]` দিয়ে দ্বিতীয় element নির্বাচন করা হয়েছে।
- `"Orange"` দিয়ে আগের `"Banana"` পরিবর্তন করা হয়েছে।

অর্থাৎ, Indexing ব্যবহার করে List-এর নির্দিষ্ট element update করা যায়।

## 2. Basic Syntax

List-এর কোনো element পরিবর্তন করার Syntax:

```python
list_name[index] = new_value
```

এখানে:

- `list_name` → যে List পরিবর্তন করতে চাই।
- `index` → যে element পরিবর্তন করতে চাই তার index number।
- `new_value` → নতুন value।

উদাহরণ:

```python
numbers = [10, 20, 30, 40]

numbers[2] = 100

print(numbers)
```

**Output:**

```text
[10, 20, 100, 40]
```

এখানে index `2`-এর value `30` পরিবর্তন হয়ে `100` হয়েছে।

## 3. Modifying the First Element

List-এর প্রথম element পরিবর্তন করতে index `0` ব্যবহার করতে হয়।

উদাহরণ:

```python
students = ["Rahim", "Karim", "Hasan"]

students[0] = "Masum"

print(students)
```

**Output:**

```text
['Masum', 'Karim', 'Hasan']
```

এখানে প্রথম element `"Rahim"` পরিবর্তন হয়ে `"Masum"` হয়েছে।

## 4. Modifying the Last Element

List-এর শেষ element পরিবর্তন করতে negative index `-1` ব্যবহার করা যায়।

উদাহরণ:

```python
colors = ["Red", "Green", "Blue"]

colors[-1] = "Yellow"

print(colors)
```

**Output:**

```text
['Red', 'Green', 'Yellow']
```

এখানে `colors[-1]` দিয়ে শেষ element নির্বাচন করা হয়েছে।

এর value `"Blue"` থেকে `"Yellow"` করা হয়েছে।

## 5. Modifying Multiple Elements

আমরা চাইলে একই List-এর একাধিক element আলাদাভাবে পরিবর্তন করতে পারি।

উদাহরণ:

```python
numbers = [10, 20, 30, 40, 50]

numbers[0] = 100
numbers[2] = 300
numbers[4] = 500

print(numbers)
```

**Output:**

```text
[100, 20, 300, 40, 500]
```

এখানে তিনটি element পরিবর্তন করা হয়েছে:

- Index `0`: `10` → `100`
- Index `2`: `30` → `300`
- Index `4`: `50` → `500`

## 6. Modifying Elements Using Variables

আমরা চাইলে variable ব্যবহার করেও List-এর element পরিবর্তন করতে পারি।

উদাহরণ:

```python
fruits = ["Apple", "Banana", "Mango"]

index = 1
new_value = "Orange"

fruits[index] = new_value

print(fruits)
```

**Output:**

```text
['Apple', 'Orange', 'Mango']
```

এখানে:

- `index = 1` দিয়ে দ্বিতীয় element নির্বাচন করা হয়েছে।
- `new_value = "Orange"` দিয়ে নতুন value রাখা হয়েছে।
- `fruits[index] = new_value` দিয়ে element পরিবর্তন করা হয়েছে।

## 7. Changing the Data Type of a List Element

Python List-এ বিভিন্ন data type রাখা যায়।

তাই একটি element পরিবর্তন করার সময় নতুন data type-এর value-ও assign করা যায়।

উদাহরণ:

```python
student = ["Masum", 23, 3.50]

student[1] = "Twenty Three"

print(student)
```

**Output:**

```text
['Masum', 'Twenty Three', 3.5]
```

এখানে আগে index `1`-এ Integer value `23` ছিল।

পরে সেটি String value `"Twenty Three"` দিয়ে পরিবর্তন করা হয়েছে।

## 8. Modifying Elements Using Negative Indexing

Negative Indexing ব্যবহার করেও List-এর element পরিবর্তন করা যায়।

উদাহরণ:

```python
numbers = [10, 20, 30, 40, 50]

numbers[-1] = 100
numbers[-3] = 300

print(numbers)
```

**Output:**

```text
[10, 20, 300, 40, 100]
```

এখানে:

- `numbers[-1]` → শেষ element `50` পরিবর্তন করে `100` করা হয়েছে।
- `numbers[-3]` → শেষ থেকে তৃতীয় element `30` পরিবর্তন করে `300` করা হয়েছে।

## 9. Difference Between Accessing and Modifying List Elements

List Indexing ব্যবহার করে আমরা element access এবং modify—দুই কাজই করতে পারি।

| Accessing | Modifying |
|---|---|
| Element-এর value দেখা হয়। | Element-এর value পরিবর্তন করা হয়। |
| `numbers[0]` | `numbers[0] = 100` |
| Original List পরিবর্তন হয় না। | Original List পরিবর্তন হয়। |

উদাহরণ:

```python
numbers = [10, 20, 30]

# Accessing
print(numbers[0])

# Modifying
numbers[0] = 100

print(numbers)
```

**Output:**

```text
10
[100, 20, 30]
```

## 10. IndexError While Modifying List Elements

List-এর valid index-এর বাইরে কোনো index ব্যবহার করে element পরিবর্তন করতে গেলে `IndexError` হয়।

উদাহরণ:

```python
numbers = [10, 20, 30]

numbers[5] = 100
```

**Output:**

```text
IndexError: list assignment index out of range
```

কারণ List-এ মাত্র 3টি element রয়েছে।

Valid index হলো `0`, `1` এবং `2`।

তাই index `5` ব্যবহার করে element পরিবর্তন করা সম্ভব নয়।

**মনে রাখবে:** Indexing দিয়ে কোনো নতুন position-এ সরাসরি element যোগ করা যায় না। নতুন element যোগ করার জন্য `append()` বা `insert()` ব্যবহার করা হয়। এগুলো আমরা পরবর্তী topics-এ শিখব।

## 11. Modifying Elements in an Empty List

Empty List-এর মধ্যে কোনো element থাকে না।

তাই সরাসরি index ব্যবহার করে এর element পরিবর্তন করা যায় না।

উদাহরণ:

```python
numbers = []

numbers[0] = 10

print(numbers)
```

**Output:**

```text
IndexError: list assignment index out of range
```

কারণ Empty List-এর কোনো valid index নেই।

প্রথমে element যোগ করতে হবে, তারপর সেটি পরিবর্তন করা যাবে।

## 12. Important Rules

1. Python List হলো Mutable।
2. Indexing ব্যবহার করে নির্দিষ্ট element পরিবর্তন করা যায়।
3. প্রথম element পরিবর্তন করতে index `0` ব্যবহার করতে হয়।
4. শেষ element পরিবর্তন করতে index `-1` ব্যবহার করা যায়।
5. Positive এবং Negative Indexing—দুইভাবেই element পরিবর্তন করা যায়।
6. নতুন value-এর data type আগের value-এর data type-এর মতো হওয়া বাধ্যতামূলক নয়।
7. Invalid index ব্যবহার করলে `IndexError` হয়।
8. Empty List-এর কোনো element সরাসরি modify করা যায় না।
9. Indexing দিয়ে নতুন position তৈরি করে element যোগ করা যায় না।

## 13. Common Mistakes

### Mistake 1: Using an Invalid Index

ভুল:

```python
numbers = [10, 20, 30]

numbers[3] = 40
```

এখানে index `3` নেই। তাই `IndexError` হবে।

**Correct:**

```python
numbers = [10, 20, 30]

numbers[2] = 40

print(numbers)
```

**Output:**

```text
[10, 20, 40]
```

### Mistake 2: Using Double Equal Sign

ভুল:

```python
numbers = [10, 20, 30]

numbers[0] == 100
```

এখানে `==` ব্যবহার করা হয়েছে, যা দুটি value সমান কি না তা check করে।

কিন্তু element পরিবর্তন করতে assignment operator `=` ব্যবহার করতে হয়।

**Correct:**

```python
numbers[0] = 100

print(numbers)
```

**Output:**

```text
[100, 20, 30]
```

### Mistake 3: Modifying an Empty List

ভুল:

```python
numbers = []

numbers[0] = 50
```

Empty List-এ কোনো element নেই। তাই সরাসরি index দিয়ে modify করা যাবে না।

**Correct:**

```python
numbers = []

numbers.append(50)

numbers[0] = 100

print(numbers)
```

**Output:**

```text
[100]
```

## 14. Practice Exercises

### Exercise 1: Predict the Output

নিচের code-এর output কী হবে?

```python
numbers = [10, 20, 30, 40]

numbers[1] = 100
numbers[-1] = 400

print(numbers)
```

**Solution:**

```text
[10, 100, 30, 400]
```

### Exercise 2: Change the First and Last Elements

একটি List-এর প্রথম element `"Python"` এবং শেষ element `"Programming"` দিয়ে পরিবর্তন করো।

**Solution:**

```python
subjects = ["Java", "C++", "HTML", "CSS"]

subjects[0] = "Python"
subjects[-1] = "Programming"

print(subjects)
```

**Output:**

```text
['Python', 'C++', 'HTML', 'Programming']
```

### Exercise 3: Modify an Integer Value

নিচের List-এর দ্বিতীয় element `200` দিয়ে পরিবর্তন করো।

**Solution:**

```python
numbers = [100, 150, 250, 300]

numbers[1] = 200

print(numbers)
```

**Output:**

```text
[100, 200, 250, 300]
```

### Exercise 4: Modify Using a Variable

Variable ব্যবহার করে List-এর তৃতীয় element `"Python"` দিয়ে পরিবর্তন করো।

**Solution:**

```python
languages = ["Java", "C++", "C"]

index = 2
new_value = "Python"

languages[index] = new_value

print(languages)
```

**Output:**

```text
['Java', 'C++', 'Python']
```

## 15. Chapter Summary

এই topic-এ আমরা শিখেছি:

- List-এর element modify করা।
- Indexing ব্যবহার করে value পরিবর্তন করা।
- First এবং Last element পরিবর্তন করা।
- Multiple elements পরিবর্তন করা।
- Variable ব্যবহার করে element modify করা।
- Different data type-এর value assign করা।
- Negative Indexing ব্যবহার করে element পরিবর্তন করা।
- Invalid index এবং Empty List-এর error।

## 16. Self-Assessment Checklist

- [ ] List কেন Mutable বুঝি।
- [ ] Indexing দিয়ে element পরিবর্তন করতে পারি।
- [ ] First এবং Last element modify করতে পারি।
- [ ] Multiple elements পরিবর্তন করতে পারি।
- [ ] Negative Indexing দিয়ে element পরিবর্তন করতে পারি।
- [ ] Variable ব্যবহার করে element modify করতে পারি।
- [ ] Accessing এবং Modifying-এর পার্থক্য বুঝি।
- [ ] IndexError-এর কারণ বুঝতে পারি।

## 17. Next Topic

**09. Introduction to List Slicing in Python**

পরবর্তী topic-এ আমরা শিখব কীভাবে List Slicing ব্যবহার করে List-এর নির্দিষ্ট অংশ বা একাধিক element একসাথে access করা যায়।