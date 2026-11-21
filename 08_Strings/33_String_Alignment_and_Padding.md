
# 33. String Alignment and Padding in Python

## 1. Introduction to String Alignment and Padding

Python-এ String-এর text নির্দিষ্ট width-এর মধ্যে সুন্দরভাবে সাজানো বা position ঠিক করার জন্য **String Alignment and Padding** ব্যবহার করা হয়।

Padding হলো কোনো String-এর আগে বা পরে অতিরিক্ত character যোগ করে নির্দিষ্ট width তৈরি করা।

Python-এ String Alignment এবং Padding-এর জন্য প্রধানত চারটি method রয়েছে:

1. `center()`
2. `ljust()`
3. `rjust()`
4. `zfill()`

উদাহরণ:

```python
name = "Masum"

print(name.center(11))
print(name.ljust(11))
print(name.rjust(11))
```

**Output:**

```text
   Masum   
Masum      
      Masum
```

এখানে প্রতিটি String-এর মোট width হলো `11`।

---

## 2. center() Method

`center()` method কোনো String-কে নির্দিষ্ট width-এর মধ্যে মাঝখানে রাখে।

### Syntax

```python
string.center(width, fillchar)
```

- `width`: String-এর মোট width।
- `fillchar`: অতিরিক্ত জায়গায় কোন character বসবে। এটি optional।
- Default padding character হলো space (`" "`)।

### Example 1: Default Padding

```python
name = "Python"

result = name.center(12)

print(result)
```

**Output:**

```text
   Python   
```

**ব্যাখ্যা:**

- Original String-এর length হলো `6`।
- নির্ধারিত width হলো `12`।
- অতিরিক্ত `6`টি space যোগ হয়েছে।
- দুই পাশে `3`টি করে space বসেছে।

### Example 2: Custom Padding

```python
name = "Python"

result = name.center(12, "*")

print(result)
```

**Output:**

```text
***Python***
```

এখানে space-এর পরিবর্তে `*` ব্যবহার করা হয়েছে।

### Example 3: Odd Padding

```python
text = "Hi"

print(text.center(7, "-"))
```

**Output:**

```text
---Hi--
```

এখানে মোট `5`টি padding character প্রয়োজন।

- বাম পাশে `3`টি।
- ডান পাশে `2`টি।

অর্থাৎ, অতিরিক্ত একটি character বাম পাশে যোগ হয়।

---

## 3. ljust() Method

`ljust()` method কোনো String-কে বাম পাশে রাখে এবং প্রয়োজনীয় padding ডান পাশে যোগ করে।

### Syntax

```python
string.ljust(width, fillchar)
```

### Example 1: Default Padding

```python
name = "Python"

result = name.ljust(12)

print(result)
```

**Output:**

```text
Python      
```

এখানে String-এর ডান পাশে space যোগ হয়েছে।

### Example 2: Custom Padding

```python
name = "Python"

result = name.ljust(12, "-")

print(result)
```

**Output:**

```text
Python------
```

এখানে ডান পাশে `6`টি `-` যোগ হয়েছে।

---

## 4. rjust() Method

`rjust()` method কোনো String-কে ডান পাশে রাখে এবং প্রয়োজনীয় padding বাম পাশে যোগ করে।

### Syntax

```python
string.rjust(width, fillchar)
```

### Example 1: Default Padding

```python
name = "Python"

result = name.rjust(12)

print(result)
```

**Output:**

```text
      Python
```

এখানে String-এর বাম পাশে space যোগ হয়েছে।

### Example 2: Custom Padding

```python
name = "Python"

result = name.rjust(12, "-")

print(result)
```

**Output:**

```text
------Python
```

এখানে বাম পাশে `6`টি `-` যোগ হয়েছে।

---

## 5. zfill() Method

`zfill()` method কোনো String-এর বাম পাশে zero (`0`) যোগ করে নির্দিষ্ট width তৈরি করে।

এটি সাধারণত Number-কে নির্দিষ্ট digit-এর format-এ দেখানোর জন্য ব্যবহার করা হয়।

### Syntax

```python
string.zfill(width)
```

এখানে `width` হলো String-এর কাঙ্ক্ষিত মোট length।

### Example 1: Basic Usage

```python
number = "42"

result = number.zfill(5)

print(result)
```

**Output:**

```text
00042
```

এখানে String-এর length `2` এবং target width `5`।

তাই বাম পাশে `3`টি zero যোগ হয়েছে।

### Example 2: Different Numbers

```python
print("7".zfill(4))
print("25".zfill(5))
print("123".zfill(6))
```

**Output:**

```text
0007
00025
000123
```

### Example 3: Negative Number

```python
number = "-42"

print(number.zfill(5))
```

**Output:**

```text
-0042
```

**ব্যাখ্যা:**

Negative sign (`-`) শুরুতেই থাকে। Zero-গুলো sign-এর পরে যোগ হয়।

### Example 4: Positive Sign

```python
number = "+42"

print(number.zfill(5))
```

**Output:**

```text
+0042
```

এখানেও zero-গুলো `+` sign-এর পরে যোগ হয়েছে।

---

## 6. Comparing String Alignment Methods

নিচের উদাহরণটি লক্ষ্য করো:

```python
text = "Python"

print(text.center(10, "*"))
print(text.ljust(10, "*"))
print(text.rjust(10, "*"))
print(text.zfill(10))
```

**Output:**

```text
**Python**
Python****
****Python
0000Python
```

| Method | কাজ |
|---|---|
| `center()` | মাঝখানে রাখে |
| `ljust()` | বাম পাশে রাখে |
| `rjust()` | ডান পাশে রাখে |
| `zfill()` | বাম পাশে zero যোগ করে |

---

## 7. What Happens When Width Is Smaller?

যদি নির্ধারিত width String-এর বর্তমান length-এর সমান বা ছোট হয়, তাহলে কোনো padding যোগ হয় না।

### Example

```python
text = "Python"

print(text.center(4))
print(text.ljust(6))
print(text.rjust(3))
print(text.zfill(2))
```

**Output:**

```text
Python
Python
Python
Python
```

কারণ String-এর length ইতোমধ্যে `6`।

তাই কোনো method-ই String-এর character বাদ দেয় না।

---

## 8. Using Alignment Methods in Practical Examples

### Example 1: Creating a Heading

```python
heading = "STUDENT INFORMATION"

print(heading.center(30, "="))
```

**Output:**

```text
=====STUDENT INFORMATION======
```

এখানে heading-টি মাঝখানে দেখানো হয়েছে।

### Example 2: Creating a Simple Table

```python
print("Name".ljust(15), "Age".rjust(5))
print("Masum".ljust(15), "22".rjust(5))
print("Rahim".ljust(15), "21".rjust(5))
print("Karim".ljust(15), "23".rjust(5))
```

**Output:**

```text
Name              Age
Masum              22
Rahim              21
Karim              23
```

এখানে:

- `ljust()` Name-গুলোকে বাম পাশে সাজিয়েছে।
- `rjust()` Age-গুলোকে ডান পাশে সাজিয়েছে।

### Example 3: Formatting Student ID

```python
student_id = "123"

formatted_id = student_id.zfill(6)

print(formatted_id)
```

**Output:**

```text
000123
```

এভাবে Student ID-কে নির্দিষ্ট width-এ দেখানো যায়।

---

## 9. Important Rules

1. `center()` String-কে মাঝখানে রাখে।
2. `ljust()` String-কে বাম পাশে রাখে।
3. `rjust()` String-কে ডান পাশে রাখে।
4. `zfill()` String-এর বাম পাশে zero যোগ করে।
5. `fillchar` ব্যবহার করলে অবশ্যই একটি character দিতে হবে।
6. `fillchar` না দিলে default হিসেবে space ব্যবহার হয়।
7. `width` হলো String-এর মোট কাঙ্ক্ষিত length।
8. Width ছোট বা সমান হলে কোনো padding যোগ হয় না।
9. এই method-গুলো original String পরিবর্তন করে না; নতুন String return করে।
10. `zfill()` negative বা positive sign থাকলে sign-এর পরে zero যোগ করে।

---

## 10. Common Mistakes

### Mistake 1: Using More Than One Character as fillchar

```python
name = "Python"

print(name.center(12, "ab"))
```

**Output:**

```text
TypeError: The fill character must be exactly one character long
```

**কারণ:** `fillchar` হিসেবে একাধিক character দেওয়া যাবে না।

**Correct Code:**

```python
print(name.center(12, "*"))
```

### Mistake 2: Expecting Original String to Change

```python
name = "Python"

name.center(12, "*")

print(name)
```

**Output:**

```text
Python
```

**কারণ:** String method নতুন String return করে। Original String পরিবর্তন হয় না।

**Correct Code:**

```python
name = "Python"

name = name.center(12, "*")

print(name)
```

**Output:**

```text
***Python***
```

### Mistake 3: Confusing ljust() and rjust()

```python
text = "Hello"

print(text.ljust(10, "-"))
print(text.rjust(10, "-"))
```

**Output:**

```text
Hello-----
-----Hello
```

মনে রাখবে:

- `ljust()` → Padding ডান পাশে।
- `rjust()` → Padding বাম পাশে।

---

## 11. Practice Exercises

### Exercise 1: Center Alignment

একটি String-কে `20` width-এর মধ্যে মাঝখানে রাখো এবং `*` দিয়ে padding করো।

**Expected Output:**

```text
*******Python*******
```

### Exercise 2: Left Alignment

`"Bangladesh"` String-কে `15` width-এর মধ্যে বাম পাশে রাখো এবং `-` দিয়ে padding করো।

**Expected Output:**

```text
Bangladesh-----
```

### Exercise 3: Right Alignment

`"Python"` String-কে `12` width-এর মধ্যে ডান পাশে রাখো।

**Expected Output:**

```text
      Python
```

### Exercise 4: Zero Padding

`"456"` String-কে `7` width-এর মধ্যে zero দিয়ে পূরণ করো।

**Expected Output:**

```text
0000456
```

### Exercise 5: Negative Number Padding

`"-75"` String-কে `6` width-এর মধ্যে zero দিয়ে পূরণ করো।

**Expected Output:**

```text
-00075
```

### Exercise 6: Predict the Output

```python
text = "AI"

print(text.center(6, "-"))
print(text.ljust(6, "*"))
print(text.rjust(6, "+"))
print(text.zfill(6))
```

**Expected Output:**

```text
--AI--
AI****
++++AI
0000AI
```

---

## 12. Chapter Summary

এই topic-এ আমরা Python-এর String Alignment and Padding সম্পর্কে শিখেছি।

| Method | কাজ | Example |
|---|---|---|
| `center()` | মাঝখানে রাখে | `"Hi".center(6)` |
| `ljust()` | বাম পাশে রাখে | `"Hi".ljust(6)` |
| `rjust()` | ডান পাশে রাখে | `"Hi".rjust(6)` |
| `zfill()` | বাম পাশে zero যোগ করে | `"42".zfill(5)` |

**মনে রাখার সহজ উপায়:**

- `center()` = Center
- `ljust()` = Left
- `rjust()` = Right
- `zfill()` = Zero Fill

---

## 13. Self-Assessment Checklist

- [ ] String Alignment কী বুঝতে পেরেছি।
- [ ] `center()` method ব্যবহার করতে পারি।
- [ ] `ljust()` method ব্যবহার করতে পারি।
- [ ] `rjust()` method ব্যবহার করতে পারি।
- [ ] `zfill()` method ব্যবহার করতে পারি।
- [ ] Custom padding character ব্যবহার করতে পারি।
- [ ] Negative number-এর ক্ষেত্রে `zfill()` বুঝতে পেরেছি।
- [ ] Alignment method-গুলোর পার্থক্য বুঝতে পেরেছি।

---

## 14. Next Topic

পরবর্তী topic:

**34. Escape Sequences in Python Strings**

এখানে আমরা `\n`, `\t`, `\\`, `\"` এবং অন্যান্য Escape Sequence সম্পর্কে শিখব।
