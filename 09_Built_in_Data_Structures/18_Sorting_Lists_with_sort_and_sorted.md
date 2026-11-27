# 18. Sorting Lists with sort() and sorted() in Python

## 1. Introduction

Python List-এর elements নির্দিষ্ট ক্রমে সাজানোর প্রক্রিয়াকে **Sorting** বলা হয়।

Python-এ List Sort করার জন্য দুটি গুরুত্বপূর্ণ method/function রয়েছে:

1. `sort()` Method
2. `sorted()` Function

এগুলো ব্যবহার করে List-এর elements ছোট থেকে বড় অথবা বড় থেকে ছোট ক্রমে সাজানো যায়।

উদাহরণ:

```python
numbers = [40, 10, 30, 20, 50]

numbers.sort()

print(numbers)
```

Output:

```text
[10, 20, 30, 40, 50]
```

এখানে Number-গুলো ছোট থেকে বড় ক্রমে সাজানো হয়েছে।

## 2. Introduction to sort() Method

`sort()` হলো Python List-এর একটি Built-in Method।

এটি Original List-এর elements-গুলোকে সরাসরি সাজিয়ে দেয়।

Syntax:

```python
list_name.sort()
```

উদাহরণ:

```python
numbers = [50, 20, 40, 10, 30]

numbers.sort()

print(numbers)
```

Output:

```text
[10, 20, 30, 40, 50]
```

এখানে `sort()` Original List পরিবর্তন করেছে।

## 3. Sorting Numbers in Ascending Order

Ascending Order মানে ছোট থেকে বড় ক্রমে সাজানো।

`sort()` ব্যবহার করলে Defaultভাবে List Ascending Order-এ সাজানো হয়।

উদাহরণ:

```python
numbers = [80, 20, 60, 10, 40]

numbers.sort()

print(numbers)
```

Output:

```text
[10, 20, 40, 60, 80]
```

এখানে:

- সবচেয়ে ছোট Number প্রথমে এসেছে।
- সবচেয়ে বড় Number শেষে এসেছে।

## 4. Sorting Numbers in Descending Order

Descending Order মানে বড় থেকে ছোট ক্রমে সাজানো।

এর জন্য `sort()` Method-এর মধ্যে `reverse=True` ব্যবহার করতে হয়।

Syntax:

```python
list_name.sort(reverse=True)
```

উদাহরণ:

```python
numbers = [80, 20, 60, 10, 40]

numbers.sort(reverse=True)

print(numbers)
```

Output:

```text
[80, 60, 40, 20, 10]
```

এখানে সবচেয়ে বড় Number প্রথমে এবং সবচেয়ে ছোট Number শেষে এসেছে।

## 5. Introduction to sorted() Function

`sorted()` হলো Python-এর একটি Built-in Function।

এটি কোনো Iterable-এর elements Sort করে একটি নতুন List return করে।

Syntax:

```python
sorted(iterable)
```

উদাহরণ:

```python
numbers = [50, 20, 40, 10, 30]

result = sorted(numbers)

print(result)
```

Output:

```text
[10, 20, 30, 40, 50]
```

এখানে `sorted()` একটি নতুন Sorted List তৈরি করেছে।

## 6. Sorting Numbers with sorted() in Ascending Order

`sorted()` Function Defaultভাবে Ascending Order-এ elements সাজায়।

উদাহরণ:

```python
numbers = [70, 30, 90, 10, 50]

result = sorted(numbers)

print(result)
```

Output:

```text
[10, 30, 50, 70, 90]
```

## 7. Sorting Numbers with sorted() in Descending Order

`sorted()` Function-এর ক্ষেত্রেও `reverse=True` ব্যবহার করে Descending Order-এ Sort করা যায়।

উদাহরণ:

```python
numbers = [70, 30, 90, 10, 50]

result = sorted(numbers, reverse=True)

print(result)
```

Output:

```text
[90, 70, 50, 30, 10]
```

## 8. Difference Between sort() and sorted()

`sort()` এবং `sorted()`-এর মধ্যে সবচেয়ে গুরুত্বপূর্ণ পার্থক্য হলো Original List-এর পরিবর্তন।

| sort() | sorted() |
|---|---|
| এটি একটি List Method। | এটি একটি Built-in Function। |
| Original List পরিবর্তন করে। | Original List পরিবর্তন করে না। |
| নতুন List return করে না। | নতুন Sorted List return করে। |
| শুধু List-এর ক্ষেত্রে ব্যবহার করা যায়। | বিভিন্ন Iterable-এর ক্ষেত্রে ব্যবহার করা যায়। |
| `list_name.sort()` | `sorted(list_name)` |

উদাহরণ:

```python
numbers = [40, 10, 30, 20]

result = sorted(numbers)

print("Original List:", numbers)
print("Sorted List:", result)

numbers.sort()

print("After sort():", numbers)
```

Output:

```text
Original List: [40, 10, 30, 20]
Sorted List: [10, 20, 30, 40]
After sort(): [10, 20, 30, 40]
```

এখানে:

- `sorted()` Original List অপরিবর্তিত রেখেছে।
- `sort()` Original List পরিবর্তন করেছে।

## 9. Sorting String Elements

String-এর List-ও Alphabetical Order অনুযায়ী Sort করা যায়।

উদাহরণ:

```python
fruits = ["Mango", "Apple", "Banana", "Orange"]

fruits.sort()

print(fruits)
```

Output:

```text
['Apple', 'Banana', 'Mango', 'Orange']
```

এখানে String-গুলো Alphabetical Order-এ সাজানো হয়েছে।

## 10. Sorting Strings in Descending Order

String-এর List-ও Descending Order-এ Sort করা যায়।

উদাহরণ:

```python
fruits = ["Mango", "Apple", "Banana", "Orange"]

fruits.sort(reverse=True)

print(fruits)
```

Output:

```text
['Orange', 'Mango', 'Banana', 'Apple']
```

এখানে Reverse Alphabetical Order-এ সাজানো হয়েছে।

## 11. Sorting Strings with sorted()

`sorted()` Function ব্যবহার করেও String-এর List Sort করা যায়।

উদাহরণ:

```python
languages = ["Python", "Java", "C++", "JavaScript"]

result = sorted(languages)

print(result)
```

Output:

```text
['C++', 'Java', 'JavaScript', 'Python']
```

এখানে Original List পরিবর্তন না করে নতুন Sorted List তৈরি হয়েছে।

## 12. Sorting Mixed Case Strings

Python-এ সাধারণ String Sorting Unicode Character-এর মান অনুযায়ী হয়। তাই Uppercase এবং Lowercase String একসঙ্গে থাকলে Sorting-এর Result কিছুটা আলাদা হতে পারে।

উদাহরণ:

```python
names = ["masum", "Abdulla", "rahim", "Karim"]

names.sort()

print(names)
```

Output:

```text
['Abdulla', 'Karim', 'masum', 'rahim']
```

এখানে Uppercase এবং Lowercase letters-এর Sorting Order এক নয়।

### Case-Insensitive Sorting

Uppercase এবং Lowercase-এর পার্থক্য উপেক্ষা করে Sort করতে চাইলে `key=str.lower` ব্যবহার করা যায়।

উদাহরণ:

```python
names = ["masum", "Abdulla", "rahim", "Karim"]

names.sort(key=str.lower)

print(names)
```

Output:

```text
['Abdulla', 'Karim', 'masum', 'rahim']
```

এখানে Sorting করার সময় প্রতিটি String-এর Lowercase value বিবেচনা করা হয়েছে।

## 13. Sorting with key Parameter

`sort()` এবং `sorted()`-এ `key` Parameter ব্যবহার করে কোন নিয়মে Sorting হবে তা নির্ধারণ করা যায়।

উদাহরণ:

```python
words = ["Banana", "Kiwi", "Apple", "Watermelon"]

words.sort(key=len)

print(words)
```

Output:

```text
['Kiwi', 'Apple', 'Banana', 'Watermelon']
```

এখানে `key=len` প্রতিটি Word-এর Length অনুযায়ী Sort করেছে।

আরও একটি উদাহরণ:

```python
words = ["Banana", "Kiwi", "Apple", "Watermelon"]

result = sorted(words, key=len)

print(result)
```

Output:

```text
['Kiwi', 'Apple', 'Banana', 'Watermelon']
```

এখানে `sorted()` ব্যবহার করেও Word-এর Length অনুযায়ী Sorting করা হয়েছে।

**Note:** একই Length-এর elements থাকলে Python তাদের আগের Relative Order বজায় রাখে। একে Stable Sorting বলা হয়।

## 14. Sorting a List of Tuples

একটি List-এর মধ্যে Tuple থাকলেও Sorting করা যায়।

Python Defaultভাবে Tuple-এর প্রথম element অনুযায়ী Sorting শুরু করে।

উদাহরণ:

```python
students = [
    ("Masum", 85),
    ("Rahim", 70),
    ("Karim", 90)
]

students.sort()

print(students)
```

Output:

```text
[('Karim', 90), ('Masum', 85), ('Rahim', 70)]
```

এখানে Tuple-এর প্রথম element অর্থাৎ Name অনুযায়ী Sorting হয়েছে।

### Sorting Tuples by Marks

Marks অনুযায়ী Sorting করতে `key` ব্যবহার করা যায়।

উদাহরণ:

```python
students = [
    ("Masum", 85),
    ("Rahim", 70),
    ("Karim", 90)
]

students.sort(key=lambda student: student[1])

print(students)
```

Output:

```text
[('Rahim', 70), ('Masum', 85), ('Karim', 90)]
```

এখানে:

- `student[1]` Tuple-এর দ্বিতীয় element অর্থাৎ Marks নির্দেশ করে।
- `key` Marks অনুযায়ী Sorting করেছে।

## 15. Sorting a List of Dictionaries

Dictionary-এর List-ও `key` ব্যবহার করে Sort করা যায়।

উদাহরণ:

```python
students = [
    {"name": "Masum", "marks": 85},
    {"name": "Rahim", "marks": 70},
    {"name": "Karim", "marks": 90}
]

students.sort(key=lambda student: student["marks"])

print(students)
```

Output:

```text
[{'name': 'Rahim', 'marks': 70}, {'name': 'Masum', 'marks': 85}, {'name': 'Karim', 'marks': 90}]
```

এখানে Dictionary-এর `"marks"` value অনুযায়ী Sorting হয়েছে।

## 16. Sorting with reverse=True and key Together

`key` এবং `reverse=True` একসঙ্গে ব্যবহার করা যায়।

উদাহরণ:

```python
words = ["Banana", "Kiwi", "Apple", "Watermelon"]

words.sort(key=len, reverse=True)

print(words)
```

Output:

```text
['Watermelon', 'Banana', 'Apple', 'Kiwi']
```

এখানে:

- `key=len` Word-এর Length অনুযায়ী Sort করেছে।
- `reverse=True` বড় Length থেকে ছোট Length-এ সাজিয়েছে।

## 17. Sorting Different Iterables with sorted()

`sorted()` শুধু List-এর জন্য নয়। এটি বিভিন্ন Iterable-এর উপর কাজ করতে পারে।

### Sorting a Tuple

```python
numbers = (40, 10, 30, 20)

result = sorted(numbers)

print(result)
```

Output:

```text
[10, 20, 30, 40]
```

এখানে Tuple থেকে একটি নতুন Sorted List তৈরি হয়েছে।

### Sorting a String

```python
text = "python"

result = sorted(text)

print(result)
```

Output:

```text
['h', 'n', 'o', 'p', 't', 'y']
```

এখানে String-এর Characters Sort করে একটি List return করা হয়েছে।

### Sorting a Set

```python
numbers = {40, 10, 30, 20}

result = sorted(numbers)

print(result)
```

Output:

```text
[10, 20, 30, 40]
```

এখানে Set-এর elements Sort করে একটি List তৈরি হয়েছে।

**Important:** `sort()` শুধু List-এর Method। Tuple, String বা Set-এর উপর সরাসরি `.sort()` ব্যবহার করা যায় না।

## 18. What Does sort() Return?

`sort()` Original List পরিবর্তন করে, কিন্তু এটি `None` return করে।

অন্যদিকে `sorted()` একটি নতুন Sorted List return করে।

উদাহরণ:

```python
numbers = [30, 10, 20]

result = numbers.sort()

print(result)
print(numbers)
```

Output:

```text
None
[10, 20, 30]
```

এখানে `result`-এর value `None`, কারণ `sort()` নতুন List return করে না।

অন্যদিকে:

```python
numbers = [30, 10, 20]

result = sorted(numbers)

print(result)
```

Output:

```text
[10, 20, 30]
```

## 19. Important Rules

- `sort()` একটি List Method।
- `sorted()` একটি Built-in Function।
- Defaultভাবে উভয়েই Ascending Order-এ Sort করে।
- `reverse=True` ব্যবহার করে Descending Order-এ Sort করা যায়।
- `sort()` Original List পরিবর্তন করে।
- `sorted()` Original Iterable পরিবর্তন করে না।
- `sort()` `None` return করে।
- `sorted()` একটি নতুন List return করে।
- `key` Parameter দিয়ে Sorting-এর নিয়ম নির্ধারণ করা যায়।
- `sort()` শুধু List-এর ক্ষেত্রে ব্যবহার করা যায়।
- `sorted()` বিভিন্ন Iterable-এর ক্ষেত্রে ব্যবহার করা যায়।
- Python-এর Sorting Stable।

## 20. Common Mistakes

### Mistake 1: Assigning sort() Result to a Variable

ভুল:

```python
numbers = [30, 10, 20]

result = numbers.sort()

print(result)
```

Output:

```text
None
```

কারণ `sort()` কোনো নতুন List return করে না।

Correct:

```python
numbers = [30, 10, 20]

numbers.sort()

print(numbers)
```

Output:

```text
[10, 20, 30]
```

### Mistake 2: Using sort() on a Tuple

ভুল:

```python
numbers = (30, 10, 20)

numbers.sort()
```

Output:

```text
AttributeError: 'tuple' object has no attribute 'sort'
```

কারণ Tuple-এর মধ্যে `sort()` Method নেই।

Correct:

```python
numbers = (30, 10, 20)

result = sorted(numbers)

print(result)
```

Output:

```text
[10, 20, 30]
```

### Mistake 3: Confusing reverse=True with reverse()

`reverse=True` এবং `reverse()` এক জিনিস নয়।

- `reverse=True` Sorting-এর সময় Descending Order নির্ধারণ করে।
- `reverse()` List-এর বর্তমান Order উল্টে দেয়; এটি Sort করে না।

উদাহরণ:

```python
numbers = [30, 10, 20]

numbers.reverse()

print(numbers)
```

Output:

```text
[20, 10, 30]
```

অন্যদিকে:

```python
numbers = [30, 10, 20]

numbers.sort(reverse=True)

print(numbers)
```

Output:

```text
[30, 20, 10]
```

### Mistake 4: Forgetting Parentheses

ভুল:

```python
numbers = [30, 10, 20]

numbers.sort

print(numbers)
```

Output:

```text
[30, 10, 20]
```

এখানে `sort` Method Call করা হয়নি।

Correct:

```python
numbers = [30, 10, 20]

numbers.sort()

print(numbers)
```

Output:

```text
[10, 20, 30]
```

## 21. Practice Exercises

### Exercise 1: Sort Numbers in Ascending Order

নিচের List-টি ছোট থেকে বড় ক্রমে সাজাও।

Solution:

```python
numbers = [50, 20, 40, 10, 30]

numbers.sort()

print(numbers)
```

Output:

```text
[10, 20, 30, 40, 50]
```

### Exercise 2: Sort Numbers in Descending Order

নিচের List-টি বড় থেকে ছোট ক্রমে সাজাও।

Solution:

```python
numbers = [50, 20, 40, 10, 30]

numbers.sort(reverse=True)

print(numbers)
```

Output:

```text
[50, 40, 30, 20, 10]
```

### Exercise 3: Use sorted() Without Changing Original List

Solution:

```python
numbers = [40, 10, 30, 20]

result = sorted(numbers)

print("Original:", numbers)
print("Sorted:", result)
```

Output:

```text
Original: [40, 10, 30, 20]
Sorted: [10, 20, 30, 40]
```

### Exercise 4: Sort Words by Length

Solution:

```python
words = ["Apple", "Kiwi", "Banana", "Cat"]

words.sort(key=len)

print(words)
```

Output:

```text
['Cat', 'Kiwi', 'Apple', 'Banana']
```

### Exercise 5: Predict the Output

নিচের Code-এর Output কী হবে?

```python
numbers = [5, 2, 8, 1, 9]

result = sorted(numbers, reverse=True)

print(result)
print(numbers)
```

Solution:

```text
[9, 8, 5, 2, 1]
[5, 2, 8, 1, 9]
```

কারণ `sorted()` Original List পরিবর্তন করে না।

## 22. Chapter Summary

এই Topic-এ আমরা শিখেছি:

- Sorting কী এবং কেন ব্যবহার করা হয়।
- `sort()` Method-এর ব্যবহার।
- `sorted()` Function-এর ব্যবহার।
- Ascending এবং Descending Order।
- `reverse=True`-এর ব্যবহার।
- `sort()` এবং `sorted()`-এর পার্থক্য।
- Number এবং String Sorting।
- Case-Insensitive Sorting।
- `key` Parameter-এর ব্যবহার।
- Tuple এবং Dictionary-এর List Sorting।
- বিভিন্ন Iterable-কে `sorted()` দিয়ে Sort করা।
- `sort()`-এর Return Value।
- Common Mistakes এবং তাদের সমাধান।

## 23. Self-Assessment Checklist

- [ ] Sorting কী বুঝি।
- [ ] `sort()` Method ব্যবহার করতে পারি।
- [ ] `sorted()` Function ব্যবহার করতে পারি।
- [ ] Ascending Order-এ Sort করতে পারি।
- [ ] Descending Order-এ Sort করতে পারি।
- [ ] `sort()` এবং `sorted()`-এর পার্থক্য বুঝি।
- [ ] `key` Parameter ব্যবহার করতে পারি।
- [ ] String এবং Number Sort করতে পারি।
- [ ] Tuple এবং Dictionary-এর List Sort করতে পারি।
- [ ] `sort()` কেন `None` return করে বুঝি।

## 24. Next Topic

**19. Reversing Lists in Python**

পরবর্তী Topic-এ আমরা শিখব কীভাবে Python List-এর elements-এর Order উল্টে দিতে হয়। এজন্য `reverse()` এবং অন্যান্য পদ্ধতি সম্পর্কে জানব।