# 45. Printing Alphabet Patterns

## 1. Introduction

Alphabet pattern হলো ইংরেজি অক্ষর ব্যবহার করে নির্দিষ্ট নিয়মে সাজানো output। Python-এর `for` loop, nested loop এবং `chr()` ও `ord()` function ব্যবহার করে এসব pattern তৈরি করা যায়।

উদাহরণ:

```text
A
A B
A B C
A B C D
```

এই pattern তৈরিতে তিনটি বিষয় গুরুত্বপূর্ণ:

- **Outer loop:** কতটি row হবে তা নিয়ন্ত্রণ করে।
- **Inner loop:** প্রতিটি row-তে কতটি letter print হবে তা নিয়ন্ত্রণ করে।
- **`chr()` ও `ord()`:** অক্ষর এবং তার Unicode code point-এর মধ্যে রূপান্তর করতে সাহায্য করে।

## 2. Understanding `ord()` and `chr()`

Alphabet pattern তৈরির আগে `ord()` এবং `chr()` বুঝতে হবে।

### `ord()` Function

`ord()` একটি character-এর Unicode code point ফেরত দেয়।

```python
print(ord("A"))
print(ord("B"))
print(ord("a"))
```

Output:

```text
65
66
97
```

ইংরেজি uppercase অক্ষরগুলোর code point ধারাবাহিকভাবে বাড়ে:

- A = 65
- B = 66
- C = 67
- D = 68

### `chr()` Function

`chr()` একটি Unicode code point থেকে character তৈরি করে।

```python
print(chr(65))
print(chr(66))
print(chr(67))
```

Output:

```text
A
B
C
```

### Converting a Number to an Alphabet

```python
number = 3
letter = chr(ord("A") + number - 1)

print(letter)
```

Output:

```text
C
```

ব্যাখ্যা:

1. `ord("A")`-এর মান 65।
2. `65 + 3 - 1 = 67`।
3. `chr(67)` হলো `C`।

এই formula দিয়ে A থেকে Z পর্যন্ত uppercase alphabet তৈরি করা যায়।

## 3. Pattern 1: Printing the Alphabet Sequence

প্রথমে A থেকে Z পর্যন্ত সব uppercase alphabet print করি।

### Code

```python
for code in range(ord("A"), ord("Z") + 1):
    print(chr(code), end=" ")

print()
```

### Output

```text
A B C D E F G H I J K L M N O P Q R S T U V W X Y Z
```

### Explanation

- `ord("A")` শুরু করার code point দেয়।
- `ord("Z") + 1` ব্যবহার করা হয়েছে, কারণ `range()`-এর stop value অন্তর্ভুক্ত হয় না।
- `chr(code)` প্রতিটি code point-কে character-এ রূপান্তর করে।
- `end=" "` সব অক্ষর একই লাইনে রাখে।

## 4. Pattern 2: Increasing Alphabet Triangle

এই pattern-এ প্রতিটি row-তে A থেকে শুরু করে পরবর্তী অক্ষরগুলো print হবে।

### Code

```python
for row in range(1, 6):
    for code in range(ord("A"), ord("A") + row):
        print(chr(code), end=" ")
    print()
```

### Output

```text
A
A B
A B C
A B C D
A B C D E
```

### Explanation

Outer loop `row`-এর মান ১ থেকে ৫ পর্যন্ত নেয়।

Inner loop-এর range:

```python
range(ord("A"), ord("A") + row)
```

যখন `row = 3`, তখন A, B ও C print হয়।

প্রতিটি row-তে একটি করে নতুন alphabet যোগ হয়।

## 5. Pattern 3: Repeating the Same Alphabet in Each Row

এখানে প্রতিটি row-তে একই alphabet বারবার print হবে।

### Code

```python
for row in range(1, 6):
    letter = chr(ord("A") + row - 1)

    for column in range(row):
        print(letter, end=" ")

    print()
```

### Output

```text
A
B B
C C C
D D D D
E E E E E
```

### Explanation

প্রথমে বর্তমান row-এর alphabet নির্ধারণ করা হয়েছে:

```python
letter = chr(ord("A") + row - 1)
```

এরপর inner loop সেই letter-টি `row` সংখ্যক বার print করে।

উদাহরণস্বরূপ, `row = 4` হলে letter হবে D এবং এটি চারবার print হবে।

## 6. Pattern 4: Increasing Alphabet Sequence in Each Row

এই pattern-এ প্রতিটি row-তে আগের অক্ষর থেকে শুরু করে অক্ষরের সংখ্যা বাড়বে।

### Code

```python
for row in range(1, 6):
    for column in range(row):
        letter = chr(ord("A") + column)
        print(letter, end=" ")
    print()
```

### Output

```text
A
A B
A B C
A B C D
A B C D E
```

### Explanation

এখানে `column`-এর মান অনুযায়ী alphabet নির্ধারণ করা হয়েছে।

- Column 0 → A
- Column 1 → B
- Column 2 → C
- Column 3 → D

প্রতিটি row-তে inner loop-এর iteration সংখ্যা বাড়ে।

**Note:** এই pattern এবং Pattern 2-এর output একই। তবে এখানে alphabet নির্ধারণ করা হচ্ছে `column` দিয়ে; Pattern 2-তে range-এর মাধ্যমে সরাসরি অক্ষরের code point নিয়ন্ত্রণ করা হয়েছে।

## 7. Pattern 5: Repeating the Row Alphabet Without Spaces

এবার একই row-based alphabet print করব, তবে letter-গুলোর মধ্যে space থাকবে না।

### Code

```python
for row in range(1, 6):
    letter = chr(ord("A") + row - 1)

    for column in range(row):
        print(letter, end="")

    print()
```

### Output

```text
A
BB
CCC
DDDD
EEEEE
```

### Explanation

এখানে `end=""` ব্যবহার করা হয়েছে। তাই একই row-এর letter-গুলোর মধ্যে কোনো space থাকবে না।

- `end=" "` → letter-গুলোর মধ্যে space থাকবে।
- `end=""` → letter-গুলো পাশাপাশি থাকবে।

## 8. Pattern 6: Decreasing Alphabet Triangle

এই pattern-এ প্রতিটি নতুন row-তে alphabet-এর সংখ্যা কমবে।

### Code

```python
for row in range(5, 0, -1):
    for column in range(row):
        letter = chr(ord("A") + column)
        print(letter, end=" ")
    print()
```

### Output

```text
A B C D E
A B C D
A B C
A B
A
```

### Explanation

Outer loop ৫ থেকে ১ পর্যন্ত কমে।

প্রতিটি row-তে inner loop `row` সংখ্যক letter print করে। তাই প্রতিটি পরবর্তী row-তে একটি করে letter কমে।

## 9. Pattern 7: Decreasing Alphabet Sequence

এবার প্রতিটি row-তে সেই row-এর শেষ alphabet থেকে A পর্যন্ত উল্টোভাবে print হবে।

### Code

```python
for row in range(5, 0, -1):
    for code in range(ord("A") + row - 1, ord("A") - 1, -1):
        print(chr(code), end=" ")
    print()
```

### Output

```text
E D C B A
D C B A
C B A
B A
A
```

### Explanation

Inner loop শুরু হয় বর্তমান row-এর শেষ alphabet থেকে এবং `-1` step দিয়ে পেছনের দিকে যায়।

উদাহরণস্বরূপ, `row = 4` হলে:

- শুরু code point = `ord("A") + 3`, অর্থাৎ D।
- এরপর C, B এবং A print হয়।

## 10. Pattern 8: Continuous Alphabet Triangle

এই pattern-এ প্রতিটি নতুন row আগের row-এর পরবর্তী alphabet দিয়ে শুরু হবে।

### Code

```python
code = ord("A")

for row in range(1, 6):
    for column in range(row):
        print(chr(code), end=" ")
        code += 1
    print()
```

### Output

```text
A
B C
D E F
G H I J
K L M N O
```

### Explanation

- `code = ord("A")` দিয়ে A-এর code point থেকে শুরু করা হয়েছে।
- প্রতিটি character print করার পরে `code += 1` হয়।
- `code` outer loop-এর বাইরে রাখা হয়েছে, তাই পরবর্তী row-তে আগের মান বজায় থাকে।

এটি সংখ্যার Floyd’s Triangle-এর মতো, তবে এখানে সংখ্যা না দিয়ে alphabet print করা হয়েছে।

**গুরুত্বপূর্ণ:** এই উদাহরণটি ছোট pattern-এর জন্য তৈরি। এখানে ২৬টির বেশি অক্ষর দরকার হলে `chr()` পরবর্তী Unicode character-ও দিতে পারে, কিন্তু সেগুলো আর ইংরেজি A–Z alphabet হবে না।

## 11. Pattern 9: Alphabet Pyramid

এবার spaces ব্যবহার করে centered alphabet pyramid তৈরি করব।

### Code

```python
height = 5

for row in range(1, height + 1):
    for space in range(height - row):
        print(" ", end="")

    for column in range(row):
        letter = chr(ord("A") + column)
        print(letter, end=" ")

    print()
```

### Output

```text
    A
   A B
  A B C
 A B C D
A B C D E
```

### Explanation

এখানে দুটি inner loop আছে।

1. প্রথম loop leading spaces print করে।
2. দ্বিতীয় loop A থেকে বর্তমান row-এর শেষ alphabet পর্যন্ত print করে।
3. Row বাড়ার সঙ্গে সঙ্গে spaces কমে এবং alphabet-এর সংখ্যা বাড়ে।

## 12. Pattern 10: Palindromic Alphabet Pyramid

এই pattern-এ alphabet প্রথমে বাড়বে, তারপর কমবে।

### Code

```python
height = 5

for row in range(1, height + 1):
    for space in range(height - row):
        print(" ", end="")

    for column in range(row):
        print(chr(ord("A") + column), end="")

    for column in range(row - 2, -1, -1):
        print(chr(ord("A") + column), end="")

    print()
```

### Output

```text
    A
   ABA
  ABCBA
 ABCDCBA
ABCDEDCBA
```

### Explanation

প্রতিটি row-তে তিনটি কাজ করা হয়:

1. Leading spaces print করা।
2. A থেকে বর্তমান row-এর শেষ alphabet পর্যন্ত print করা।
3. শেষ alphabet-এর ঠিক আগের alphabet থেকে A পর্যন্ত উল্টোভাবে print করা।

উদাহরণস্বরূপ, `row = 4` হলে:

- Increasing part: `ABCD`
- Decreasing part: `CBA`
- Combined: `ABCDCBA`

এখানে দ্বিতীয় loop `row - 2` থেকে শুরু হয়েছে, যাতে D দুবার print না হয়।

## 13. Pattern 11: Alphabet Square

এই pattern-এ প্রতিটি row-তে A থেকে শুরু করে একই sequence print হবে।

### Code

```python
size = 5

for row in range(size):
    for column in range(size):
        print(chr(ord("A") + column), end=" ")
    print()
```

### Output

```text
A B C D E
A B C D E
A B C D E
A B C D E
A B C D E
```

### Explanation

- Outer loop পাঁচটি row তৈরি করে।
- Inner loop প্রতিটি row-তে A থেকে E পর্যন্ত print করে।
- `column` প্রতিটি iteration-এ বাড়ে, তাই alphabet-ও পরিবর্তিত হয়।

## 14. Pattern 12: Alphabet Sequence Starting from Each Row

এই pattern-এ প্রতিটি row তার নিজস্ব alphabet দিয়ে শুরু হবে এবং সামনে এগোবে।

### Code

```python
size = 5

for row in range(size):
    for column in range(size):
        letter = chr(ord("A") + row + column)
        print(letter, end=" ")
    print()
```

### Output

```text
A B C D E
B C D E F
C D E F G
D E F G H
E F G H I
```

### Explanation

এখানে alphabet-এর code point নির্ধারণ করা হয়েছে:

```python
ord("A") + row + column
```

- Row 0, Column 0 → A
- Row 0, Column 1 → B
- Row 1, Column 0 → B
- Row 2, Column 0 → C

তাই প্রতিটি নতুন row আগের row-এর তুলনায় পরের alphabet দিয়ে শুরু হয়।

## 15. Dry Run of an Alphabet Triangle

Code:

```python
for row in range(1, 4):
    for column in range(row):
        letter = chr(ord("A") + column)
        print(letter, end=" ")
    print()
```

### Dry Run Table

| Row | Column values | Printed letters |
|---:|---|---|
| 1 | 0 | A |
| 2 | 0, 1 | A B |
| 3 | 0, 1, 2 | A B C |

### Output

```text
A
A B
A B C
```

এখানে `column` প্রতিবার ০ থেকে শুরু হয়। তাই প্রতিটি row-তে alphabet আবার A থেকে শুরু হচ্ছে।

## 16. Common Mistakes

### Mistake 1: Forgetting `ord()` or `chr()`

```python
print("A" + 1)
```

এতে `TypeError` হবে, কারণ string-এর সঙ্গে integer সরাসরি যোগ করা যায় না।

সঠিক পদ্ধতি:

```python
print(chr(ord("A") + 1))
```

Output:

```text
B
```

### Mistake 2: Incorrect Stop Value

```python
range(ord("A"), ord("A") + row)
```

এই range-এ A থেকে বর্তমান row অনুযায়ী প্রয়োজনীয় সংখ্যক alphabet পাওয়া যায়। Stop value অন্তর্ভুক্ত হয় না—এটি মনে রাখতে হবে।

### Mistake 3: Initializing the Counter Inside the Outer Loop

Continuous alphabet pattern-এ `code = ord("A")` outer loop-এর ভেতরে রাখলে প্রতিটি row-তে আবার A থেকে শুরু হবে।

### Mistake 4: Forgetting `end`

`end=" "` ব্যবহার না করলে প্রতিটি alphabet আলাদা লাইনে চলে যাবে।

### Mistake 5: Wrong Reverse Range

```python
range(3, -1, -1)
```

এটি ৩, ২, ১, ০ দেয়। Stop value `-1` অন্তর্ভুক্ত হয় না।

### Mistake 6: Going Beyond Z

`chr()` যেকোনো valid Unicode code point-এর character দিতে পারে। তাই code point বাড়াতে থাকলে Z-এর পরে ইংরেজি alphabet না-ও পাওয়া যেতে পারে।

A–Z-এর মধ্যেই রাখতে চাইলে সর্বোচ্চ ২৬টি uppercase alphabet ব্যবহার করো।

## 17. Practice Exercises

### Exercise 1: Increasing Alphabet Triangle

```text
A
A B
A B C
A B C D
```

### Exercise 2: Repeating Row Alphabet

```text
A
B B
C C C
D D D D
```

### Exercise 3: Decreasing Alphabet Triangle

```text
A B C D
A B C
A B
A
```

### Exercise 4: Continuous Alphabet Triangle

```text
A
B C
D E F
G H I J
```

### Exercise 5: Alphabet Square

৫ × ৫ alphabet square তৈরি করো।

### Exercise 6: Palindromic Alphabet Pyramid

```text
   A
  ABA
 ABCBA
ABCDCBA
```

### Exercise 7: Find the Output

```python
for row in range(1, 4):
    for column in range(row):
        print(chr(ord("A") + column), end=" ")
    print()
```

### Exercise 8: Explain the Output

```python
code = ord("A")

for row in range(1, 4):
    for column in range(row):
        print(chr(code), end=" ")
        code += 1
    print()
```

## 18. Practice Answer Key

### Answer 1

```python
for row in range(1, 5):
    for column in range(row):
        print(chr(ord("A") + column), end=" ")
    print()
```

### Answer 2

```python
for row in range(1, 5):
    letter = chr(ord("A") + row - 1)

    for column in range(row):
        print(letter, end=" ")
    print()
```

### Answer 3

```python
for row in range(4, 0, -1):
    for column in range(row):
        print(chr(ord("A") + column), end=" ")
    print()
```

### Answer 4

```python
code = ord("A")

for row in range(1, 5):
    for column in range(row):
        print(chr(code), end=" ")
        code += 1
    print()
```

### Answer 5

```python
size = 5

for row in range(size):
    for column in range(size):
        print(chr(ord("A") + column), end=" ")
    print()
```

### Answer 6

```python
height = 4

for row in range(1, height + 1):
    for space in range(height - row):
        print(" ", end="")

    for column in range(row):
        print(chr(ord("A") + column), end="")

    for column in range(row - 2, -1, -1):
        print(chr(ord("A") + column), end="")

    print()
```

### Answer 7

Output:

```text
A
A B
A B C
```

কারণ প্রতিটি row-তে `column` ০ থেকে শুরু হয় এবং বর্তমান row অনুযায়ী বাড়ে।

### Answer 8

Output:

```text
A
B C
D E F
```

কারণ `code` outer loop-এর বাইরে initialize করা হয়েছে এবং প্রতিটি alphabet print করার পর এর মান এক বাড়ছে।

## 19. Chapter Summary

- Alphabet pattern তৈরিতে nested loop ব্যবহার করা যায়।
- `ord()` character-কে Unicode code point-এ রূপান্তর করে।
- `chr()` code point-কে character-এ রূপান্তর করে।
- `row` ও `column` অনুযায়ী alphabet নির্ধারণ করা যায়।
- `end=" "` একই row-তে একাধিক alphabet print করে।
- Counter outer loop-এর বাইরে রাখলে পরবর্তী row-তেও আগের মান বজায় থাকে।
- Spaces ব্যবহার করে pyramid তৈরি করা যায়।
- Increasing ও decreasing loop ব্যবহার করে palindromic pattern তৈরি করা যায়।

## 20. Completion Checklist

- [ ] `ord()` এবং `chr()`-এর ব্যবহার বুঝি।
- [ ] Increasing alphabet triangle তৈরি করতে পারি।
- [ ] Repeating alphabet pattern তৈরি করতে পারি।
- [ ] Decreasing alphabet triangle তৈরি করতে পারি।
- [ ] Continuous alphabet triangle তৈরি করতে পারি।
- [ ] Alphabet square ও pyramid তৈরি করতে পারি।
- [ ] Palindromic alphabet pattern তৈরি করতে পারি।
- [ ] Nested loop-এর dry run করতে পারি।

**Next Topic:** `46_Controlling_Nested_Loops.md`
