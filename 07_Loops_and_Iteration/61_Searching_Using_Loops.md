# 61. Searching Using Loops

## 1. Introduction

Searching হলো কোনো collection-এর মধ্যে নির্দিষ্ট একটি value খুঁজে বের করার প্রক্রিয়া।

ধরি, আমাদের কাছে একটি list আছে:

```python
numbers = [10, 20, 30, 40, 50]
```

এখন আমরা জানতে চাই:

- `30` list-এর মধ্যে আছে কি না।
- `40` কোন index-এ আছে।
- `60` list-এর মধ্যে আছে কি না।

Loop ব্যবহার করে list-এর প্রতিটি element পরীক্ষা করা যায়।

এই Topic-এ আমরা শিখব:

- Searching-এর basic concept
- `for` loop দিয়ে search করা
- `while` loop দিয়ে search করা
- Index ও position-এর পার্থক্য
- `break` এবং flag variable-এর ব্যবহার
- Linear Search algorithm
- প্রথম ও সব matching element খোঁজা
- Dry run, common mistakes ও practice problems

## 2. Understanding Searching

ধরি:

```python
numbers = [10, 20, 30, 40, 50]
target = 30
```

এখানে `target` হলো যে value-টি আমরা খুঁজছি।

Loop প্রতিটি element পরীক্ষা করবে:

```text
10 → 20 → 30 → 40 → 50
```

যখন `30` পাওয়া যাবে, তখন search সফল হবে।

কিন্তু `target = 60` হলে list-এর কোনো element-ই match করবে না। তখন search unsuccessful হবে।

**মূল ধারণা:**

1. একটি list বা collection থাকবে।
2. একটি target value থাকবে।
3. Loop দিয়ে element পরীক্ষা করা হবে।
4. Match পাওয়া গেলে search সফল হবে।
5. পুরো collection পরীক্ষা করেও match না পেলে search unsuccessful হবে।

## 3. Searching Using a `for` Loop

প্রথমে একটি list-এর মধ্যে target value আছে কি না, তা পরীক্ষা করি।

### Code

```python
numbers = [10, 20, 30, 40, 50]
target = 30

found = False

for number in numbers:
    if number == target:
        found = True
        break

if found:
    print("Value found")
else:
    print("Value not found")
```

### Output

```text
Value found
```

### Explanation

- `numbers` হলো search করার list।
- `target = 30` হলো যে value খুঁজছি।
- `found = False` দিয়ে শুরুতে ধরে নেওয়া হয় value পাওয়া যায়নি।
- `for` loop প্রতিটি element পরীক্ষা করে।
- `number == target` হলে `found = True` হয়।
- `break` দিয়ে search বন্ধ হয়।
- শেষে `found` দেখে result print করা হয়।

এখানে `found` হলো একটি **flag variable**। এটি search সফল হয়েছে কি না, সেই তথ্য সংরক্ষণ করে।

## 4. Searching When the Value Does Not Exist

এবার এমন একটি value খুঁজি, যা list-এ নেই।

### Code

```python
numbers = [10, 20, 30, 40, 50]
target = 60

found = False

for number in numbers:
    if number == target:
        found = True
        break

if found:
    print("Value found")
else:
    print("Value not found")
```

### Output

```text
Value not found
```

### Explanation

Loop প্রতিটি element পরীক্ষা করবে:

- `10 == 60` → False
- `20 == 60` → False
- `30 == 60` → False
- `40 == 60` → False
- `50 == 60` → False

কোনো match পাওয়া যায়নি। তাই `found`-এর value `False`-ই থাকে।

## 5. Dry Run of Searching

Code:

```python
numbers = [10, 20, 30, 40, 50]
target = 30
found = False

for number in numbers:
    if number == target:
        found = True
        break

print(found)
```

### Dry Run Table

| Iteration | Current Element | Comparison | `found` |
|---:|---:|---|---|
| 1 | 10 | `10 == 30` → False | False |
| 2 | 20 | `20 == 30` → False | False |
| 3 | 30 | `30 == 30` → True | True |

তৃতীয় iteration-এ target পাওয়া যায়। তাই `break` দিয়ে loop বন্ধ হয়।

### Output

```text
True
```

`40` ও `50` পরীক্ষা করার প্রয়োজন হয়নি।

## 6. Searching Using a `while` Loop

একই search logic `while` loop দিয়েও করা যায়।

### Code

```python
numbers = [10, 20, 30, 40, 50]
target = 40

index = 0
found = False

while index < len(numbers):
    if numbers[index] == target:
        found = True
        break

    index += 1

if found:
    print("Value found")
else:
    print("Value not found")
```

### Output

```text
Value found
```

### Explanation

- `index = 0` দিয়ে প্রথম element থেকে search শুরু হয়।
- `len(numbers)` list-এর মোট element সংখ্যা দেয়।
- `numbers[index]` দিয়ে বর্তমান element পাওয়া যায়।
- Match হলে `found = True` হয় এবং loop বন্ধ হয়।
- Match না হলে `index += 1` দিয়ে পরের element-এ যাওয়া হয়।

**গুরুত্বপূর্ণ:** `index += 1` বাদ দিলে target না পাওয়া অবস্থায় loop অনন্তকাল চলতে পারে, কারণ index পরিবর্তিত হবে না।

## 7. Finding the Index of a Target Value

কোনো value আছে কি না জানার পাশাপাশি সেটি কোন index-এ আছে, সেটিও বের করা যায়।

Python-এ list indexing `0` থেকে শুরু হয়।

```text
Index:     0   1   2   3   4
Value:    10  20  30  40  50
```

এখানে `30`-এর index হলো `2`।

### Code

```python
numbers = [10, 20, 30, 40, 50]
target = 30

position = -1

for index in range(len(numbers)):
    if numbers[index] == target:
        position = index
        break

if position != -1:
    print("Index:", position)
else:
    print("Value not found")
```

### Output

```text
Index: 2
```

### Explanation

- `range(len(numbers))` দিয়ে valid index পাওয়া যায়।
- `numbers[index]` দিয়ে সেই index-এর value পরীক্ষা করা হয়।
- Match হলে `position = index` করা হয়।
- `break` দিয়ে search বন্ধ হয়।
- `position = -1` বোঝায় যে এখনো target পাওয়া যায়নি।

এখানে `-1` একটি marker value। এটি list-এর valid index হিসেবে ব্যবহার করা হচ্ছে না।

## 8. Understanding Index and Position

Programming-এ index এবং সাধারণ গণনার position এক জিনিস নয়।

| Element | Index | Human-readable Position |
|---:|---:|---:|
| 10 | 0 | 1st |
| 20 | 1 | 2nd |
| 30 | 2 | 3rd |
| 40 | 3 | 4th |
| 50 | 4 | 5th |

যদি user-কে মানুষের মতো position দেখাতে চাও, তাহলে:

```python
position = index + 1
```

ব্যবহার করতে পারো।

উদাহরণ:

```python
numbers = [10, 20, 30, 40, 50]
target = 30

for index in range(len(numbers)):
    if numbers[index] == target:
        print("Position:", index + 1)
        break
```

Output:

```text
Position: 3
```

`30`-এর index `2`, কিন্তু মানুষের হিসাবে এটি তৃতীয় element।

## 9. Searching with User Input

এবার user-এর কাছ থেকে target value নিয়ে search করি।

### Code

```python
numbers = [10, 20, 30, 40, 50]

target = int(input("Enter a number to search: "))

found = False

for number in numbers:
    if number == target:
        found = True
        break

if found:
    print("Value found")
else:
    print("Value not found")
```

### Sample Output 1

```text
Enter a number to search: 40
Value found
```

### Sample Output 2

```text
Enter a number to search: 90
Value not found
```

এই উদাহরণে ধরে নেওয়া হয়েছে user integer input দেবেন। অন্য ধরনের input দিলে `int()` থেকে `ValueError` হতে পারে।

## 10. Finding All Occurrences of a Value

একটি list-এ একই value একাধিকবার থাকতে পারে।

```python
numbers = [10, 20, 10, 30, 10]
```

এখানে `10` তিনবার আছে।

সব occurrence খুঁজতে `break` ব্যবহার করা যাবে না। কারণ `break` প্রথম match পাওয়ার পর loop বন্ধ করে দেবে।

### Code

```python
numbers = [10, 20, 10, 30, 10]
target = 10

for index in range(len(numbers)):
    if numbers[index] == target:
        print("Found at index:", index)
```

### Output

```text
Found at index: 0
Found at index: 2
Found at index: 4
```

### Explanation

এখানে প্রতিটি index পরীক্ষা করা হয়েছে। কোনো match পাওয়ার পর loop বন্ধ করা হয়নি।

**মনে রাখবে:**

- শুধু প্রথম match দরকার হলে `break` ব্যবহার করো।
- সব match দরকার হলে পুরো loop চালাও।

## 11. Counting Occurrences of a Value

কোনো value কতবার আছে, সেটিও loop দিয়ে গণনা করা যায়।

### Code

```python
numbers = [10, 20, 10, 30, 10, 40]
target = 10

count = 0

for number in numbers:
    if number == target:
        count += 1

print("Occurrences:", count)
```

### Output

```text
Occurrences: 3
```

### Explanation

- `count = 0` দিয়ে শুরু হয়।
- প্রতিটি element target-এর সঙ্গে তুলনা করা হয়।
- Match হলে `count += 1` হয়।
- Loop শেষে মোট occurrence print হয়।

এখানে `break` নেই, কারণ সব match গণনা করতে হবে।

## 12. Linear Search Algorithm

এতক্ষণ আমরা যে পদ্ধতি ব্যবহার করেছি, সেটিকে **Linear Search** বলা হয়।

Linear Search হলো এমন একটি searching algorithm, যেখানে collection-এর element-গুলোকে একে একে পরীক্ষা করা হয়, যতক্ষণ না target পাওয়া যায় বা collection শেষ হয়।

### Algorithm Steps

1. প্রথম element থেকে শুরু করো।
2. বর্তমান element target-এর সমান কি না পরীক্ষা করো।
3. সমান হলে তার index return করো।
4. সমান না হলে পরের element পরীক্ষা করো।
5. পুরো collection-এ target না পাওয়া গেলে `-1` return করো।

### Implementation

```python
def linear_search(numbers, target):
    for index in range(len(numbers)):
        if numbers[index] == target:
            return index

    return -1


numbers = [10, 20, 30, 40, 50]

print(linear_search(numbers, 30))
print(linear_search(numbers, 60))
```

### Output

```text
2
-1
```

### Explanation

- `linear_search()` একটি function।
- Target পাওয়া গেলে `return index` result ফেরত দেয় এবং function শেষ হয়।
- Target না পাওয়া গেলে loop শেষ হওয়ার পরে `return -1` হয়।

এখানে `return` ব্যবহারের কারণে আলাদা flag variable প্রয়োজন হয়নি।

## 13. Linear Search Time Complexity

Linear Search-এর performance নির্ভর করে target কোথায় আছে এবং collection-এর আকার কত বড়, তার ওপর।

ধরি, list-এ `n`টি element আছে।

| Case | Situation | Time Complexity |
|---|---|---|
| Best Case | প্রথম element-এই target পাওয়া যায় | \(O(1)\) |
| Average Case | মাঝামাঝি কোথাও পাওয়া যায় | \(O(n)\) |
| Worst Case | শেষ element-এ পাওয়া যায় বা target নেই | \(O(n)\) |

### সহজ ব্যাখ্যা

- প্রথম element-এ target পেলে একটি comparison-ই যথেষ্ট।
- Target শেষে থাকলে প্রায় সব element পরীক্ষা করতে হয়।
- Target না থাকলেও পুরো list পরীক্ষা করতে হয়।

সাধারণ iterative Linear Search-এর auxiliary space complexity হলো \(O(1)\), কারণ algorithm নিজে অতিরিক্ত স্থায়ী memory খুব কম ব্যবহার করে।

## 14. Searching in a String

Loop দিয়ে string-এর মধ্যে character-ও search করা যায়।

### Code

```python
text = "programming"
target = "g"

found = False

for character in text:
    if character == target:
        found = True
        break

if found:
    print("Character found")
else:
    print("Character not found")
```

### Output

```text
Character found
```

এখানে `for` loop string-এর প্রতিটি character পরীক্ষা করে।

String-এ target character-এর index খুঁজতে চাইলে:

```python
text = "programming"
target = "g"

for index in range(len(text)):
    if text[index] == target:
        print("Index:", index)
        break
```

Output:

```text
Index: 3
```

এখানে প্রথম `g`-এর index print হয়েছে।

## 15. Searching in a List of Strings

List-এর মধ্যে string value-ও search করা যায়।

### Code

```python
students = ["Masum", "Ritu", "Mahin", "Tusher"]
target = "Mahin"

found = False

for student in students:
    if student == target:
        found = True
        break

if found:
    print("Student found")
else:
    print("Student not found")
```

### Output

```text
Student found
```

String comparison সাধারণত case-sensitive।

যেমন, `"Masum" == "masum"` False হবে।

Case-insensitive search প্রয়োজন হলে:

```python
students = ["Masum", "Ritu", "Mahin", "Tusher"]
target = "masum"

found = False

for student in students:
    if student.lower() == target.lower():
        found = True
        break

print(found)
```

Output:

```text
True
```

## 16. Common Mistakes

### Mistake 1: Forgetting to Initialize the Flag

ভুল:

```python
for number in numbers:
    if number == target:
        found = True
```

এখানে target না পাওয়া গেলে `found` তৈরি নাও হতে পারে।

সঠিক:

```python
found = False
```

Loop-এর আগে initialize করো।

### Mistake 2: Using `break` When All Matches Are Needed

প্রথম match-এর পর `break` দিলে বাকি occurrence খুঁজে পাওয়া যাবে না।

সব match খুঁজতে `break` বাদ দিতে হবে।

### Mistake 3: Confusing Index with Position

List-এর প্রথম element-এর index `0`, position `1`।

Human-readable position দরকার হলে `index + 1` ব্যবহার করো।

### Mistake 4: Forgetting to Increment the Index in a `while` Loop

ভুল:

```python
index = 0

while index < len(numbers):
    if numbers[index] == target:
        break
```

Target না পাওয়া গেলে index কখনো বাড়বে না, ফলে loop অনন্তকাল চলতে পারে।

সঠিক:

```python
index += 1
```

Match না হলে index বাড়াতে হবে।

### Mistake 5: Returning the Wrong Value

Linear Search-এ target না পেলে `-1` return করা একটি প্রচলিত convention।

তবে `-1`-কে list-এর valid index হিসেবে ব্যবহার করা উচিত নয়, কারণ Python-এ `numbers[-1]` শেষ element বোঝায়।

### Mistake 6: Using `return` Outside a Function

`return` শুধু function-এর ভেতরে ব্যবহার করা যায়। সাধারণ loop-এর মধ্যে function ছাড়া `return` লিখলে `SyntaxError` হবে।

### Mistake 7: Forgetting Case Sensitivity

`"Python"` ও `"python"` একই string নয়। Case-insensitive search দরকার হলে দুই string-কে একই case-এ রূপান্তর করতে পারো।

## 17. Practice Exercises

### Exercise 1

`[10, 20, 30, 40, 50]` list-এ `30` আছে কি না, `for` loop দিয়ে পরীক্ষা করো।

### Exercise 2

`while` loop ব্যবহার করে `[5, 10, 15, 20]` list-এ `15` খুঁজে বের করো।

### Exercise 3

`[12, 24, 36, 48]` list-এ `36`-এর index বের করো।

### Exercise 4

`[10, 20, 10, 30, 10]` list-এ `10`-এর সব index print করো।

### Exercise 5

নিচের code-এর output নির্ণয় করো:

```python
numbers = [2, 4, 6, 8]
target = 5
found = False

for number in numbers:
    if number == target:
        found = True
        break

print(found)
```

### Exercise 6

একটি list-এ নির্দিষ্ট value কতবার আছে, তা গণনা করার program লেখো।

### Exercise 7

`linear_search(numbers, target)` function লেখো, যা target পাওয়া গেলে index এবং না পেলে `-1` return করবে।

### Exercise 8

নিচের code-এ ভুলটি খুঁজে বের করো:

```python
numbers = [10, 20, 30]
target = 40
index = 0

while index < len(numbers):
    if numbers[index] == target:
        print("Found")
        break
```

### Exercise 9

Linear Search-এর best-case ও worst-case time complexity ব্যাখ্যা করো।

### Exercise 10

`["Python", "Java", "C++"]` list-এ `"Java"` search করো এবং তার position print করো।

## 18. Practice Answer Key

### Answer 1

```python
numbers = [10, 20, 30, 40, 50]
target = 30
found = False

for number in numbers:
    if number == target:
        found = True
        break

print(found)
```

Output:

```text
True
```

### Answer 2

```python
numbers = [5, 10, 15, 20]
target = 15

index = 0
found = False

while index < len(numbers):
    if numbers[index] == target:
        found = True
        break

    index += 1

print(found)
```

Output:

```text
True
```

### Answer 3

```python
numbers = [12, 24, 36, 48]
target = 36

for index in range(len(numbers)):
    if numbers[index] == target:
        print("Index:", index)
        break
```

Output:

```text
Index: 2
```

### Answer 4

```python
numbers = [10, 20, 10, 30, 10]

for index in range(len(numbers)):
    if numbers[index] == 10:
        print(index)
```

Output:

```text
0
2
4
```

### Answer 5

Output:

```text
False
```

কারণ `5` list-এর মধ্যে নেই।

### Answer 6

```python
numbers = [10, 20, 10, 30, 10]
target = 10
count = 0

for number in numbers:
    if number == target:
        count += 1

print(count)
```

Output:

```text
3
```

### Answer 7

```python
def linear_search(numbers, target):
    for index in range(len(numbers)):
        if numbers[index] == target:
            return index

    return -1


print(linear_search([10, 20, 30], 20))
print(linear_search([10, 20, 30], 40))
```

Output:

```text
1
-1
```

### Answer 8

এখানে `index += 1` নেই। Target না পাওয়া গেলে index `0`-তেই থেকে যায় এবং loop অনন্তকাল চলতে থাকে।

সঠিক code:

```python
numbers = [10, 20, 30]
target = 40
index = 0

while index < len(numbers):
    if numbers[index] == target:
        print("Found")
        break

    index += 1
else:
    print("Not found")
```

Output:

```text
Not found
```

এখানে `while`-এর `else` clause loop স্বাভাবিকভাবে শেষ হলে চলে; `break` দিয়ে শেষ হলে চলে না।

### Answer 9

- **Best case:** \(O(1)\), কারণ প্রথম element-এ target পাওয়া যায়।
- **Worst case:** \(O(n)\), কারণ শেষ পর্যন্ত সব element পরীক্ষা করতে হতে পারে।

### Answer 10

```python
languages = ["Python", "Java", "C++"]
target = "Java"

for index in range(len(languages)):
    if languages[index] == target:
        print("Position:", index + 1)
        break
```

Output:

```text
Position: 2
```

## 19. Chapter Summary

- Searching হলো collection-এর মধ্যে নির্দিষ্ট value খুঁজে বের করা।
- `for` ও `while` loop দিয়ে searching করা যায়।
- Flag variable দিয়ে value পাওয়া গেছে কি না বোঝানো যায়।
- `break` প্রথম match পাওয়ার পর loop বন্ধ করতে পারে।
- Index `0` থেকে শুরু হয়, কিন্তু human-readable position `1` থেকে।
- সব occurrence খুঁজতে পুরো collection পরীক্ষা করতে হয়।
- Linear Search একে একে প্রতিটি element পরীক্ষা করে।
- Linear Search-এর best-case time complexity \(O(1)\) এবং worst-case \(O(n)\)।
- Function দিয়ে search result return করা যায়।
- String ও string-এর list-এও loop দিয়ে search করা সম্ভব।

## 20. Completion Checklist

- [ ] `for` loop দিয়ে search করতে পারি।
- [ ] `while` loop দিয়ে search করতে পারি।
- [ ] Flag variable ব্যবহার করতে পারি।
- [ ] Target-এর index বের করতে পারি।
- [ ] Index ও position-এর পার্থক্য বুঝি।
- [ ] সব occurrence খুঁজে বের করতে পারি।
- [ ] Occurrence count করতে পারি।
- [ ] Linear Search function লিখতে পারি।
- [ ] Linear Search-এর time complexity বুঝি।
- [ ] Common searching mistakes শনাক্ত করতে পারি।

**Next Topic:** `62_Loop_Based_Menu_Programs.md`