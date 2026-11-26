# 09. List Slicing Basics in Python

## 1. Introduction

Python List-এর নির্দিষ্ট কোনো অংশ বা একাধিক element একসাথে access করার পদ্ধতিকে **List Slicing** বলা হয়।

Indexing ব্যবহার করে আমরা List-এর একটি নির্দিষ্ট element access করতে পারি। অন্যদিকে, Slicing ব্যবহার করে একসাথে একাধিক element access করা যায়।

উদাহরণ:

```python
fruits = ["Apple", "Banana", "Mango", "Orange", "Grapes"]

print(fruits[1:4])
```

Output:

```text
['Banana', 'Mango', 'Orange']
```

এখানে:

- `fruits[1:4]` দিয়ে index 1 থেকে index 3 পর্যন্ত elements নেওয়া হয়েছে।
- Starting index 1 অন্তর্ভুক্ত হয়েছে।
- Ending index 4 অন্তর্ভুক্ত হয়নি।

অর্থাৎ, List Slicing ব্যবহার করে List-এর নির্দিষ্ট অংশ সহজে access করা যায়।

## 2. Basic Syntax of List Slicing

List Slicing-এর Basic Syntax:

```python
list_name[start:stop]
```

এখানে:

- `list_name` → যে List থেকে elements নিতে চাই।
- `start` → যে index থেকে slicing শুরু হবে।
- `stop` → যে index-এর আগ পর্যন্ত slicing চলবে।

**Important Rule:**

Starting index অন্তর্ভুক্ত হয়, কিন্তু stopping index অন্তর্ভুক্ত হয় না।

উদাহরণ:

```python
numbers = [10, 20, 30, 40, 50, 60]

print(numbers[1:4])
```

Output:

```text
[20, 30, 40]
```

এখানে:

- Start index = 1
- Stop index = 4
- Selected indexes = 1, 2, 3

তাই output-এ `20, 30, 40` এসেছে।

## 3. Slicing from the Beginning

List-এর শুরু থেকে নির্দিষ্ট index-এর আগ পর্যন্ত elements নিতে চাইলে starting index 0 ব্যবহার করা যায়।

উদাহরণ:

```python
numbers = [10, 20, 30, 40, 50]

print(numbers[0:3])
```

Output:

```text
[10, 20, 30]
```

এখানে index 0 থেকে index 2 পর্যন্ত elements নেওয়া হয়েছে।

অর্থাৎ, প্রথম তিনটি element পাওয়া গেছে।

## 4. Slicing from a Specific Index

আমরা চাইলে যেকোনো নির্দিষ্ট index থেকে slicing শুরু করতে পারি।

উদাহরণ:

```python
fruits = ["Apple", "Banana", "Mango", "Orange", "Grapes"]

print(fruits[2:5])
```

Output:

```text
['Mango', 'Orange', 'Grapes']
```

এখানে index 2 থেকে index 4 পর্যন্ত elements নেওয়া হয়েছে।

## 5. Omitting the Start Index

Slicing করার সময় starting index না দিলে Python স্বয়ংক্রিয়ভাবে 0 ধরে নেয়।

উদাহরণ:

```python
numbers = [10, 20, 30, 40, 50]

print(numbers[:3])
```

Output:

```text
[10, 20, 30]
```

এখানে:

- Starting index দেওয়া হয়নি।
- Python default হিসেবে 0 নিয়েছে।
- Stop index 3-এর আগ পর্যন্ত elements নিয়েছে।

অর্থাৎ, `numbers[:3]` এবং `numbers[0:3]` একই কাজ করে।

## 6. Omitting the Stop Index

Slicing করার সময় stopping index না দিলে Python List-এর শেষ পর্যন্ত elements নেয়।

উদাহরণ:

```python
numbers = [10, 20, 30, 40, 50]

print(numbers[2:])
```

Output:

```text
[30, 40, 50]
```

এখানে:

- Starting index = 2
- Stopping index দেওয়া হয়নি।
- তাই index 2 থেকে List-এর শেষ পর্যন্ত elements নেওয়া হয়েছে।

অর্থাৎ, `numbers[2:]` এবং `numbers[2:5]` একই output দেয়।

## 7. Omitting Both Start and Stop Index

Starting এবং stopping index দুটিই না দিলে সম্পূর্ণ List-এর একটি নতুন shallow copy পাওয়া যায়।

উদাহরণ:

```python
numbers = [10, 20, 30, 40, 50]

new_numbers = numbers[:]

print(new_numbers)
```

Output:

```text
[10, 20, 30, 40, 50]
```

এখানে:

- Start index দেওয়া হয়নি।
- Stop index দেওয়া হয়নি।
- তাই সম্পূর্ণ List নেওয়া হয়েছে।

মনে রাখবে: `numbers[:]` দিয়ে নতুন List তৈরি হয়। এটি original List-এর সঙ্গে একই List object নয়।

## 8. List Slicing with Negative Indexing

Negative Indexing ব্যবহার করেও List Slicing করা যায়।

Negative Indexing-এর ক্ষেত্রে শেষ element-এর index হলো `-1`।

উদাহরণ:

```python
numbers = [10, 20, 30, 40, 50]

print(numbers[-4:-1])
```

Output:

```text
[20, 30, 40]
```

এখানে:

- Start index = -4
- Stop index = -1
- Selected elements = 20, 30, 40

কারণ stopping index `-1` অন্তর্ভুক্ত হয় না।

## 9. Selecting the First Few Elements

List থেকে প্রথম কয়েকটি element নেওয়ার জন্য Slicing ব্যবহার করা যায়।

উদাহরণ:

```python
students = ["Masum", "Rahim", "Karim", "Hasan", "Rafi"]

print(students[:3])
```

Output:

```text
['Masum', 'Rahim', 'Karim']
```

এখানে List-এর প্রথম তিনটি student-এর নাম নেওয়া হয়েছে।

## 10. Selecting the Last Few Elements

List-এর শেষের কয়েকটি element নেওয়ার জন্য Negative Indexing ব্যবহার করা যায়।

উদাহরণ:

```python
numbers = [10, 20, 30, 40, 50, 60]

print(numbers[-3:])
```

Output:

```text
[40, 50, 60]
```

এখানে শেষ তিনটি element নেওয়া হয়েছে।

## 11. List Slicing Does Not Modify the Original List

List Slicing সাধারণত original List পরিবর্তন করে না। এটি selected elements দিয়ে একটি নতুন List return করে।

উদাহরণ:

```python
numbers = [10, 20, 30, 40, 50]

result = numbers[1:4]

print("Original List:", numbers)
print("Sliced List:", result)
```

Output:

```text
Original List: [10, 20, 30, 40, 50]
Sliced List: [20, 30, 40]
```

এখানে:

- `numbers` হলো original List।
- `result` হলো slicing-এর মাধ্যমে তৈরি নতুন List।
- Slicing করার কারণে original List পরিবর্তন হয়নি।

## 12. Using Slicing with String and Other Lists

Python-এর List Slicing-এর নিয়ম অন্যান্য sequence-এর ক্ষেত্রেও ব্যবহার করা যায়।

উদাহরণ:

```python
languages = ["Python", "Java", "C++", "JavaScript"]

print(languages[1:3])
```

Output:

```text
['Java', 'C++']
```

এখানে index 1 থেকে index 2 পর্যন্ত elements নেওয়া হয়েছে।

## 13. Understanding Start and Stop Index

List Slicing ভালোভাবে বুঝতে Start এবং Stop index-এর নিয়ম জানা গুরুত্বপূর্ণ।

উদাহরণ:

```python
numbers = [10, 20, 30, 40, 50, 60]

print(numbers[1:5])
```

Output:

```text
[20, 30, 40, 50]
```

Index Table:

| Index | Value |
|---|---|
| 0 | 10 |
| 1 | 20 |
| 2 | 30 |
| 3 | 40 |
| 4 | 50 |
| 5 | 60 |

এখানে:

- Start = 1
- Stop = 5
- Selected indexes = 1, 2, 3, 4

তাই output-এ চারটি element এসেছে।

**মনে রাখবে:** Slicing-এর Stop Index কখনো selected result-এর মধ্যে অন্তর্ভুক্ত হয় না।

## 14. Slicing with Out-of-Range Index

List-এর length-এর চেয়ে বড় stopping index ব্যবহার করলেও সাধারণত Slicing-এ কোনো error হয় না।

উদাহরণ:

```python
numbers = [10, 20, 30, 40, 50]

print(numbers[1:10])
```

Output:

```text
[20, 30, 40, 50]
```

এখানে List-এর শেষ index 4 হলেও stop index 10 দেওয়া হয়েছে।

Python স্বয়ংক্রিয়ভাবে List-এর শেষ পর্যন্ত elements নিয়েছে।

অর্থাৎ, সাধারণ Indexing-এর মতো Slicing-এ out-of-range index ব্যবহার করলে `IndexError` হয় না।

## 15. Slicing an Empty List

Empty List-এর ওপর Slicing ব্যবহার করলেও কোনো error হয় না।

উদাহরণ:

```python
numbers = []

result = numbers[0:3]

print(result)
```

Output:

```text
[]
```

কারণ Empty List-এ কোনো element নেই।

তাই Slicing-এর result-ও Empty List হয়েছে।

## 16. Difference Between Indexing and Slicing

| Indexing | Slicing |
|---|---|
| একটি element access করে। | একাধিক element access করতে পারে। |
| একটি value return করে। | একটি List return করে। |
| `numbers[1]` | `numbers[1:4]` |
| Invalid index-এ IndexError হতে পারে। | Out-of-range slice-এ সাধারণত error হয় না। |

উদাহরণ:

```python
numbers = [10, 20, 30, 40, 50]

# Indexing
print(numbers[1])

# Slicing
print(numbers[1:4])
```

Output:

```text
20
[20, 30, 40]
```

## 17. Important Rules

- List Slicing ব্যবহার করে একাধিক element access করা যায়।
- Slicing-এর Syntax হলো `list_name[start:stop]`।
- Starting index অন্তর্ভুক্ত হয়।
- Stopping index অন্তর্ভুক্ত হয় না।
- Starting index না দিলে default হিসেবে 0 ব্যবহৃত হয়।
- Stopping index না দিলে List-এর শেষ পর্যন্ত elements নেওয়া হয়।
- `list_name[:]` দিয়ে সম্পূর্ণ List slice করা যায়।
- Positive এবং Negative Indexing উভয়ই Slicing-এ ব্যবহার করা যায়।
- Slicing সাধারণত original List পরিবর্তন করে না।
- Slicing একটি নতুন List return করে।
- Out-of-range slicing-এ সাধারণত IndexError হয় না।
- Empty List-এর Slicing result-ও Empty List হয়।

## 18. Common Mistakes

### Mistake 1: Including the Stop Index

ভুল ধারণা:

```python
numbers = [10, 20, 30, 40, 50]

print(numbers[1:3])
```

অনেকে মনে করে output হবে:

```text
[20, 30, 40]
```

কিন্তু সঠিক Output:

```text
[20, 30]
```

কারণ Stop Index 3 অন্তর্ভুক্ত হয় না।

### Mistake 2: Using Parentheses Instead of Square Brackets

ভুল:

```python
numbers = [10, 20, 30, 40]

print(numbers(1:3))
```

এটি invalid syntax।

Correct:

```python
print(numbers[1:3])
```

Output:

```text
[20, 30]
```

### Mistake 3: Confusing Negative Indexing

ভুল ধারণা:

```python
numbers = [10, 20, 30, 40, 50]

print(numbers[-3:-1])
```

অনেকে মনে করে output হবে:

```text
[30, 40, 50]
```

সঠিক Output:

```text
[30, 40]
```

কারণ `-1` হলো stopping index এবং এটি অন্তর্ভুক্ত হয় না।

### Mistake 4: Thinking Slicing Modifies the Original List

ভুল ধারণা:

```python
numbers = [10, 20, 30, 40, 50]

numbers[1:3]

print(numbers)
```

Output:

```text
[10, 20, 30, 40, 50]
```

কারণ Slicing-এর result কোনো variable-এ assign করা হয়নি এবং original List পরিবর্তন হয়নি।

Correct:

```python
numbers = [10, 20, 30, 40, 50]

result = numbers[1:3]

print(result)
```

Output:

```text
[20, 30]
```

## 19. Practice Exercises

### Exercise 1: Predict the Output

নিচের code-এর output কী হবে?

```python
numbers = [10, 20, 30, 40, 50, 60]

print(numbers[2:5])
```

Solution:

```text
[30, 40, 50]
```

### Exercise 2: Select the First Three Elements

একটি List থেকে প্রথম তিনটি element বের করো।

Solution:

```python
fruits = ["Apple", "Banana", "Mango", "Orange", "Grapes"]

print(fruits[:3])
```

Output:

```text
['Apple', 'Banana', 'Mango']
```

### Exercise 3: Select the Last Three Elements

Negative Indexing ব্যবহার করে শেষ তিনটি element বের করো।

Solution:

```python
numbers = [10, 20, 30, 40, 50, 60]

print(numbers[-3:])
```

Output:

```text
[40, 50, 60]
```

### Exercise 4: Use Both Start and Stop Index

নিচের List থেকে index 1 থেকে index 4-এর আগ পর্যন্ত elements বের করো।

Solution:

```python
languages = ["Python", "Java", "C++", "C", "JavaScript"]

print(languages[1:4])
```

Output:

```text
['Java', 'C++', 'C']
```

### Exercise 5: Create a New List Using Slicing

একটি List থেকে index 2 থেকে শেষ পর্যন্ত elements নিয়ে নতুন List তৈরি করো।

Solution:

```python
numbers = [10, 20, 30, 40, 50]

new_numbers = numbers[2:]

print(new_numbers)
```

Output:

```text
[30, 40, 50]
```

## 20. Chapter Summary

এই topic-এ আমরা শিখেছি:

- List Slicing কী।
- List Slicing-এর Basic Syntax।
- Start এবং Stop Index-এর ব্যবহার।
- Starting Index বাদ দিয়ে Slicing করা।
- Stopping Index বাদ দিয়ে Slicing করা।
- সম্পূর্ণ List Slicing করা।
- Negative Indexing দিয়ে Slicing করা।
- First এবং Last elements নির্বাচন করা।
- Slicing-এর মাধ্যমে নতুন List তৈরি করা।
- Original List এবং Sliced List-এর পার্থক্য।
- Out-of-range এবং Empty List Slicing।
- Indexing এবং Slicing-এর পার্থক্য।

## 21. Self-Assessment Checklist

- [ ] List Slicing কী বুঝি।
- [ ] List Slicing-এর Syntax লিখতে পারি।
- [ ] Start এবং Stop Index-এর কাজ বুঝি।
- [ ] Starting Index বাদ দিয়ে Slicing করতে পারি।
- [ ] Stopping Index বাদ দিয়ে Slicing করতে পারি।
- [ ] সম্পূর্ণ List Slicing করতে পারি।
- [ ] Negative Indexing দিয়ে Slicing করতে পারি।
- [ ] First এবং Last elements বের করতে পারি।
- [ ] Slicing দিয়ে নতুন List তৈরি করতে পারি।
- [ ] Indexing এবং Slicing-এর পার্থক্য বুঝি।
- [ ] Slicing কেন Original List পরিবর্তন করে না বুঝি।

## 22. Next Topic

**10. Modifying List Elements Using Slicing in Python**

পরবর্তী topic-এ আমরা শিখব কীভাবে List Slicing ব্যবহার করে একসাথে একাধিক element পরিবর্তন, replace এবং update করা যায়।