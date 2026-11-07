# 18. Nested Conditional Expressions

## 1. Nested Conditional Expression কী?

একটি Conditional Expression-এর ভেতরে আরেকটি Conditional Expression ব্যবহার করাকে **Nested Conditional Expression** বলে।

এটি ব্যবহার করে একাধিক condition পরীক্ষা করে নির্দিষ্ট value নির্বাচন করা যায়।

উদাহরণ:

```python
marks = 75

grade = "A" if marks >= 80 else (
    "B" if marks >= 60 else "C"
)

print(grade)
```

Output:

```text
B
```

ব্যাখ্যা:

1. প্রথমে `marks >= 80` পরীক্ষা হবে।
2. এটি False হওয়ায় `else`-এর পরের expression evaluate হবে।
3. এবার `marks >= 60` পরীক্ষা হবে।
4. এটি True হওয়ায় `"B"` নির্বাচন হবে।

এখানে একটি Conditional Expression-এর `else` অংশে আরেকটি Conditional Expression রয়েছে।

## 2. Nested Conditional Expression-এর Syntax

সাধারণ Ternary Operator-এর syntax:

```python
value_if_true if condition else value_if_false
```

Nested Conditional Expression-এর একটি সাধারণ গঠন:

```python
value1 if condition1 else (
    value2 if condition2 else value3
)
```

এখানে:

- `condition1` True হলে `value1` নির্বাচন হবে।
- `condition1` False এবং `condition2` True হলে `value2` নির্বাচন হবে।
- দুটি condition-ই False হলে `value3` নির্বাচন হবে।

**মনে রাখবে:** Nested Conditional Expression-এ parentheses ব্যবহার করলে expression-এর গঠন বোঝা সহজ হয়।

## 3. Nested Conditional Expression কীভাবে কাজ করে?

উদাহরণ:

```python
age = 16

category = "Child" if age < 13 else (
    "Teenager" if age < 20 else "Adult"
)

print(category)
```

Output:

```text
Teenager
```

ধাপে ধাপে:

**Step 1:** প্রথম condition পরীক্ষা হবে।

```python
age < 13
```

এটি False, কারণ বয়স ১৬।

**Step 2:** `else`-এর ভেতরের expression evaluate হবে।

```python
"Teenager" if age < 20 else "Adult"
```

**Step 3:** দ্বিতীয় condition পরীক্ষা হবে।

```python
age < 20
```

এটি True।

তাই final result:

```text
Teenager
```

## 4. Grade Calculator তৈরি করা

Nested Conditional Expression দিয়ে একটি সাধারণ grade calculator তৈরি করা যায়।

```python
marks = 85

grade = "A" if marks >= 80 else (
    "B" if marks >= 70 else (
        "C" if marks >= 60 else "F"
    )
)

print(grade)
```

Output:

```text
A
```

এখানে:

| Marks | Grade |
|---|---|
| 80 বা তার বেশি | A |
| 70–79 | B |
| 60–69 | C |
| 60-এর কম | F |

আরেকটি উদাহরণ:

```python
marks = 72

grade = "A" if marks >= 80 else (
    "B" if marks >= 70 else (
        "C" if marks >= 60 else "F"
    )
)

print(grade)
```

Output:

```text
B
```

কারণ `marks >= 80` False, কিন্তু `marks >= 70` True।

**সতর্কতা:** এটি একটি উদাহরণভিত্তিক grading scale। বাস্তবে তোমার প্রতিষ্ঠানের নির্ধারিত grading rules অনুসরণ করবে।

## 5. Positive, Negative এবং Zero নির্ণয়

একটি সংখ্যা positive, negative নাকি zero, তা Nested Conditional Expression দিয়ে নির্ণয় করা যায়।

```python
number = -10

result = "Positive" if number > 0 else (
    "Negative" if number < 0 else "Zero"
)

print(result)
```

Output:

```text
Negative
```

ব্যাখ্যা:

- `number > 0` False।
- এরপর `number < 0` True।
- তাই `"Negative"` নির্বাচন হয়।

যদি `number = 0` হয়, তাহলে প্রথম ও দ্বিতীয় condition দুটিই False হবে। ফলে `"Zero"` নির্বাচন হবে।

তবে এই সমস্যার জন্য সাধারণ `if-elif-else` আরও সহজে পড়া যায়।

## 6. Nested Conditional Expression দিয়ে Maximum Number

তিনটি সংখ্যার মধ্যে সবচেয়ে বড় সংখ্যা বের করার একটি উদাহরণ:

```python
a = 10
b = 25
c = 15

maximum = (
    a if a >= b and a >= c
    else (b if b >= c else c)
)

print(maximum)
```

Output:

```text
25
```

ব্যাখ্যা:

1. প্রথমে পরীক্ষা হবে `a` অন্য দুটি সংখ্যার চেয়ে বড় বা সমান কি না।
2. এটি False হওয়ায় দ্বিতীয় expression evaluate হবে।
3. `b >= c` True হওয়ায় `b` নির্বাচন হবে।
4. তাই maximum হলো `25`।

এই code কাজ করলেও তিনটি সংখ্যার maximum বের করার জন্য Python-এর built-in `max()` function আরও সহজ:

```python
a = 10
b = 25
c = 15

maximum = max(a, b, c)

print(maximum)
```

Output:

```text
25
```

## 7. Nested Conditional Expression বনাম Nested `if`

Nested Conditional Expression এবং Nested `if` একই ধরনের decision-making কাজে ব্যবহার হতে পারে, কিন্তু তাদের গঠন আলাদা।

### Nested Conditional Expression

```python
age = 20

category = "Child" if age < 13 else (
    "Teenager" if age < 20 else "Adult"
)

print(category)
```

Output:

```text
Adult
```

### Nested `if-else`

```python
age = 20

if age < 13:
    category = "Child"
else:
    if age < 20:
        category = "Teenager"
    else:
        category = "Adult"

print(category)
```

Output:

```text
Adult
```

দুটি program-এর result একই।

তবে Nested `if-else`-এ প্রতিটি condition আলাদা block-এ লেখা হয়। ফলে জটিল logic-এর ক্ষেত্রে এটি বোঝা এবং পরিবর্তন করা সহজ হতে পারে।

## 8. Nested Conditional Expression বনাম `if-elif-else`

অনেক condition পরীক্ষা করার জন্য `if-elif-else` সাধারণত বেশি readable।

Nested Conditional Expression:

```python
marks = 55

grade = "A" if marks >= 80 else (
    "B" if marks >= 70 else (
        "C" if marks >= 60 else "F"
    )
)

print(grade)
```

Output:

```text
F
```

একই কাজ `if-elif-else` দিয়ে:

```python
marks = 55

if marks >= 80:
    grade = "A"
elif marks >= 70:
    grade = "B"
elif marks >= 60:
    grade = "C"
else:
    grade = "F"

print(grade)
```

Output:

```text
F
```

দ্বিতীয় code-টি পড়তে এবং debugging করতে তুলনামূলক সহজ।

**Best practice:** দুটি বা অল্প কয়েকটি সহজ outcome-এর জন্য Conditional Expression ব্যবহার করতে পারো। অনেক condition বা জটিল logic হলে `if-elif-else` বেছে নাও।

## 9. Common Mistakes

### Mistake 1: `else` বাদ দেওয়া

ভুল:

```python
result = "A" if marks >= 80
```

এটি `SyntaxError` তৈরি করবে, কারণ Conditional Expression-এ `else` বাধ্যতামূলক।

সঠিক:

```python
result = "A" if marks >= 80 else "B"
```

### Mistake 2: Condition-এর order ভুল রাখা

```python
marks = 85

grade = "B" if marks >= 60 else (
    "A" if marks >= 80 else "F"
)

print(grade)
```

Output:

```text
B
```

কেন?

`marks >= 60` প্রথমেই True হয়েছে। তাই পরের condition আর পরীক্ষা করা হয়নি।

সঠিক order:

```python
grade = "A" if marks >= 80 else (
    "B" if marks >= 60 else "F"
)
```

যে condition বেশি নির্দিষ্ট বা বেশি threshold চায়, সেটি আগে পরীক্ষা করা প্রয়োজন হতে পারে।

### Mistake 3: Parentheses না দিয়ে expression জটিল করা

অতিরিক্ত nested expression এক লাইনে লিখলে ভুল হওয়ার সম্ভাবনা বাড়ে।

অস্পষ্ট:

```python
grade = "A" if marks >= 80 else "B" if marks >= 60 else "F"
```

এটি Python-এ valid, কিন্তু nested structure দ্রুত বোঝা কঠিন হতে পারে।

আরও পরিষ্কার:

```python
grade = "A" if marks >= 80 else (
    "B" if marks >= 60 else "F"
)
```

### Mistake 4: অপ্রয়োজনীয়ভাবে Nested Ternary ব্যবহার

যদি একই কাজ সহজ `if-elif-else` দিয়ে লেখা যায়, তাহলে শুধু code ছোট করার জন্য nested expression ব্যবহার করা জরুরি নয়।

Readable code লেখা বেশি গুরুত্বপূর্ণ।

## 10. Practice Exercises

প্রতিটি প্রশ্নের output নিজে বের করার চেষ্টা করো।

### Question 1

```python
x = 15

result = "High" if x > 20 else (
    "Medium" if x > 10 else "Low"
)

print(result)
```

### Question 2

```python
marks = 65

grade = "A" if marks >= 80 else (
    "B" if marks >= 60 else "F"
)

print(grade)
```

### Question 3

```python
number = 0

result = "Positive" if number > 0 else (
    "Negative" if number < 0 else "Zero"
)

print(result)
```

### Question 4

```python
age = 12

category = "Child" if age < 13 else (
    "Teenager" if age < 20 else "Adult"
)

print(category)
```

### Question 5

```python
marks = 90

grade = "B" if marks >= 60 else (
    "A" if marks >= 80 else "F"
)

print(grade)
```

### Question 6

```python
a = 5
b = 10
c = 8

result = a if a > b and a > c else (
    b if b > c else c
)

print(result)
```

## 11. Answer Key

### Answer 1

```text
Medium
```

কারণ `x > 20` False, কিন্তু `x > 10` True।

### Answer 2

```text
B
```

কারণ `marks >= 80` False, কিন্তু `marks >= 60` True।

### Answer 3

```text
Zero
```

কারণ সংখ্যাটি zero; এটি positive বা negative নয়।

### Answer 4

```text
Child
```

কারণ `age < 13` True।

### Answer 5

```text
B
```

প্রথম condition `marks >= 60` True হওয়ায় `"B"` নির্বাচন হয়েছে। এটি condition-এর ভুল order-এর উদাহরণ।

### Answer 6

```text
10
```

প্রথম condition False। এরপর `b > c` True হওয়ায় `b` নির্বাচন হয়েছে।

## 12. Quick Revision

- **Nested Conditional Expression:** একটি Conditional Expression-এর মধ্যে আরেকটি Conditional Expression।
- একাধিক condition অনুযায়ী value নির্বাচন করতে পারে।
- Syntax-এর প্রতিটি Conditional Expression-এ `if`, condition এবং `else` থাকতে হবে।
- Condition-এর order গুরুত্বপূর্ণ।
- Parentheses ব্যবহার করলে nested structure বোঝা সহজ হয়।
- অনেক condition থাকলে `if-elif-else` সাধারণত বেশি readable।
- শুধু code ছোট করার জন্য readability নষ্ট করা উচিত নয়।

## 13. Self-Assessment Checklist

- [ ] Nested Conditional Expression কী, তা বুঝি।
- [ ] এর syntax লিখতে পারি।
- [ ] Nested expression ধাপে ধাপে evaluate করতে পারি।
- [ ] Grade ও number classification-এর মতো সমস্যা সমাধান করতে পারি।
- [ ] Condition-এর order ভুল হলে কী সমস্যা হয়, তা বুঝি।
- [ ] Nested Conditional Expression ও `if-elif-else`-এর পার্থক্য বুঝি।
- [ ] Readable code লেখার জন্য সঠিক structure নির্বাচন করতে পারি।

**পরবর্তী টপিক:** `19_Membership_Operators_in_Conditions.md`