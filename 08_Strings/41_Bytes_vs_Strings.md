
# 41. Bytes vs Strings in Python

## 1. Introduction

Python-এ **String (`str`)** এবং **Bytes (`bytes`)** দুটোই data সংরক্ষণের জন্য ব্যবহার করা হয়। কিন্তু এদের কাজ আলাদা।

- **String (`str`):** মানুষের পড়ার উপযোগী text সংরক্ষণ করে।
- **Bytes (`bytes`):** Byte আকারে data সংরক্ষণ করে।

সহজভাবে মনে রাখো:

- `str` = Text
- `bytes` = Byte Data

উদাহরণ:

```python
name = "Masum"
data = b"Masum"

print(name)
print(data)
```

**Output:**

```text
Masum
b'Masum'
```

দেখতে প্রায় একই হলেও এদের data type আলাদা।

---

## 2. What is a String?

String হলো এক বা একাধিক character-এর sequence, যা মানুষের পড়ার উপযোগী text সংরক্ষণ করে।

Python-এ String-এর data type হলো `str`।

উদাহরণ:

```python
name = "Masum"
message = "I am learning Python."
country = "Bangladesh"

print(name)
print(message)
print(country)
```

**Output:**

```text
Masum
I am learning Python.
Bangladesh
```

Data type পরীক্ষা:

```python
text = "Hello"

print(type(text))
```

**Output:**

```text
<class 'str'>
```

**মনে রাখবে:** String সাধারণত text বা মানুষের পড়ার উপযোগী তথ্য নিয়ে কাজ করার জন্য ব্যবহৃত হয়।

---

## 3. What is Bytes?

Bytes হলো 8-bit data-এর একটি sequence। প্রতিটি byte-এর মান 0 থেকে 255 পর্যন্ত হতে পারে।

Python-এ Bytes-এর data type হলো `bytes`।

Bytes তৈরি করার জন্য সাধারণত `b` prefix ব্যবহার করা হয়।

উদাহরণ:

```python
data = b"Hello"

print(data)
print(type(data))
```

**Output:**

```text
b'Hello'
<class 'bytes'>
```

এখানে `b` বোঝায় যে এটি একটি bytes object।

আরেকটি উদাহরণ:

```python
data = bytes([65, 66, 67])

print(data)
```

**Output:**

```text
b'ABC'
```

এখানে:

- `65` = A
- `66` = B
- `67` = C

**মনে রাখবে:** Bytes-এর প্রতিটি element হলো একটি integer, যার range 0 থেকে 255।

---

## 4. Difference Between String and Bytes

String এবং Bytes-এর মধ্যে কিছু গুরুত্বপূর্ণ পার্থক্য রয়েছে।

| String (`str`) | Bytes (`bytes`) |
|---|---|
| Text সংরক্ষণ করে | Byte data সংরক্ষণ করে |
| মানুষের পড়ার উপযোগী | সাধারণত সরাসরি text হিসেবে পড়ার উপযোগী নয় |
| Unicode character ব্যবহার করে | 0–255 range-এর byte সংরক্ষণ করে |
| `"Hello"` | `b"Hello"` |
| `str` data type | `bytes` data type |
| Text processing-এ ব্যবহৃত হয় | File, image, network data ইত্যাদিতে ব্যবহৃত হয় |

উদাহরণ:

```python
text = "Hello"
data = b"Hello"

print(type(text))
print(type(data))
```

**Output:**

```text
<class 'str'>
<class 'bytes'>
```

---

## 5. Creating Bytes Using the `b` Prefix

Python-এ কোনো string-এর আগে `b` লিখলে bytes literal তৈরি হয়।

উদাহরণ:

```python
data = b"Python"

print(data)
print(type(data))
```

**Output:**

```text
b'Python'
<class 'bytes'>
```

তবে `b` prefix ব্যবহার করে সরাসরি non-ASCII character লেখা যায় না।

উদাহরণ:

```python
data = b"বাংলা"
```

**Output:**

```text
SyntaxError
```

কারণ bytes literal-এর মধ্যে সরাসরি non-ASCII character লেখা যায় না।

এর পরিবর্তে `encode()` ব্যবহার করতে হয়।

```python
text = "বাংলা"

data = text.encode("utf-8")

print(data)
```

**Output:**

```text
b'\xe0\xa6\xac\xe0\xa6\xbe\xe0\xa6\x82\xe0\xa6\xb2\xe0\xa6\xbe'
```

---

## 6. Converting String into Bytes

String-কে Bytes-এ convert করার জন্য `encode()` method ব্যবহার করা হয়।

**Syntax:**

```python
string.encode("encoding")
```

উদাহরণ:

```python
text = "Hello"

data = text.encode("utf-8")

print(data)
print(type(data))
```

**Output:**

```text
b'Hello'
<class 'bytes'>
```

এখানে:

- `text` হলো String।
- `encode()` String-কে Bytes-এ convert করেছে।
- `"utf-8"` হলো encoding format।

Bangla text-এর উদাহরণ:

```python
text = "বাংলা"

data = text.encode("utf-8")

print(data)
print(len(data))
```

**Output:**

```text
b'\xe0\xa6\xac\xe0\xa6\xbe\xe0\xa6\x82\xe0\xa6\xb2\xe0\xa6\xbe'
15
```

**মনে রাখবে:** `encode()` ব্যবহার করলে `str` থেকে `bytes` পাওয়া যায়।

---

## 7. Converting Bytes into String

Bytes-কে String-এ convert করার জন্য `decode()` method ব্যবহার করা হয়।

**Syntax:**

```python
bytes_data.decode("encoding")
```

উদাহরণ:

```python
data = b"Hello"

text = data.decode("utf-8")

print(text)
print(type(text))
```

**Output:**

```text
Hello
<class 'str'>
```

এখানে:

- `data` হলো Bytes।
- `decode()` Bytes-কে String-এ convert করেছে।
- `"utf-8"` হলো decoding format।

Bangla text-এর উদাহরণ:

```python
data = "বাংলা".encode("utf-8")

text = data.decode("utf-8")

print(text)
```

**Output:**

```text
বাংলা
```

**মনে রাখবে:** `decode()` ব্যবহার করলে `bytes` থেকে `str` পাওয়া যায়।

---

## 8. Encoding and Decoding Difference

Encoding এবং Decoding একে অপরের বিপরীত কাজ করে।

| Encoding | Decoding |
|---|---|
| String থেকে Bytes তৈরি করে | Bytes থেকে String তৈরি করে |
| `encode()` ব্যবহার হয় | `decode()` ব্যবহার হয় |
| `str` → `bytes` | `bytes` → `str` |

উদাহরণ:

```python
text = "Python"

# Encoding
data = text.encode("utf-8")

# Decoding
result = data.decode("utf-8")

print(data)
print(result)
```

**Output:**

```text
b'Python'
Python
```

মনে রাখার সহজ নিয়ম:

```text
String --encode()--> Bytes

Bytes --decode()--> String
```

---

## 9. Accessing Bytes Elements

Bytes-এর প্রতিটি element একটি integer হিসেবে পাওয়া যায়।

উদাহরণ:

```python
data = b"ABC"

print(data[0])
print(data[1])
print(data[2])
```

**Output:**

```text
65
66
67
```

কারণ:

- `A`-এর byte value = 65
- `B`-এর byte value = 66
- `C`-এর byte value = 67

String-এর ক্ষেত্রে একই কাজ করলে character পাওয়া যায়।

```python
text = "ABC"

print(text[0])
print(text[1])
print(text[2])
```

**Output:**

```text
A
B
C
```

**গুরুত্বপূর্ণ পার্থক্য:**

- String indexing করলে character পাওয়া যায়।
- Bytes indexing করলে integer পাওয়া যায়।

---

## 10. Bytes Slicing

String-এর মতো Bytes-এর ক্ষেত্রেও slicing ব্যবহার করা যায়।

উদাহরণ:

```python
data = b"Python"

print(data[0:3])
print(data[3:6])
```

**Output:**

```text
b'Pyt'
b'hon'
```

এখানে slicing-এর নিয়ম String-এর মতোই।

```python
data = b"Python"

print(data[:2])
print(data[2:])
print(data[::-1])
```

**Output:**

```text
b'Py'
b'thon'
b'nohtyP'
```

---

## 11. Bytes are Immutable

Python-এর `bytes` object immutable। অর্থাৎ Bytes তৈরি করার পরে এর কোনো element সরাসরি পরিবর্তন করা যায় না।

উদাহরণ:

```python
data = b"Hello"

data[0] = 65

print(data)
```

**Output:**

```text
TypeError
```

কারণ Bytes-এর element পরিবর্তন করা যায় না।

তবে নতুন Bytes object তৈরি করা যায়।

```python
data = b"Hello"

new_data = b"J" + data[1:]

print(new_data)
```

**Output:**

```text
b'Jello'
```

এখানে পুরোনো Bytes পরিবর্তন হয়নি। নতুন Bytes তৈরি হয়েছে।

---

## 12. What Happens When We Use `str()` on Bytes?

অনেকেই মনে করে `str()` ব্যবহার করলে Bytes সরাসরি normal String-এ convert হয়ে যায়। কিন্তু বিষয়টি এমন নয়।

উদাহরণ:

```python
data = b"Hello"

text = str(data)

print(text)
print(type(text))
```

**Output:**

```text
b'Hello'
<class 'str'>
```

এখানে `str()` Bytes object-এর representation-কে String হিসেবে তৈরি করেছে। এটি Bytes-এর আসল text decode করেনি।

সঠিক পদ্ধতি:

```python
data = b"Hello"

text = data.decode("utf-8")

print(text)
```

**Output:**

```text
Hello
```

**মনে রাখবে:**

- `str()` Bytes-এর representation String-এ তৈরি করে।
- `decode()` Bytes-এর data থেকে আসল text বের করে।

---

## 13. String and Bytes Cannot Be Directly Combined

String এবং Bytes আলাদা data type। তাই এদের সরাসরি `+` দিয়ে যোগ করা যায় না।

উদাহরণ:

```python
text = "Hello"
data = b"World"

result = text + data

print(result)
```

**Output:**

```text
TypeError
```

কারণ Python সরাসরি String এবং Bytes যোগ করতে পারে না।

সমাধান ১: Bytes-কে String-এ convert করা।

```python
text = "Hello"
data = b"World"

result = text + data.decode("utf-8")

print(result)
```

**Output:**

```text
HelloWorld
```

সমাধান ২: String-কে Bytes-এ convert করা।

```python
text = "Hello"
data = b"World"

result = text.encode("utf-8") + data

print(result)
```

**Output:**

```text
b'HelloWorld'
```

---

## 14. Where Are Bytes Used?

Bytes সাধারণত এমন data নিয়ে কাজ করার সময় ব্যবহৃত হয়, যেগুলো সরাসরি সাধারণ text নয়।

কিছু গুরুত্বপূর্ণ ব্যবহার:

1. **Images:** Image file-এর data পড়তে।
2. **Audio:** Audio file-এর binary data নিয়ে কাজ করতে।
3. **Videos:** Video file-এর data process করতে।
4. **Networking:** Network-এর মাধ্যমে data পাঠাতে ও গ্রহণ করতে।
5. **Binary Files:** PDF, ZIP এবং অন্যান্য binary file নিয়ে কাজ করতে।

উদাহরণ:

```python
data = b"Hello"

print(data)
```

**Output:**

```text
b'Hello'
```

এখানে `data` একটি Bytes object।

---

## 15. String Length vs Bytes Length

String-এর length এবং Bytes-এর length সবসময় এক হয় না।

কারণ String-এর `len()` character বা Unicode code point গণনা করে। অন্যদিকে Bytes-এর `len()` byte গণনা করে।

উদাহরণ:

```python
text = "Hello"

print(len(text))
print(len(text.encode("utf-8")))
```

**Output:**

```text
5
5
```

এখানে প্রতিটি English character UTF-8-এ 1 byte।

এবার Bangla text দেখি:

```python
text = "বাংলা"

print(len(text))
print(len(text.encode("utf-8")))
```

**Output:**

```text
5
15
```

এখানে:

- String-এর character count = 5
- UTF-8 encoded Bytes-এর length = 15

**মনে রাখবে:** Character count এবং byte count এক জিনিস নয়।

---

## 16. Using `bytearray()`

`bytes` immutable হলেও Python-এ `bytearray` নামে একটি mutable byte sequence রয়েছে।

অর্থাৎ `bytearray`-এর element পরিবর্তন করা যায়।

উদাহরণ:

```python
data = bytearray(b"Hello")

data[0] = 74

print(data)
```

**Output:**

```text
bytearray(b'Jello')
```

এখানে:

- `bytearray()` একটি mutable byte sequence তৈরি করে।
- `74` হলো `J`-এর byte value।
- তাই `H` পরিবর্তন হয়ে `J` হয়েছে।

সহজ পার্থক্য:

| bytes | bytearray |
|---|---|
| Immutable | Mutable |
| পরিবর্তন করা যায় না | পরিবর্তন করা যায় |
| `bytes` type | `bytearray` type |

---

## 17. Common Mistakes

### Mistake 1: Bytes-কে String মনে করা

```python
data = b"Hello"

print(type(data))
```

**Output:**

```text
<class 'bytes'>
```

`b"Hello"` একটি Bytes object, String নয়।

### Mistake 2: Non-ASCII character সরাসরি Bytes literal-এ লেখা

```python
data = b"বাংলা"
```

**Output:**

```text
SyntaxError
```

সঠিক পদ্ধতি:

```python
data = "বাংলা".encode("utf-8")

print(data)
```

### Mistake 3: `str()` দিয়ে Bytes decode করার চেষ্টা করা

```python
data = b"Hello"

print(str(data))
```

**Output:**

```text
b'Hello'
```

সঠিক পদ্ধতি:

```python
print(data.decode("utf-8"))
```

**Output:**

```text
Hello
```

### Mistake 4: String এবং Bytes সরাসরি যোগ করা

```python
text = "Hello"
data = b"World"

print(text + data)
```

**Output:**

```text
TypeError
```

সমাধান: যোগ করার আগে একই data type-এ convert করতে হবে।

### Mistake 5: ভুল Encoding দিয়ে Decode করা

Bytes যে encoding দিয়ে তৈরি হয়েছে, সাধারণত সেটি দিয়েই decode করতে হয়।

```python
text = "বাংলা"

data = text.encode("utf-8")

result = data.decode("utf-8")

print(result)
```

**Output:**

```text
বাংলা
```

---

## 18. Important Rules to Remember

1. `str` হলো Python-এর String data type।
2. `bytes` হলো byte data-এর sequence।
3. `b` prefix ব্যবহার করে Bytes literal তৈরি করা যায়।
4. `encode()` String-কে Bytes-এ convert করে।
5. `decode()` Bytes-কে String-এ convert করে।
6. String indexing করলে character পাওয়া যায়।
7. Bytes indexing করলে integer পাওয়া যায়।
8. Bytes হলো immutable।
9. `bytearray` হলো mutable।
10. String এবং Bytes সরাসরি concatenate করা যায় না।
11. `str()` ব্যবহার করা মানেই Bytes decode করা নয়।
12. Text-এর জন্য String এবং binary data-এর জন্য Bytes ব্যবহার করা হয়।

---

## 19. Practice Exercises

### Practice 1: Create a String

একটি String তৈরি করো এবং তার data type print করো।

**Solution:**

```python
text = "Python Programming"

print(text)
print(type(text))
```

**Output:**

```text
Python Programming
<class 'str'>
```

### Practice 2: Create Bytes

একটি Bytes object তৈরি করো এবং তার data type print করো।

**Solution:**

```python
data = b"Python"

print(data)
print(type(data))
```

**Output:**

```text
b'Python'
<class 'bytes'>
```

### Practice 3: Convert String into Bytes

একটি String-কে UTF-8 ব্যবহার করে Bytes-এ convert করো।

**Solution:**

```python
text = "Bangladesh"

data = text.encode("utf-8")

print(data)
```

**Output:**

```text
b'Bangladesh'
```

### Practice 4: Convert Bytes into String

একটি Bytes object-কে String-এ convert করো।

**Solution:**

```python
data = b"Hello Python"

text = data.decode("utf-8")

print(text)
```

**Output:**

```text
Hello Python
```

### Practice 5: Access Bytes Elements

নিচের Bytes object-এর প্রথম এবং দ্বিতীয় element print করো।

**Solution:**

```python
data = b"ABC"

print(data[0])
print(data[1])
```

**Output:**

```text
65
66
```

### Practice 6: Check String and Bytes Length

নিচের String-এর character এবং byte count বের করো।

**Solution:**

```python
text = "বাংলা"

print(len(text))
print(len(text.encode("utf-8")))
```

**Output:**

```text
5
15
```

### Practice 7: Modify Bytes Using bytearray

একটি `bytearray` তৈরি করে প্রথম character পরিবর্তন করো।

**Solution:**

```python
data = bytearray(b"Hello")

data[0] = 74

print(data)
```

**Output:**

```text
bytearray(b'Jello')
```

---

## 20. Chapter Summary

এই topic-এ আমরা শিখেছি:

- String (`str`) কী।
- Bytes (`bytes`) কী।
- String এবং Bytes-এর পার্থক্য।
- `b` prefix দিয়ে Bytes তৈরি করা।
- `encode()` দিয়ে String থেকে Bytes তৈরি করা।
- `decode()` দিয়ে Bytes থেকে String তৈরি করা।
- Bytes indexing এবং slicing।
- Bytes immutable কেন।
- `str()` এবং `decode()`-এর পার্থক্য।
- String ও Bytes সরাসরি যোগ করা যায় না কেন।
- `bytearray()` কী এবং কেন ব্যবহার করা হয়।
- Character count এবং byte count-এর পার্থক্য।

---

## 21. Self-Assessment Checklist

নিজেকে যাচাই করো:

- [ ] String এবং Bytes-এর পার্থক্য বুঝতে পেরেছি।
- [ ] `str` এবং `bytes` data type চিনতে পারি।
- [ ] `b` prefix ব্যবহার করে Bytes তৈরি করতে পারি।
- [ ] `encode()` ব্যবহার করতে পারি।
- [ ] `decode()` ব্যবহার করতে পারি।
- [ ] Bytes indexing এবং slicing করতে পারি।
- [ ] Bytes কেন immutable তা বুঝতে পেরেছি।
- [ ] `bytearray()` ব্যবহার করতে পারি।
- [ ] String এবং Bytes-এর length-এর পার্থক্য বুঝতে পেরেছি।

---

## 22. Next Topic

পরবর্তী topic-এ আমরা শিখব:

**42. Converting Between Strings and Other Types**

এখানে String-কে Integer, Float এবং অন্যান্য data type-এ convert করা এবং সেগুলোকে আবার String-এ convert করা শিখব।
