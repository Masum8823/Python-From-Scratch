# 21. Chained Comparisons in Conditions

## 1. Chained Comparison কী?

Python-এ একাধিক comparison operator পরপর ব্যবহার করে কোনো value নির্দিষ্ট range-এর মধ্যে আছে কি না, তা পরীক্ষা করা যায়। একে **Chained Comparison** বলে।

উদাহরণ:

```python
age = 25

print(18 <= age < 60)
```

Output:

```text
True
```

এখানে Python দুটি comparison পরীক্ষা করে:

```python
18 <= age
age < 60
```

দুটিই True হওয়ায় পুরো expression-এর result `True`।

সহজভাবে মনে রাখবে, `18 <= age < 60` অর্থ:

- `age` 18-এর সমান বা বড় হতে হবে।
- `age` 60-এর ছোট হতে হবে।

দুটি শর্তই পূরণ হতে হবে।

## 2. Chained Comparison-এর Syntax

সাধারণ গঠন:

```python
value1 comparison_operator value2 comparison_operator value3
```

উদাহরণ:

```python
10 < 20 < 30
```

এটি নিচের দুটি comparison-এর সমতুল্য:

```python
10 < 20 and 20 < 30
```

Output:

```text
True
```

আরেকটি উদাহরণ:

```python
5 < 10 < 8
```

Output:

```text
False
```

কারণ:

- `5 < 10` → `True`
- `10 < 8` → `False`

সব comparison True না হওয়ায় পুরো expression False।

## 3. Chained Comparison কীভাবে কাজ করে?

উদাহরণ:

```python
marks = 75

if 40 <= marks <= 100:
    print("Valid marks")
else:
    print("Invalid marks")
```

Output:

```text
Valid marks
```

এখানে condition-এর অর্থ:

```python
40 <= marks and marks <= 100
```

অর্থাৎ marks কমপক্ষে 40 এবং সর্বোচ্চ 100 হতে হবে।

যদি `marks = 120` হয়:

```python
marks = 120

if 40 <= marks <= 100:
    print("Valid marks")
else:
    print("Invalid marks")
```

Output:

```text
Invalid marks
```

কারণ `120 <= 100` False।

## 4. Chained Comparison বনাম `and`

একই range পরীক্ষা করার জন্য Chained Comparison এবং `and` ব্যবহার করা যায়।

### Chained Comparison

```python
age = 25

if 18 <= age < 60:
    print("Eligible age")
```

### `and` ব্যবহার করে

```python
age = 25

if age >= 18 and age < 60:
    print("Eligible age")
```

দুটি code-এর result একই।

| Chained Comparison | `and` দিয়ে |
|---|---|
| `18 <= age < 60` | `age >= 18 and age < 60` |
| সংক্ষিপ্ত | তুলনামূলক দীর্ঘ |
| Range বোঝা সহজ | প্রতিটি condition আলাদা করে দেখা যায় |

**Best practice:** সাধারণ numeric range পরীক্ষা করার ক্ষেত্রে Chained Comparison বেশ readable।

## 5. Inclusive এবং Exclusive Range

Chained Comparison-এ কোন boundary অন্তর্ভুক্ত হবে, তা operator-এর ওপর নির্ভর করে।

| Expression | অর্থ |
|---|---|
| `10 < x < 20` | \(10 < x < 20\), দুই boundary-ই বাদ |
| `10 <= x < 20` | 10 অন্তর্ভুক্ত, 20 বাদ |
| `10 < x <= 20` | 10 বাদ, 20 অন্তর্ভুক্ত |
| `10 <= x <= 20` | 10 ও 20 দুটোই অন্তর্ভুক্ত |

উদাহরণ:

```python
x = 10

print(10 < x <= 20)
print(10 <= x <= 20)
```

Output:

```text
False
True
```

কারণ প্রথম expression-এ `x` অবশ্যই 10-এর চেয়ে বড় হতে হবে। কিন্তু দ্বিতীয় expression-এ `x` 10-এর সমান হলেও চলে।

## 6. Grade Range পরীক্ষা করা

Chained Comparison দিয়ে নির্দিষ্ট range-এর মধ্যে marks আছে কি না, তা পরীক্ষা করা যায়।

```python
marks = 85

if 80 <= marks <= 100:
    print("Grade A")
elif 70 <= marks < 80:
    print("Grade B")
elif 60 <= marks < 70:
    print("Grade C")
else:
    print("Below Grade C")
```

Output:

```text
Grade A
```

এখানে প্রতিটি condition একটি নির্দিষ্ট range পরীক্ষা করছে।

- `80 <= marks <= 100` → 80 থেকে 100 পর্যন্ত।
- `70 <= marks < 80` → 70 থেকে 80-এর কম।
- `60 <= marks < 70` → 60 থেকে 70-এর কম।

প্রথম যে condition True হবে, তার block execute হবে।

**Note:** এখানে ব্যবহৃত grading ranges শুধু উদাহরণের জন্য। বাস্তব পরীক্ষায় সংশ্লিষ্ট প্রতিষ্ঠানের grading policy অনুসরণ করবে।

## 7. বয়সের Range পরীক্ষা করা

ধরা যাক, 13 থেকে 19 বছর বয়সীদের Teenager বলা হবে।

```python
age = 16

if 13 <= age <= 19:
    print("Teenager")
else:
    print("Not a teenager")
```

Output:

```text
Teenager
```

যদি `age = 20` হয়, তাহলে condition False হবে।

```python
age = 20

if 13 <= age <= 19:
    print("Teenager")
else:
    print("Not a teenager")
```

Output:

```text
Not a teenager
```

এখানে 13 এবং 19—দুটি boundary-ই অন্তর্ভুক্ত।

## 8. Chained Comparison-এ Equality ও Inequality

শুধু `<` এবং `<=` নয়, `==`, `!=`, `>` ও `>=`-এর মতো comparison operator-ও chain করা যায়।

উদাহরণ:

```python
x = 10

print(5 < x <= 10)
print(5 < x != 8)
```

Output:

```text
True
True
```

প্রথম expression-এর অর্থ:

```python
5 < x and x <= 10
```

দ্বিতীয় expression-এর অর্থ:

```python
5 < x and x != 8
```

এখানে দুটি comparison-ই True।

তবে জটিল comparison chain না লিখে প্রয়োজন হলে আলাদা condition ব্যবহার করা ভালো।

## 9. Chained Comparison-এর গুরুত্বপূর্ণ নিয়ম

Chained Comparison শুধু পাশাপাশি থাকা comparison operator-কে একত্র করে। এটি সব ধরনের operator-এর জন্য ব্যবহার করা যায় না।

উদাহরণ:

```python
a = 10
b = 20
c = 30

print(a < b < c)
```

Output:

```text
True
```

কিন্তু নিচের expression-টি:

```python
a < b and b < c
```

আলাদা করে দুটি comparison এবং `and` ব্যবহার করেছে।

দুটি expression-এর result এখানে একই।

**গুরুত্বপূর্ণ:** Chained Comparison-এর মাঝের expression সাধারণত একবারই evaluate হয়। তাই এটি সব ক্ষেত্রে সরাসরি `and`-যুক্ত expression-এর মতো আচরণ করে না, বিশেষত মাঝের অংশে function call থাকলে।

উদাহরণ:

```python
def get_number():
    print("Function called")
    return 10

print(5 < get_number() < 20)
```

Output:

```text
Function called
True
```

এখানে `get_number()` একবারই call হয়েছে।

## 10. Common Mistakes

### Mistake 1: Boundary operator ভুল ব্যবহার করা

```python
age = 18

print(18 < age < 60)
```

Output:

```text
False
```

কারণ `18 < 18` False।

যদি 18 অন্তর্ভুক্ত করতে চাও:

```python
print(18 <= age < 60)
```

Output:

```text
True
```

### Mistake 2: Range-এর order ভুল করা

ভুল:

```python
10 > x < 20
```

এটি Python-এ valid, কিন্তু এর অর্থ হলো `10 > x` এবং `x < 20`। এটি `10` থেকে `20`-এর মধ্যে `x` আছে কি না, তা পরীক্ষা করে না।

সঠিক:

```python
10 < x < 20
```

### Mistake 3: `and`-এর প্রয়োজনীয়তা ভুলে যাওয়া

ভুল:

```python
if age >= 18 or age < 60:
    print("Eligible")
```

এই condition অধিকাংশ age value-এর জন্য True হবে, তাই এটি সঠিক range check নয়।

সঠিক:

```python
if 18 <= age < 60:
    print("Eligible")
```

### Mistake 4: ভুল data type ব্যবহার করা

```python
age = "25"

print(18 <= age < 60)
```

এটি `TypeError` তৈরি করবে, কারণ Python 3-এ string এবং integer-এর মধ্যে এভাবে numeric comparison করা যায় না।

সঠিক:

```python
age = int("25")

print(18 <= age < 60)
```

Output:

```text
True
```

## 11. Practice Exercises

প্রতিটি প্রশ্নের output নিজে predict করো।

### Question 1

```python
x = 15

print(10 < x < 20)
```

### Question 2

```python
x = 10

print(10 < x <= 20)
```

### Question 3

```python
marks = 40

if 40 <= marks <= 100:
    print("Valid")
else:
    print("Invalid")
```

### Question 4

```python
age = 60

print(18 <= age < 60)
```

### Question 5

```python
x = 25

print(10 < x < 20)
print(10 < x <= 25)
```

### Question 6

```python
x = 8

if 5 < x <= 10:
    print("Inside range")
else:
    print("Outside range")
```

### Question 7

```python
x = 10

print(5 < x != 10)
```

### Question 8

```python
marks = 75

if 80 <= marks <= 100:
    print("A")
elif 70 <= marks < 80:
    print("B")
else:
    print("Other")
```

## 12. Answer Key

### Answer 1

```text
True
```

কারণ `10 < 15` এবং `15 < 20`—দুটিই True।

### Answer 2

```text
False
```

কারণ `10 < 10` False।

### Answer 3

```text
Valid
```

40 হলো range-এর lower boundary এবং সেটি অন্তর্ভুক্ত।

### Answer 4

```text
False
```

কারণ condition-এ age অবশ্যই 60-এর কম হতে হবে।

### Answer 5

```text
False
True
```

প্রথম expression-এ 25, 20-এর চেয়ে ছোট নয়। দ্বিতীয় expression-এ 25 অন্তর্ভুক্ত।

### Answer 6

```text
Inside range
```

কারণ `5 < 8` এবং `8 <= 10`—দুটিই True।

### Answer 7

```text
False
```

কারণ `x != 10` False।

### Answer 8

```text
B
```

কারণ `75` দ্বিতীয় range-এর মধ্যে পড়ে।

## 13. Quick Revision

- **Chained Comparison:** একাধিক comparison operator পরপর ব্যবহার করা।
- `10 < x < 20` অর্থ `10 < x and x < 20`।
- `<=` ব্যবহার করলে boundary value অন্তর্ভুক্ত হয়।
- `<` ব্যবহার করলে boundary value অন্তর্ভুক্ত হয় না।
- Numeric range পরীক্ষা করার জন্য Chained Comparison সহজ ও readable।
- Chained Comparison-এর মাঝের expression একবারই evaluate হয়।
- Comparison-এর order ভুল হলে condition-এর অর্থ বদলে যেতে পারে।
- Range check করার সময় `and` ও `or` সঠিকভাবে ব্যবহার করতে হবে।

## 14. Self-Assessment Checklist

- [ ] Chained Comparison কী, তা বুঝি।
- [ ] `10 < x < 20`-এর অর্থ ব্যাখ্যা করতে পারি।
- [ ] Inclusive ও exclusive range-এর পার্থক্য বুঝি।
- [ ] বয়স ও marks-এর range পরীক্ষা করতে পারি।
- [ ] Chained Comparison এবং `and`-এর পার্থক্য বুঝি।
- [ ] ভুল boundary ও operator শনাক্ত করতে পারি।
- [ ] Chained Comparison-এর output predict করতে পারি।

**পরবর্তী টপিক:** `22_Match_Case_Statement.md`
