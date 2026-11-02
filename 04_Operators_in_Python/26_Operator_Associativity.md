# 26. Operator Associativity in Python

## 1. Operator Associativity কী?

**Operator Associativity** হলো একই precedence level-এর একাধিক operator থাকলে expression-টি কোন দিক থেকে group বা evaluate করা হবে, সেই নিয়ম।

সহজভাবে:

- **Operator Precedence:** কোন operator আগে কাজ করবে?
- **Operator Associativity:** একই precedence-এর operator থাকলে কোন দিক থেকে grouping হবে?

### উদাহরণ

```python
result = 20 - 5 - 3
print(result)
```

**Output:**
```text
12
```

Python এটিকে এভাবে group করে:

```python
(20 - 5) - 3
15 - 3
12
```

এখানে subtraction operator সাধারণত left-to-right associativity অনুসরণ করে।

---

## 2. Types of Operator Associativity

Python-এ associativity বোঝার জন্য প্রধানত তিনটি বিষয় খেয়াল রাখতে হবে:

1. Left-to-right associativity
2. Right-to-left associativity
3. Special cases, যেমন chained comparisons

## 3. Left-to-Right Associativity

**Left-to-right associativity** মানে একই precedence-এর operator থাকলে expression বাম দিক থেকে group করা হয়।

### Example 1: Subtraction

```python
print(20 - 5 - 3)
```

**Output:**
```text
12
```

Grouping:

```python
(20 - 5) - 3
```

### Example 2: Division

```python
print(100 / 10 / 2)
```

**Output:**
```text
5.0
```

Grouping:

```python
(100 / 10) / 2
10.0 / 2
5.0
```

### Example 3: Floor Division

```python
print(100 // 10 // 2)
```

**Output:**
```text
5
```

Grouping:

```python
(100 // 10) // 2
```

### Example 4: Modulo

```python
print(17 % 5 % 3)
```

**Output:**
```text
2
```

Grouping:

```python
(17 % 5) % 3
2 % 3
2
```

### গুরুত্বপূর্ণ কথা

একই precedence-এর arithmetic operator-এর ক্ষেত্রে সাধারণ grouping বাম দিক থেকে হতে পারে। তবে ভিন্ন precedence-এর operator থাকলে আগে precedence-এর নিয়ম দেখতে হবে।

---

## 4. Right-to-Left Associativity

**Right-to-left associativity** মানে expression ডান দিক থেকে group করা হয়।

Python-এর exponentiation operator `**` এই নিয়ম অনুসরণ করে।

### Example 1: Exponentiation

```python
print(2 ** 3 ** 2)
```

**Output:**
```text
512
```

Python এটিকে এভাবে group করে:

```python
2 ** (3 ** 2)
2 ** 9
512
```

এটিকে `(2 ** 3) ** 2` হিসেবে হিসাব করা হয় না।

কারণ:

```python
(2 ** 3) ** 2
8 ** 2
64
```

অর্থাৎ, parentheses না থাকলে `2 ** 3 ** 2`-এর output হলো `512`, `64` নয়।

### Example 2: Nested Exponentiation

```python
print(3 ** 2 ** 2)
```

**Output:**
```text
81
```

Grouping:

```python
3 ** (2 ** 2)
3 ** 4
81
```

### মনে রাখার নিয়ম

`**` operator-এর ক্ষেত্রে:

**ডান দিক থেকে grouping করতে হবে।**

---

## 5. Unary Operators এবং Exponentiation-এর বিশেষ নিয়ম

Python-এ unary minus `-` এবং exponentiation `**` একসঙ্গে থাকলে সতর্ক থাকতে হবে।

### Example 1

```python
print(-2 ** 2)
```

**Output:**
```text
-4
```

কারণ Python এটিকে এভাবে ব্যাখ্যা করে:

```python
-(2 ** 2)
-4
```

এখানে exponentiation আগে কাজ করে।

### Example 2

```python
print((-2) ** 2)
```

**Output:**
```text
4
```

এখানে parentheses-এর কারণে `-2` পুরো সংখ্যাটিকে base হিসেবে নেওয়া হয়েছে।

```python
(-2) * (-2)
4
```

### Example 3

```python
print(2 ** -2)
```

**Output:**
```text
0.25
```

কারণ:

```python
2 ** (-2)
1 / (2 ** 2)
0.25
```

এটি Python-এর একটি গুরুত্বপূর্ণ নিয়ম: exponentiation-এর ডান পাশে unary expression থাকতে পারে।

---

## 6. Conditional Expression-এর Associativity

Python-এর conditional expression হলো:

```python
value_if_true if condition else value_if_false
```

Nested conditional expression সাধারণত right-to-left grouping অনুসরণ করে।

### Example

```python
x = 5

result = "A" if x > 10 else "B" if x > 3 else "C"

print(result)
```

**Output:**
```text
B
```

এটি এভাবে বোঝা যায়:

```python
"A" if x > 10 else ("B" if x > 3 else "C")
```

প্রথম condition `x > 10` মিথ্যা। এরপর `x > 3` সত্য, তাই `"B"` পাওয়া যায়।

**পরামর্শ:** Nested conditional expression জটিল হলে parentheses ব্যবহার করো অথবা `if-elif-else` statement লেখো।

---

## 7. Logical Operators-এর Evaluation Order

Python-এ `and` এবং `or` একই ধরনের operator-এর ধারাবাহিক expression-এ বাম দিক থেকে evaluation করে এবং প্রয়োজন হলে short-circuit করে।

### Example 1: `and`

```python
print(False and True and True)
```

**Output:**
```text
False
```

প্রথম operand `False` হওয়ায় পরের operand-গুলো evaluate করার প্রয়োজন হয় না।

### Example 2: `or`

```python
print(True or False or False)
```

**Output:**
```text
True
```

প্রথম operand `True` হওয়ায় বাকি operand-গুলো evaluate করার প্রয়োজন হয় না।

### Function দিয়ে বোঝা

```python
def check():
    print("Function called")
    return True

print(False and check())
```

**Output:**
```text
False
```

এখানে `check()` call করা হয়নি। কারণ `False and ...`-এর ফলাফল আগেই `False` নিশ্চিত।

মনে রাখবে, logical operators সব সময় শুধু `True` বা `False` return করে না; তারা operand-এর actual value-ও return করতে পারে।

---

## 8. Comparison Operators-এর Special Case

Comparison operators-কে সাধারণ arithmetic operator-এর মতো সরল left-to-right grouping হিসেবে বোঝা ঠিক নয়। Python-এ **chained comparisons** নামে বিশেষ নিয়ম রয়েছে।

### Example

```python
x = 5

print(1 < x < 10)
```

**Output:**
```text
True
```

এটি প্রায় এভাবে কাজ করে:

```python
1 < x and x < 10
```

অর্থাৎ, দুটি comparison-ই সত্য হতে হবে।

আরেকটি উদাহরণ:

```python
print(1 < 5 < 3)
```

**Output:**
```text
False
```

কারণ `1 < 5` সত্য হলেও `5 < 3` মিথ্যা।

সুতরাং chained comparison-কে সাধারণ associativity-এর নিয়মের সঙ্গে গুলিয়ে ফেলবে না।

---

## 9. Associativity বনাম Precedence

| বিষয় | Operator Precedence | Operator Associativity |
|---|---|---|
| অর্থ | কোন operator আগে কাজ করবে | একই precedence হলে কীভাবে group হবে |
| মূল প্রশ্ন | Which operator first? | Which direction? |
| উদাহরণ | `2 + 3 * 4` | `20 - 5 - 3` |
| ফলাফল | `14` | `12` |

### Example: Precedence আগে, Associativity পরে

```python
print(10 - 2 * 3)
```

**Output:**
```text
4
```

এখানে multiplication-এর precedence বেশি, তাই আগে `2 * 3` হয়।

```python
10 - (2 * 3)
10 - 6
4
```

অন্যদিকে:

```python
print(20 - 5 - 3)
```

**Output:**
```text
12
```

এখানে subtraction operator একই precedence-এর, তাই left-to-right grouping হয়।

---

## 10. Parentheses দিয়ে Grouping নিয়ন্ত্রণ

Parentheses `()` ব্যবহার করলে expression-এর grouping স্পষ্ট করা যায়।

### Example 1

```python
print(20 - 5 - 3)
```

**Output:**
```text
12
```

### Example 2

```python
print(20 - (5 - 3))
```

**Output:**
```text
18
```

দুটি expression-এর operator একই হলেও parentheses-এর কারণে grouping আলাদা হয়েছে।

আরেকটি উদাহরণ:

```python
print(2 ** 3 ** 2)
print((2 ** 3) ** 2)
```

**Output:**
```text
512
64
```

**Best Practice:** Expression জটিল হলে parentheses ব্যবহার করো। এতে code পড়া ও বোঝা সহজ হয়।

---

## 11. Common Mistakes

### Mistake 1: সব operator বাম দিক থেকে হিসাব করা

ভুল ধারণা:

```python
2 ** 3 ** 2
```

এটিকে `(2 ** 3) ** 2` ভাবা।

সঠিক output:

```text
512
```

কারণ `**` right-to-left grouping অনুসরণ করে।

### Mistake 2: Unary minus-কে সব সময় base-এর অংশ ধরা

```python
print(-3 ** 2)
```

Output:
```text
-9
```

কিন্তু:

```python
print((-3) ** 2)
```

Output:
```text
9
```

### Mistake 3: Precedence এবং associativity গুলিয়ে ফেলা

`10 - 2 * 3`-এ multiplication আগে হবে precedence-এর কারণে; subtraction-এর associativity-এর কারণে নয়।

### Mistake 4: Parentheses উপেক্ষা করা

```python
print(20 - (5 - 3))
```

Output:
```text
18
```

Parentheses থাকলে grouping পরিবর্তিত হয়।

### Mistake 5: Chained comparison-কে সাধারণ comparison-এর মতো ধরা

```python
print(1 < 5 < 10)
```

Output:
```text
True
```

এটি Python-এর chained comparison syntax।

---

## 12. Practice Exercises

প্রথমে নিজে output অনুমান করো। তারপর নিচের answer key মিলিয়ে দেখো।

### Exercise 1

```python
print(30 - 10 - 5)
```

### Exercise 2

```python
print(64 / 4 / 2)
```

### Exercise 3

```python
print(2 ** 2 ** 3)
```

### Exercise 4

```python
print(-4 ** 2)
```

### Exercise 5

```python
print((-4) ** 2)
```

### Exercise 6

```python
print(20 - (10 - 4))
```

### Exercise 7

```python
print(1 < 3 < 5)
```

### Exercise 8

```python
print(False or True or False)
```

### Answer Key

| Exercise | Output | কারণ |
|---|---|---|
| 1 | `15` | `(30 - 10) - 5` |
| 2 | `8.0` | `(64 / 4) / 2` |
| 3 | `256` | `2 ** (2 ** 3)` |
| 4 | `-16` | `-(4 ** 2)` |
| 5 | `16` | `(-4) ** 2` |
| 6 | `14` | `20 - (10 - 4)` |
| 7 | `True` | দুটি comparison-ই সত্য |
| 8 | `True` | প্রথম `False`-এর পর `True` পাওয়া যায় |

---

## 13. Quick Revision

- **Associativity:** একই precedence-এর operator কীভাবে group হবে, তার নিয়ম।
- **Left-to-right:** সাধারণ arithmetic operator যেমন `-`, `/`, `//` এবং `%` একই precedence-এ থাকলে বাম দিক থেকে grouping হয়।
- **Right-to-left:** `**` operator ডান দিক থেকে group হয়।
- **Unary minus:** `-2 ** 2`-এর ফল `-4`, কিন্তু `(-2) ** 2`-এর ফল `4`।
- **Logical operators:** `and` ও `or` short-circuit evaluation করতে পারে।
- **Chained comparisons:** `1 < x < 10`-এর মতো expression-এর বিশেষ নিয়ম আছে।
- **Parentheses:** Expression-এর grouping স্পষ্ট করে এবং সাধারণত পড়তে সহজ করে।

## 14. Self-Assessment Checklist

- [ ] Precedence ও associativity-এর পার্থক্য বুঝতে পারি।
- [ ] Left-to-right grouping করতে পারি।
- [ ] Exponentiation-এর right-to-left grouping বুঝি।
- [ ] Unary minus ও exponentiation-এর interaction বুঝি।
- [ ] Chained comparison চিনতে পারি।
- [ ] Parentheses দিয়ে grouping পরিবর্তন করতে পারি।
- [ ] Code execute করার আগে output অনুমান করতে পারি।

পরের topic: **27. Using Parentheses in Expressions**