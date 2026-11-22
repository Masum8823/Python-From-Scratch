
# 40. String Encoding and Unicode Basics in Python

## 1. Introduction to Character Encoding

Computer মূলত Binary Data অর্থাৎ `0` এবং `1` ব্যবহার করে কাজ করে।

কিন্তু আমরা Computer-এ বিভিন্ন ধরনের Character ব্যবহার করি, যেমন:

- English Letters: A, B, C
- Numbers: 1, 2, 3
- Symbols: @, #, $
- Bangla Characters: অ, আ, ক, খ
- Other Languages: 中, 日, 한

Computer-কে এসব Character বুঝতে হলে Character-কে Binary Data-তে Represent করতে হয়।

একটি Character-কে নির্দিষ্ট নিয়মে Binary Data-তে Represent করার পদ্ধতিকে **Character Encoding** বলা হয়।

### Example

```python
text = "A"

print(text)
```

**Output:**

```text
A
```

আমরা `A` দেখতে পেলেও Computer এটিকে নির্দিষ্ট Binary Representation-এর মাধ্যমে সংরক্ষণ করতে পারে।

**মনে রাখবে:**

Character Encoding-এর মূল কাজ হলো Text Character-কে Byte-এর মাধ্যমে Represent করা।

---

## 2. What is ASCII?

ASCII-এর Full Form হলো **American Standard Code for Information Interchange**।

ASCII হলো একটি পুরোনো Character Encoding Standard, যেখানে English Letters, Numbers এবং কিছু Special Symbols-এর জন্য নির্দিষ্ট Numeric Code ব্যবহার করা হয়।

ASCII মূলত 7-bit ব্যবহার করে।

তাই এতে মোট:

\[
2^7 = 128
\]

টি Character Represent করা যায়।

### Some ASCII Values

| Character | Decimal Value |
|---|---:|
| A | 65 |
| B | 66 |
| C | 67 |
| a | 97 |
| b | 98 |
| c | 99 |
| 0 | 48 |
| 1 | 49 |
| Space | 32 |

### Example 1: Using ord()

Python-এর `ord()` Function ব্যবহার করে কোনো Character-এর Unicode Code Point জানা যায়।

```python
print(ord("A"))
print(ord("B"))
print(ord("a"))
```

**Output:**

```text
65
66
97
```

এখানে:

- `ord("A")` → 65
- `ord("B")` → 66
- `ord("a")` → 97

এই Character-গুলো ASCII-এর অংশও।

### Example 2: Using chr()

Python-এর `chr()` Function ব্যবহার করে কোনো Numeric Code Point থেকে Character পাওয়া যায়।

```python
print(chr(65))
print(chr(66))
print(chr(97))
```

**Output:**

```text
A
B
a
```

**মনে রাখবে:**

- `ord()` → Character থেকে Number।
- `chr()` → Number থেকে Character।

---

## 3. Limitations of ASCII

ASCII মূলত English Language-এর Character এবং কিছু Symbols Represent করার জন্য তৈরি হয়েছিল।

কিন্তু পৃথিবীতে অনেক Language রয়েছে, যেমন:

- Bangla
- Arabic
- Chinese
- Japanese
- Korean
- Hindi

Standard ASCII-তে এসব Language-এর Character Represent করার ব্যবস্থা নেই।

### Example

```python
text = "Hello"

print(text)
```

**Output:**

```text
Hello
```

এটি ASCII Character দিয়ে তৈরি।

কিন্তু Bangla Text-এর ক্ষেত্রে:

```python
text = "আমি Python শিখছি"

print(text)
```

**Output:**

```text
আমি Python শিখছি
```

Python 3 এই Text সহজেই Handle করতে পারে।

কিন্তু Standard ASCII-তে Bangla Character Represent করা যায় না।

**সমাধান:** বিভিন্ন ভাষার Character Represent করার জন্য Unicode তৈরি করা হয়েছে।

---

## 4. What is Unicode?

Unicode হলো একটি Universal Character Standard, যা পৃথিবীর বিভিন্ন Language-এর Character, Number এবং Symbol-কে একটি Unique Code Point প্রদান করে।

Unicode-এর মাধ্যমে আমরা একই Programming Language-এ বিভিন্ন ভাষার Text ব্যবহার করতে পারি।

Unicode Support করে:

- English
- Bangla
- Arabic
- Chinese
- Japanese
- Hindi
- Emoji
- বিভিন্ন Special Symbols

### Example

```python
text = "Hello, আমি Python শিখছি 😊"

print(text)
```

**Output:**

```text
Hello, আমি Python শিখছি 😊
```

এখানে English, Bangla এবং Emoji একই String-এর মধ্যে ব্যবহার করা হয়েছে।

Python 3 Unicode Text Support করে।

### Unicode Code Point

প্রতিটি Unicode Character-এর একটি নির্দিষ্ট Code Point থাকে।

Unicode Code Point সাধারণত `U+` দিয়ে লেখা হয়।

### Example

| Character | Unicode Code Point |
|---|---|
| A | U+0041 |
| B | U+0042 |
| a | U+0061 |
| অ | U+0985 |
| আ | U+0986 |
| 😊 | U+1F60A |

### Example: Using ord()

```python
print(ord("A"))
print(ord("অ"))
print(ord("😊"))
```

**Output:**

```text
65
2437
128522
```

এখানে `ord()` প্রতিটি Character-এর Unicode Code Point-এর Decimal Value Return করেছে।

---

## 5. Unicode vs ASCII

ASCII এবং Unicode উভয়ই Character Represent করার জন্য ব্যবহৃত হয়।

তবে তাদের মধ্যে কিছু গুরুত্বপূর্ণ পার্থক্য রয়েছে।

| ASCII | Unicode |
|---|---|
| পুরোনো Character Encoding Standard। | Universal Character Standard। |
| Standard ASCII 7-bit ব্যবহার করে। | বিভিন্ন Encoding Form ব্যবহার করে। |
| মোট 128টি Character Represent করে। | অসংখ্য Language ও Symbol Support করে। |
| মূলত English Character-এর জন্য তৈরি। | বিশ্বের বিভিন্ন Language Support করে। |
| Bangla Character Support করে না। | Bangla Character Support করে। |

**মনে রাখবে:** ASCII-এর প্রথম 128টি Character Unicode-এর মধ্যেও অন্তর্ভুক্ত রয়েছে।

---

## 6. What is UTF?

UTF-এর Full Form হলো **Unicode Transformation Format**।

Unicode Character-কে Byte-এর মাধ্যমে Encode করার জন্য UTF ব্যবহার করা হয়।

Unicode একটি Character Standard, আর UTF হলো সেই Character-গুলোকে Byte-এ Represent করার Encoding Method।

UTF-এর গুরুত্বপূর্ণ কয়েকটি Encoding হলো:

1. UTF-8
2. UTF-16
3. UTF-32

এগুলোর মধ্যে UTF-8 সবচেয়ে বেশি ব্যবহৃত Encoding Form।

---

## 7. What is UTF-8?

UTF-8 হলো Unicode-এর একটি Variable-Length Encoding Method।

এতে একটি Character Encode করতে 1 থেকে 4 Byte পর্যন্ত প্রয়োজন হতে পারে।

| Character Range | Bytes |
|---|---:|
| U+0000 to U+007F | 1 Byte |
| U+0080 to U+07FF | 2 Bytes |
| U+0800 to U+FFFF | 3 Bytes |
| U+10000 to U+10FFFF | 4 Bytes |

### Example 1: Encoding English Text

```python
text = "Hello"

encoded_text = text.encode("utf-8")

print(encoded_text)
```

**Output:**

```text
b'Hello'
```

এখানে `encode("utf-8")` String-কে UTF-8 Bytes-এ Convert করেছে।

English-এর প্রতিটি Character এখানে 1 Byte করে নিয়েছে।

### Example 2: Encoding Bangla Text

```python
text = "বাংলা"

encoded_text = text.encode("utf-8")

print(encoded_text)
```

**Output:**

```text
b'\xe0\xa6\xac\xe0\xa6\xbe\xe0\xa6\x82\xe0\xa6\xb2\xe0\xa6\xbe'
```

এখানে Bangla Character-গুলো UTF-8 Encoding অনুযায়ী Bytes-এ Convert হয়েছে।

### Example 3: Checking Byte Length

```python
english = "Hello"
bangla = "বাংলা"

print(len(english.encode("utf-8")))
print(len(bangla.encode("utf-8")))
```

**Output:**

```text
5
10
```

এখানে:

- `"Hello"` → 5 Bytes।
- `"বাংলা"` → 10 Bytes।

**মনে রাখবে:** String-এর Character সংখ্যা এবং UTF-8 Encoded Byte সংখ্যা সবসময় সমান হয় না।

---

## 8. What is UTF-16?

UTF-16 হলো Unicode-এর আরেকটি Variable-Length Encoding Method।

এতে সাধারণত একটি Character Encode করতে 2 অথবা 4 Byte প্রয়োজন হয়।

### Example

```python
text = "Hello"

encoded_text = text.encode("utf-16")

print(encoded_text)
```

**Output (BOM এবং Byte Order অনুযায়ী):**

```text
b'\xff\xfeH\x00e\x00l\x00l\x00o\x00'
```

এখানে:

- `utf-16` ব্যবহার করে String Encode করা হয়েছে।
- Output একটি Bytes Object।
- BOM (Byte Order Mark) Encoding-এর Byte Order নির্দেশ করতে পারে।

### UTF-16-এর বৈশিষ্ট্য

- সাধারণ BMP Character সাধারণত 2 Bytes নেয়।
- BMP-এর বাইরের Character 4 Bytes নেয়।
- UTF-16 Variable-Length Encoding।
- বিভিন্ন Platform-এ UTF-16 ব্যবহৃত হয়।

---

## 9. What is UTF-32?

UTF-32 হলো Unicode-এর একটি Fixed-Length Encoding Method।

এতে প্রতিটি Unicode Code Point-এর জন্য 4 Bytes ব্যবহার করা হয়।

### Example

```python
text = "Hello"

encoded_text = text.encode("utf-32")

print(encoded_text)
```

**Output (সাধারণ Little-Endian Python Environment):**

```text
b'\xff\xfe\x00\x00H\x00\x00\x00e\x00\x00\x00l\x00\x00\x00l\x00\x00\x00o\x00\x00\x00'
```

এখানে প্রতিটি Character-এর জন্য 4 Bytes ব্যবহার হয়েছে।

### UTF-32-এর বৈশিষ্ট্য

- Fixed-Length Encoding।
- প্রতিটি Unicode Code Point-এর জন্য 4 Bytes।
- UTF-8 এবং UTF-16-এর তুলনায় বেশি Storage প্রয়োজন হতে পারে।
- Character-এর অবস্থান নির্ণয় করা সহজ।

---

## 10. Difference Between UTF-8, UTF-16 and UTF-32

| Feature | UTF-8 | UTF-16 | UTF-32 |
|---|---|---|---|
| Encoding Type | Variable | Variable | Fixed |
| Bytes | 1–4 | 2 or 4 | 4 |
| English Character | 1 Byte | 2 Bytes | 4 Bytes |
| ASCII Compatible | Yes | No | No |
| Storage | সাধারণত Efficient | মাঝামাঝি | বেশি |
| Usage | খুব বেশি প্রচলিত | বিভিন্ন Platform-এ ব্যবহৃত | তুলনামূলকভাবে কম |

**মনে রাখবে:**

- UTF-8 → 1 থেকে 4 Bytes।
- UTF-16 → 2 অথবা 4 Bytes।
- UTF-32 → 4 Bytes।

---

## 11. Encoding Strings in Python

Python-এর `encode()` Method ব্যবহার করে String-কে Bytes-এ Convert করা যায়।

### Syntax

```python
string.encode(encoding)
```

### Example 1: UTF-8 Encoding

```python
text = "Python"

encoded = text.encode("utf-8")

print(encoded)
print(type(encoded))
```

**Output:**

```text
b'Python'
<class 'bytes'>
```

এখানে:

- `encode()` String-কে Bytes-এ Convert করেছে।
- `type()` দেখিয়েছে যে Result-এর Data Type হলো `bytes`।

### Example 2: Different Encodings

```python
text = "Hello"

utf8 = text.encode("utf-8")
utf16 = text.encode("utf-16")
utf32 = text.encode("utf-32")

print(len(utf8))
print(len(utf16))
print(len(utf32))
```

**Output (Common Little-Endian Environment):**

```text
5
12
24
```

এখানে:

- UTF-8 → 5 Bytes।
- UTF-16 → 12 Bytes (2-Byte BOM সহ)।
- UTF-32 → 24 Bytes (4-Byte BOM সহ)।

---

## 12. Decoding Bytes in Python

Bytes-কে আবার String-এ Convert করার পদ্ধতিকে Decoding বলা হয়।

Python-এর `decode()` Method ব্যবহার করে এটি করা যায়।

### Syntax

```python
bytes_data.decode(encoding)
```

### Example

```python
text = "Hello, Python!"

encoded = text.encode("utf-8")

decoded = encoded.decode("utf-8")

print(decoded)
```

**Output:**

```text
Hello, Python!
```

এখানে:

1. প্রথমে String-কে UTF-8 দিয়ে Encode করা হয়েছে।
2. এরপর Bytes-কে UTF-8 দিয়ে Decode করা হয়েছে।
3. Original Text আবার পাওয়া গেছে।

### Example 2: Checking Data Types

```python
text = "Python"

encoded = text.encode("utf-8")
decoded = encoded.decode("utf-8")

print(type(text))
print(type(encoded))
print(type(decoded))
```

**Output:**

```text
<class 'str'>
<class 'bytes'>
<class 'str'>
```

**মনে রাখবে:**

- `encode()` → String থেকে Bytes।
- `decode()` → Bytes থেকে String।

---

## 13. Difference Between Encoding and Decoding

Encoding এবং Decoding একে অপরের বিপরীত প্রক্রিয়া।

| Encoding | Decoding |
|---|---|
| String-কে Bytes-এ Convert করে। | Bytes-কে String-এ Convert করে। |
| `encode()` Method ব্যবহার করে। | `decode()` Method ব্যবহার করে। |
| Text সংরক্ষণ বা পাঠানোর জন্য ব্যবহৃত হয়। | Bytes থেকে Text ফিরে পাওয়ার জন্য ব্যবহৃত হয়। |

### Example

```python
text = "Python"

encoded = text.encode("utf-8")
decoded = encoded.decode("utf-8")

print(encoded)
print(decoded)
```

**Output:**

```text
b'Python'
Python
```

---

## 14. Unicode Escape Sequences

Python-এ Unicode Character Represent করার জন্য Unicode Escape Sequence ব্যবহার করা যায়।

দুই ধরনের Escape Sequence গুরুত্বপূর্ণ:

- `\u` → 4-Digit Unicode Code Point।
- `\U` → 8-Digit Unicode Code Point।

### Example 1: Using \u

```python
print("\u0041")
print("\u0985")
```

**Output:**

```text
A
অ
```

### Example 2: Using \U

```python
print("\U0001F60A")
```

**Output:**

```text
😊
```

### Example 3: Multiple Unicode Characters

```python
text = "\u0048\u0065\u006C\u006C\u006F"

print(text)
```

**Output:**

```text
Hello
```

এখানে প্রতিটি Unicode Escape Sequence একটি Character নির্দেশ করছে।

---

## 15. Unicode in Python Strings

Python 3-এর `str` Type Unicode Text সংরক্ষণ করে।

তাই একই String-এর মধ্যে বিভিন্ন Language-এর Character ব্যবহার করা যায়।

### Example

```python
message = "Hello, আমি Python শিখছি!"

print(message)
```

**Output:**

```text
Hello, আমি Python শিখছি!
```

### Example 2: Multiple Languages

```python
text = "Hello | বাংলা | العربية | 日本語"

print(text)
```

**Output:**

```text
Hello | বাংলা | العربية | 日本語
```

এখানে বিভিন্ন Language-এর Character একই String-এ ব্যবহার করা হয়েছে।

---

## 16. Difference Between len() and Encoded Byte Length

Python-এর `len()` Function String-এর Character Count করে।

অন্যদিকে, `encode()` করার পরে `len()` ব্যবহার করলে Encoded Bytes-এর সংখ্যা পাওয়া যায়।

### Example 1: English Text

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

এখানে প্রতিটি English Character UTF-8-এ 1 Byte।

### Example 2: Bangla Text

```python
text = "বাংলা"

print(len(text))
print(len(text.encode("utf-8")))
```

**Output:**

```text
5
10
```

এখানে:

- `len(text)` → 5টি Unicode Code Point।
- `len(text.encode("utf-8"))` → 10 Bytes।

**Important:** Python-এর `len()` সাধারণত String-এর Unicode Code Point Count করে; এটি সবসময় মানুষের চোখে দেখা Character বা Grapheme Cluster-এর সংখ্যা নয়।

---

## 17. Character vs Byte

Character এবং Byte এক জিনিস নয়।

Character হলো Text-এর একটি Unicode Code Point।

অন্যদিকে, Byte হলো Binary Data-এর একটি Unit।

একটি Character Encode করতে একাধিক Byte প্রয়োজন হতে পারে।

### Example

```python
text = "Aঅ😊"

print(len(text))
print(len(text.encode("utf-8")))
```

**Output:**

```text
3
8
```

এখানে:

- `A` → 1 Byte।
- `অ` → 3 Bytes।
- `😊` → 4 Bytes।

মোট:

\[
1 + 3 + 4 = 8 \text{ Bytes}
\]

কিন্তু Unicode Code Point-এর সংখ্যা 3।

---

## 18. Handling Unicode Encoding Errors

কোনো String-কে এমন Encoding দিয়ে Encode করতে গেলে Error হতে পারে, যেখানে সেই Character Represent করা সম্ভব নয়।

### Example

```python
text = "বাংলা"

encoded = text.encode("ascii")
```

**Output:**

```text
UnicodeEncodeError
```

কারণ Standard ASCII-তে Bangla Character Represent করা যায় না।

### Solution: Using UTF-8

```python
text = "বাংলা"

encoded = text.encode("utf-8")

print(encoded)
```

**Output:**

```text
b'\xe0\xa6\xac\xe0\xa6\xbe\xe0\xa6\x82\xe0\xb2\xb2\xe0\xa6\xbe'
```

UTF-8 ব্যবহার করলে Bangla Character সঠিকভাবে Encode করা যায়।

---

## 19. Practical Example: Encoding and Decoding Bangla Text

```python
message = "আমি Python শিখছি"

encoded = message.encode("utf-8")

decoded = encoded.decode("utf-8")

print("Original:", message)
print("Encoded:", encoded)
print("Decoded:", decoded)
```

**Output:**

```text
Original: আমি Python শিখছি
Encoded: [UTF-8 Bytes]
Decoded: আমি Python শিখছি
```

এখানে:

- Original Text একটি String।
- Encoded Data একটি Bytes Object।
- Decoded Text আবার Original String হয়েছে।

---

## 20. Practical Example: Checking String Size

```python
text = "Hello বাংলা"

character_count = len(text)
byte_count = len(text.encode("utf-8"))

print("Text:", text)
print("Character Count:", character_count)
print("UTF-8 Byte Count:", byte_count)
```

**Output:**

```text
Text: Hello বাংলা
Character Count: 11
UTF-8 Byte Count: 16
```

এখানে:

- Character Count হলো 11।
- UTF-8 Byte Count হলো 16।

এটি দেখায় যে Character Count এবং Byte Count আলাদা হতে পারে।

---

## 21. Practical Example: Saving Unicode Text in a File

Python-এ File-এর মধ্যে Unicode Text সংরক্ষণ করতে `encoding="utf-8"` ব্যবহার করা যায়।

### Example

```python
with open("message.txt", "w", encoding="utf-8") as file:
    file.write("Hello, আমি Python শিখছি!")

print("File saved successfully.")
```

**Output:**

```text
File saved successfully.
```

এখানে:

- `open()` File তৈরি বা Open করেছে।
- `"w"` Write Mode নির্দেশ করে।
- `encoding="utf-8"` UTF-8 Encoding ব্যবহার করেছে।
- `write()` Text File-এ সংরক্ষণ করেছে।

### Reading the File

```python
with open("message.txt", "r", encoding="utf-8") as file:
    content = file.read()

print(content)
```

**Output:**

```text
Hello, আমি Python শিখছি!
```

**মনে রাখবে:** Unicode Text File-এ সংরক্ষণ এবং পড়ার সময় একই Encoding ব্যবহার করা ভালো।

---

## 22. Important Rules to Remember

1. Computer Binary Data ব্যবহার করে কাজ করে।
2. Character Encoding Text-কে Bytes-এ Represent করার নিয়ম।
3. ASCII একটি পুরোনো Character Encoding Standard।
4. Standard ASCII 7-bit ব্যবহার করে।
5. Standard ASCII-তে মোট 128টি Character রয়েছে।
6. Unicode বিভিন্ন Language-এর Character-এর জন্য Code Point নির্ধারণ করে।
7. UTF-এর Full Form হলো Unicode Transformation Format।
8. UTF-8 একটি Variable-Length Encoding।
9. UTF-8-এ 1 থেকে 4 Bytes প্রয়োজন হয়।
10. UTF-16-এ সাধারণত 2 অথবা 4 Bytes প্রয়োজন হয়।
11. UTF-32 প্রতিটি Unicode Code Point-এর জন্য 4 Bytes ব্যবহার করে।
12. Python 3-এর `str` Type Unicode Text Support করে।
13. `ord()` Character-এর Unicode Code Point Return করে।
14. `chr()` Code Point থেকে Character Return করে।
15. `encode()` String-কে Bytes-এ Convert করে।
16. `decode()` Bytes-কে String-এ Convert করে।
17. `len()` String-এর Unicode Code Point Count করে।
18. Encoded Byte Count বের করতে `len(text.encode("utf-8"))` ব্যবহার করা যায়।
19. Unicode Escape Sequence-এর জন্য `\u` এবং `\U` ব্যবহার করা হয়।
20. Bangla এবং অন্যান্য Language-এর Text Handle করার জন্য UTF-8 একটি ভালো সাধারণ পছন্দ।

---

## 23. Common Mistakes and Debugging

### Mistake 1: Confusing String and Bytes

```python
text = "Python"

print(type(text))
```

**Output:**

```text
<class 'str'>
```

এটি একটি String, Bytes নয়।

**Correct Way:**

```python
text = "Python"

encoded = text.encode("utf-8")

print(type(encoded))
```

**Output:**

```text
<class 'bytes'>
```

**মনে রাখবে:** `str` এবং `bytes` আলাদা Data Type।

### Mistake 2: Using Wrong Encoding for Decoding

```python
text = "বাংলা"

encoded = text.encode("utf-8")

decoded = encoded.decode("ascii")
```

**Output:**

```text
UnicodeDecodeError
```

**সমস্যা:** UTF-8 দিয়ে Encode করা Bytes-কে ASCII দিয়ে Decode করা হয়েছে।

**Correct Code:**

```python
text = "বাংলা"

encoded = text.encode("utf-8")
decoded = encoded.decode("utf-8")

print(decoded)
```

**Output:**

```text
বাংলা
```

### Mistake 3: Counting Characters Instead of Bytes

```python
text = "বাংলা"

print(len(text))
```

**Output:**

```text
5
```

এটি Character Count, Byte Count নয়।

**Correct Code:**

```python
text = "বাংলা"

print(len(text.encode("utf-8")))
```

**Output:**

```text
10
```

### Mistake 4: Using ASCII for Bangla Text

```python
text = "আমি ভালো আছি"

encoded = text.encode("ascii")
```

**Output:**

```text
UnicodeEncodeError
```

**সমস্যা:** Standard ASCII-তে Bangla Character Represent করা যায় না।

**Correct Code:**

```python
text = "আমি ভালো আছি"

encoded = text.encode("utf-8")

print(encoded)
```

**মনে রাখবে:** বিভিন্ন Language-এর Text Encode করার জন্য UTF-8 ব্যবহার করা সুবিধাজনক।

---

## 24. Practice Exercises

### Exercise 1: Using ord()

নিচের Character-গুলোর Unicode Code Point বের করো।

```python
print(ord("A"))
print(ord("B"))
print(ord("a"))
```

**Expected Output:**

```text
65
66
97
```

### Exercise 2: Using chr()

নিচের Number-গুলো থেকে Character তৈরি করো।

```python
print(chr(65))
print(chr(66))
print(chr(67))
```

**Expected Output:**

```text
A
B
C
```

### Exercise 3: Unicode Character

Unicode ব্যবহার করে Bangla Character Display করো।

```python
print("\u0985")
print("\u0986")
```

**Expected Output:**

```text
অ
আ
```

### Exercise 4: UTF-8 Encoding

নিচের String-কে UTF-8-এ Encode করো।

```python
text = "Hello"
```

**Expected Output:**

```text
b'Hello'
```

### Exercise 5: Encoding and Decoding

String-কে প্রথমে Encode এবং পরে Decode করো।

```python
text = "Python"
```

**Expected Output:**

```text
Python
```

### Exercise 6: Character and Byte Count

নিচের String-এর Character Count এবং UTF-8 Byte Count বের করো।

```python
text = "Hello"
```

**Expected Output:**

```text
Character Count: 5
Byte Count: 5
```

### Exercise 7: Bangla Encoding

নিচের Bangla Text-কে UTF-8-এ Encode করো।

```python
text = "বাংলা"
```

**Expected Output:**

```text
UTF-8 Bytes: b'\xe0\xa6\xac\xe0\xa6\xbe\xe0\xa6\x82\xe0\xb2\xb2\xe0\xa6\xbe'
```

### Exercise 8: Predict the Output

নিচের Code-এর Output নিজে Predict করো।

```python
text = "Hello"

print(len(text))
print(len(text.encode("utf-8")))
print(type(text))
print(type(text.encode("utf-8")))
```

**Expected Output:**

```text
5
5
<class 'str'>
<class 'bytes'>
```

### Exercise 9: Predict the Output

```python
text = "Aঅ😊"

print(len(text))
print(len(text.encode("utf-8")))
print(ord("A"))
print(ord("অ"))
```

**Expected Output:**

```text
3
8
65
2437
```

### Exercise 10: Practical Programming

একটি Program তৈরি করো, যেখানে:

1. একটি Bangla Text Variable-এ রাখবে।
2. Text-কে UTF-8 দিয়ে Encode করবে।
3. Encoded Data-কে আবার Decode করবে।
4. Original Text এবং Decoded Text Display করবে।

**Expected Output:**

```text
Original Text: আমি Python শিখছি
Decoded Text: আমি Python শিখছি
```

---

## 25. Chapter Summary

এই Topic-এ আমরা Python-এর String Encoding এবং Unicode-এর Basic Concepts শিখেছি।

| Topic | Description |
|---|---|
| Character Encoding | Character-কে Bytes-এ Represent করা |
| ASCII | 7-bit Character Standard |
| Unicode | Universal Character Standard |
| UTF-8 | 1–4 Bytes Encoding |
| UTF-16 | 2 অথবা 4 Bytes Encoding |
| UTF-32 | 4 Bytes Fixed-Length Encoding |
| ord() | Character থেকে Code Point |
| chr() | Code Point থেকে Character |
| encode() | String থেকে Bytes |
| decode() | Bytes থেকে String |
| Unicode Escape | `\u` এবং `\U` ব্যবহার |

**মনে রাখবে:**

```python
text = "আমি Python শিখছি"

encoded = text.encode("utf-8")
decoded = encoded.decode("utf-8")

print(decoded)
```

**Output:**

```text
আমি Python শিখছি
```

সবচেয়ে গুরুত্বপূর্ণ বিষয় হলো, Python 3-এর String Unicode Text Support করে এবং `encode()` ও `decode()` ব্যবহার করে String এবং Bytes-এর মধ্যে Conversion করা যায়।

---

## 26. Self-Assessment Checklist

- [ ] Character Encoding কী বুঝতে পেরেছি।
- [ ] ASCII কী এবং এর Limitations জানি।
- [ ] Unicode কী বুঝতে পেরেছি।
- [ ] ASCII এবং Unicode-এর পার্থক্য বুঝি।
- [ ] UTF-এর Full Form জানি।
- [ ] UTF-8, UTF-16 এবং UTF-32 বুঝি।
- [ ] `ord()` ব্যবহার করতে পারি।
- [ ] `chr()` ব্যবহার করতে পারি।
- [ ] `encode()` ব্যবহার করতে পারি।
- [ ] `decode()` ব্যবহার করতে পারি।
- [ ] String এবং Bytes-এর পার্থক্য বুঝি।
- [ ] Character Count এবং Byte Count বের করতে পারি।
- [ ] Unicode Escape Sequence ব্যবহার করতে পারি।
- [ ] Bangla Text Encode এবং Decode করতে পারি।
- [ ] UTF-8 দিয়ে File Read এবং Write করতে পারি।

---

## 27. Next Topic

পরবর্তী Topic:

**41. Bytes vs Strings in Python**

পরবর্তী File:

`41_Bytes_vs_Strings.md`

এখানে আমরা `str` এবং `bytes` Data Type-এর পার্থক্য, Bytes Object তৈরি, Indexing, Slicing, Iteration এবং Encoding ও Decoding-এর Practical ব্যবহার শিখব।
