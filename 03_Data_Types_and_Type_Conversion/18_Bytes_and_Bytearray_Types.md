# 18. Bytes and Bytearray Types in Python

## 1. Introduction to Bytes and Bytearray

Python-এ `bytes` এবং `bytearray` হলো দুটি built-in data type, যেগুলো **binary data** সংরক্ষণ করতে ব্যবহৃত হয়।

আমরা সাধারণত String দিয়ে text সংরক্ষণ করি। কিন্তু image, audio, video, network data এবং binary file-এর মতো তথ্য নিয়ে কাজ করার সময় byte-এর প্রয়োজন হয়।

উদাহরণ:

```python
text = "Python"
data = b"Python"

print(text)
print(data)
print(type(text))
print(type(data))
```

Output:

```text
Python
b'Python'
<class 'str'>
<class 'bytes'>
```

এখানে:

- `str` হলো text data type।
- `bytes` হলো binary data সংরক্ষণের immutable type।
- `bytearray` হলো binary data সংরক্ষণের mutable type।

**মনে রাখবে:** `str`, `bytes` এবং `bytearray` দেখতে সম্পর্কিত হলেও এদের কাজ ও আচরণ এক নয়।

## 2. What Is a Byte?

একটি **byte সাধারণত 8 bits** নিয়ে গঠিত।

একটি bit-এর মান `0` অথবা `1` হতে পারে। তাই 8 bits দিয়ে \(2^8 = 256\)টি ভিন্ন combination তৈরি করা সম্ভব।

অর্থাৎ একটি byte-এর unsigned numerical value সাধারণত `0` থেকে `255` পর্যন্ত হয়।

উদাহরণ:

```python
data = bytes([65, 66, 67])

print(data)
```

Output:

```text
b'ABC'
```

এখানে ASCII-compatible encoding অনুযায়ী:

- `65` হলো `A`।
- `66` হলো `B`।
- `67` হলো `C`।

`bytes`-এর প্রতিটি element-এর numeric value `0` থেকে `255`-এর মধ্যে থাকে।

```python
data = bytes([65, 66, 67])

print(data[0])
print(data[1])
print(data[2])
```

Output:

```text
65
66
67
```

এখানে গুরুত্বপূর্ণ বিষয় হলো, `bytes`-এর indexing করলে `int` পাওয়া যায়, এক-character String নয়।

## 3. The `bytes` Data Type

`bytes` হলো একটি **immutable sequence of bytes**।

Immutable মানে object তৈরি হওয়ার পর এর individual byte পরিবর্তন করা যায় না।

### 3.1 Creating Bytes with a Prefix

Byte literal তৈরির জন্য String-এর আগে `b` ব্যবহার করা হয়।

```python
data = b"Hello"

print(data)
print(type(data))
```

Output:

```text
b'Hello'
<class 'bytes'>
```

এখানে `b` বোঝায় যে এটি সাধারণ String নয়, বরং `bytes` object।

### 3.2 Creating Bytes with `bytes()`

`bytes()` constructor বিভিন্ন উপায়ে ব্যবহার করা যায়।

একটি integer দিয়ে:

```python
data = bytes(5)

print(data)
```

Output:

```text
b'\x00\x00\x00\x00\x00'
```

এখানে পাঁচটি zero byte তৈরি হয়েছে।

Integer-এর List দিয়ে:

```python
data = bytes([65, 66, 67])

print(data)
```

Output:

```text
b'ABC'
```

প্রতিটি Integer `0` থেকে `255`-এর মধ্যে হতে হবে।

```python
data = bytes([65, 300])
```

এই code `ValueError` তৈরি করবে, কারণ `300` বৈধ byte value নয়।

Empty bytes:

```python
data = bytes()

print(data)
print(len(data))
```

Output:

```text
b''
0
```

### 3.3 Creating Bytes from a String

সাধারণ String-কে সরাসরি `bytes()` দিয়ে encode করা যায় না; এখানে encoding নির্দিষ্ট করতে হয়।

Incorrect:

```python
data = bytes("Python")
```

এটি `TypeError` তৈরি করবে।

Correct:

```python
text = "Python"

data = text.encode("utf-8")

print(data)
print(type(data))
```

Output:

```text
b'Python'
<class 'bytes'>
```

এখানে `encode()` String-কে UTF-8 encoding ব্যবহার করে bytes-এ রূপান্তর করেছে।

## 4. The `bytearray` Data Type

`bytearray` হলো একটি **mutable sequence of bytes**।

অর্থাৎ, এর individual byte পরিবর্তন করা যায়, নতুন byte যোগ করা যায় এবং byte বাদ দেওয়া যায়।

### 4.1 Creating a Bytearray

```python
data = bytearray([65, 66, 67])

print(data)
print(type(data))
```

Output:

```text
bytearray(b'ABC')
<class 'bytearray'>
```

এখানে `bytearray()` একটি mutable binary data object তৈরি করেছে।

### 4.2 Creating an Empty Bytearray

```python
data = bytearray()

print(data)
print(len(data))
```

Output:

```text
bytearray(b'')
0
```

### 4.3 Creating a Bytearray with a Size

```python
data = bytearray(4)

print(data)
```

Output:

```text
bytearray(b'\x00\x00\x00\x00')
```

এখানে চারটি zero byte তৈরি হয়েছে।

### 4.4 Creating a Bytearray from Bytes

```python
original = b"Hello"
data = bytearray(original)

print(data)
```

Output:

```text
bytearray(b'Hello')
```

এখানে original `bytes` object অপরিবর্তিত থাকে এবং একটি নতুন `bytearray` তৈরি হয়।

## 5. Difference Between `bytes` and `bytearray`

| Feature | `bytes` | `bytearray` |
|---|---|---|
| Nature | Immutable | Mutable |
| Modify an element | Not allowed | Allowed |
| Add or remove bytes | Cannot modify the object | Methods দিয়ে সম্ভব |
| Indexing | Integer return করে | Integer return করে |
| Slicing | `bytes` return করে | `bytearray` return করে |
| Common use | Read-only binary data | পরিবর্তনযোগ্য binary data |

Example:

```python
data = b"ABC"

data[0] = 88
```

এই code `TypeError` তৈরি করবে, কারণ `bytes` immutable।

অন্যদিকে:

```python
data = bytearray(b"ABC")

data[0] = 88

print(data)
```

Output:

```text
bytearray(b'XBC')
```

এখানে `65` (`A`) পরিবর্তন করে `88` (`X`) করা হয়েছে।

## 6. Indexing and Slicing

`bytes` এবং `bytearray` দুটোই sequence হওয়ায় indexing ও slicing support করে।

### 6.1 Indexing

```python
data = b"Python"

print(data[0])
print(data[1])
print(data[-1])
```

Output:

```text
80
121
110
```

এখানে প্রতিটি result হলো সংশ্লিষ্ট byte-এর numeric value।

### 6.2 Slicing Bytes

```python
data = b"Python"

print(data[0:3])
print(data[3:])
```

Output:

```text
b'Pyt'
b'hon'
```

Slicing-এর result একটি নতুন `bytes` object।

### 6.3 Slicing Bytearray

```python
data = bytearray(b"Python")

result = data[0:3]

print(result)
print(type(result))
```

Output:

```text
bytearray(b'Pyt')
<class 'bytearray'>
```

`bytearray`-এর slicing result-ও `bytearray`।

## 7. Modifying a Bytearray

`bytearray` mutable হওয়ায় এর data পরিবর্তন করা যায়।

### 7.1 Changing an Element

```python
data = bytearray(b"ABC")

data[1] = 90

print(data)
```

Output:

```text
bytearray(b'AZC')
```

এখানে দ্বিতীয় byte `66` থেকে `90` হয়েছে, যা ASCII-compatible encoding-এ `Z`।

### 7.2 Appending a Byte

`append()` দিয়ে একটি byte যোগ করা যায়।

```python
data = bytearray(b"AB")

data.append(67)

print(data)
```

Output:

```text
bytearray(b'ABC')
```

এখানে `67` হলো `C`-এর byte value।

`append()`-এ `0` থেকে `255`-এর মধ্যে একটি Integer দিতে হয়।

### 7.3 Extending a Bytearray

`extend()` দিয়ে একাধিক byte যোগ করা যায়।

```python
data = bytearray(b"AB")

data.extend([67, 68])

print(data)
```

Output:

```text
bytearray(b'ABCD')
```

### 7.4 Removing a Byte

```python
data = bytearray(b"ABC")

data.pop()

print(data)
```

Output:

```text
bytearray(b'AB')
```

`pop()` শেষ byte বাদ দেয় এবং সেটির Integer value return করে।

### 7.5 Clearing a Bytearray

```python
data = bytearray(b"Python")

data.clear()

print(data)
```

Output:

```text
bytearray(b'')
```

এখানে সব byte বাদ দেওয়া হয়েছে।

## 8. String, Bytes and Bytearray

এই তিনটি data type-এর পার্থক্য বোঝা খুব গুরুত্বপূর্ণ।

```python
text = "Hello"
data = b"Hello"
mutable_data = bytearray(b"Hello")

print(type(text))
print(type(data))
print(type(mutable_data))
```

Output:

```text
<class 'str'>
<class 'bytes'>
<class 'bytearray'>
```

- `str` সাধারণ text নিয়ে কাজ করে।
- `bytes` binary data সংরক্ষণ করে এবং immutable।
- `bytearray` binary data সংরক্ষণ করে এবং mutable।

সাধারণ String-এ Unicode text রাখা যায়। কিন্তু `bytes`-এর প্রতিটি element কেবল একটি byte value।

তাই বাংলা বা অন্য Unicode text-কে bytes-এ রূপান্তর করতে encoding ব্যবহার করতে হয়।

## 9. Character Encoding

**Character Encoding** হলো text character-কে byte-এ রূপান্তর করার নিয়ম।

কম্পিউটার binary data সংরক্ষণ করে। Text-কে file বা network-এর মাধ্যমে পাঠাতে হলে একটি নির্দিষ্ট encoding ব্যবহার করে text-কে bytes-এ রূপান্তর করা হয়।

Python-এ বহুল ব্যবহৃত encoding হলো UTF-8।

Example:

```python
text = "Hello"

data = text.encode("utf-8")

print(data)
```

Output:

```text
b'Hello'
```

এখানে প্রতিটি English character UTF-8 encoding অনুযায়ী bytes-এ রূপান্তরিত হয়েছে।

### 9.1 Encoding Unicode Text

```python
text = "বাংলা"

data = text.encode("utf-8")

print(data)
print(len(data))
```

Output:

```text
b'\xe0\xa6\xac\xe0\xa6\xbe\xe0\xa6\x82\xe0\xa6\xb2\xe0\xa6\xbe'
15
```

এই উদাহরণে `"বাংলা"` String-এর character-গুলো UTF-8-এ মোট 15 byte ব্যবহার করেছে।

**গুরুত্বপূর্ণ:** একটি character সব সময় একটি byte ব্যবহার করে না। UTF-8-এ character অনুযায়ী এক বা একাধিক byte লাগতে পারে।

## 10. Decoding Bytes into a String

**Decoding** হলো নির্দিষ্ট encoding ব্যবহার করে bytes-কে আবার text-এ রূপান্তর করা।

```python
text = "বাংলা"

data = text.encode("utf-8")
decoded_text = data.decode("utf-8")

print(decoded_text)
```

Output:

```text
বাংলা
```

এখানে:

1. `encode("utf-8")` String-কে bytes-এ রূপান্তর করেছে।
2. `decode("utf-8")` bytes-কে আবার String-এ রূপান্তর করেছে।

সঠিক ফল পেতে decoding-এর সময় উপযুক্ত encoding ব্যবহার করা জরুরি।

### Invalid Decoding

```python
data = b"\xff"

text = data.decode("utf-8")
```

এই code `UnicodeDecodeError` তৈরি করবে, কারণ `b"\xff"` একা একটি valid UTF-8 sequence নয়।

অর্থাৎ, যেকোনো bytes-কে ইচ্ছামতো encoding দিয়ে decode করা যায় না।

## 11. Encoding and Decoding Methods

| Method | কাজ |
|---|---|
| `str.encode()` | String-কে bytes-এ রূপান্তর করে |
| `bytes.decode()` | Bytes-কে String-এ রূপান্তর করে |
| `bytearray.decode()` | Bytearray-কে String-এ রূপান্তর করে |

Example:

```python
text = "Python"

data = text.encode("utf-8")
decoded = data.decode("utf-8")

print(data)
print(decoded)
```

Output:

```text
b'Python'
Python
```

Default encoding নির্ভর করে method ও environment-এর ওপর; শেখার সময় encoding স্পষ্টভাবে `"utf-8"` উল্লেখ করা ভালো।

## 12. Concatenation and Repetition

`bytes` এবং `bytearray`-এর মধ্যে একই ধরনের data দিয়ে concatenation ও repetition করা যায়।

### 12.1 Concatenation

```python
a = b"Hello "
b = b"Python"

result = a + b

print(result)
```

Output:

```text
b'Hello Python'
```

### 12.2 Repetition

```python
data = b"AB"

print(data * 3)
```

Output:

```text
b'ABABAB'
```

`bytes` ও `bytearray` একসঙ্গে সরাসরি concatenation করলে type mismatch হতে পারে।

```python
a = b"Hello"
b = bytearray(b"World")

result = a + b
```

এই code `TypeError` তৈরি করবে।

প্রয়োজন হলে উভয় operand-কে একই type-এ রূপান্তর করে নিতে হবে।

## 13. Comparing Bytes

`bytes` object-কে তুলনা করা যায়।

```python
a = b"ABC"
b = b"ABC"
c = b"ABD"

print(a == b)
print(a == c)
```

Output:

```text
True
False
```

`bytes`-এর equality comparison content-এর ওপর নির্ভর করে।

Byte value-এর ক্রম অনুযায়ী ordering comparison-ও করা যায়।

```python
print(b"ABC" < b"ABD")
```

Output:

```text
True
```

তবে এই comparison মানুষের ভাষায় শব্দের অর্থ বা Unicode text-এর linguistic sorting বোঝায় না; এটি byte sequence-এর lexicographical comparison।

## 14. Common Uses of Bytes and Bytearray

### 14.1 Reading Binary Files

Image, audio, PDF এবং অন্যান্য binary file নিয়ে কাজ করার সময় bytes ব্যবহার করা হয়।

```python
with open("example.bin", "rb") as file:
    data = file.read()

print(type(data))
```

যদি file সফলভাবে পড়া যায়, output হবে:

```text
<class 'bytes'>
```

এখানে `"rb"` অর্থ হলো read binary mode।

### 14.2 Writing Binary Files

```python
data = b"Hello Python"

with open("example.bin", "wb") as file:
    file.write(data)
```

এখানে `"wb"` হলো write binary mode। এটি file-এ binary data লেখে এবং আগে থেকে থাকা file content overwrite করতে পারে।

### 14.3 Network Communication

Network protocol ও socket programming-এ data প্রায়ই bytes আকারে পাঠানো ও গ্রহণ করা হয়।

```python
message = "Hello Server"

data = message.encode("utf-8")
```

এখানে text-কে network transmission-এর উপযোগী bytes-এ রূপান্তর করা হয়েছে।

### 14.4 Binary Data Processing

যখন কোনো binary data-এর byte পরিবর্তন করতে হয়, তখন `bytearray` কাজে লাগে।

```python
data = bytearray([10, 20, 30])

data[0] = 99

print(data)
```

Output:

```text
bytearray(b'\nc\x1e')
```

এখানে byte value-গুলো যথাক্রমে `99`, `20` ও `30`। Printable character না হলে Python `\x` escape notation ব্যবহার করতে পারে।

## 15. Common Beginner Mistakes

### Mistake 1: Confusing String and Bytes

```python
text = "Hello"
data = b"Hello"

print(text == data)
```

Output:

```text
False
```

একই রকম text দেখালেও `str` এবং `bytes` ভিন্ন type।

### Mistake 2: Trying to Modify Bytes

```python
data = b"ABC"

data[0] = 90
```

এটি `TypeError` তৈরি করবে। পরিবর্তনযোগ্য binary data প্রয়োজন হলে `bytearray` ব্যবহার করো।

### Mistake 3: Using an Invalid Byte Value

```python
data = bytes([10, 300])
```

এটি `ValueError` তৈরি করবে। প্রতিটি Integer `0` থেকে `255`-এর মধ্যে হতে হবে।

### Mistake 4: Forgetting Encoding

```python
text = "Hello"

data = bytes(text)
```

এটি `TypeError` তৈরি করবে। String থেকে bytes পেতে:

```python
data = text.encode("utf-8")
```

### Mistake 5: Using the Wrong Encoding During Decoding

```python
text = "বাংলা"
data = text.encode("utf-8")
decoded = data.decode("ascii")
```

এটি `UnicodeDecodeError` তৈরি করবে, কারণ UTF-8-এ থাকা এই bytes-গুলো ASCII হিসেবে valid নয়।

সঠিক encoding ব্যবহার করো:

```python
decoded = data.decode("utf-8")
```

### Mistake 6: Assuming One Character Equals One Byte

```python
text = "A"
data = text.encode("utf-8")

print(len(data))
```

Output:

```text
1
```

কিন্তু:

```python
text = "অ"
data = text.encode("utf-8")

print(len(data))
```

Output:

```text
3
```

UTF-8-এ এই বাংলা character তিনটি byte ব্যবহার করে। তাই character-এর সংখ্যা এবং byte-এর সংখ্যা এক নাও হতে পারে।

## 16. Practice Exercises

### Exercise 1: Create Bytes

`bytes()` ব্যবহার করে `[65, 66, 67]` থেকে একটি bytes object তৈরি করো। এর type এবং প্রতিটি byte-এর numeric value print করো।

### Exercise 2: Create a Bytearray

`bytearray()` ব্যবহার করে `b"Python"` থেকে একটি object তৈরি করো। প্রথম byte পরিবর্তন করে `P`-এর পরিবর্তে `J` করো।

Expected output:

```text
bytearray(b'Jython')
```

### Exercise 3: Compare Mutability

একটি `bytes` এবং একটি `bytearray` তৈরি করো। দুটির প্রথম byte পরিবর্তনের চেষ্টা করে ফলাফল তুলনা করো।

### Exercise 4: Encoding

`"Hello Python"` String-কে UTF-8 দিয়ে bytes-এ রূপান্তর করো। Bytes-এর type এবং length print করো।

### Exercise 5: Decode Bengali Text

`"বাংলাদেশ"` String-কে UTF-8 দিয়ে encode করো, তারপর decode করে original text ফিরে পাও।

### Exercise 6: Bytearray Operations

```python
data = bytearray([10, 20, 30])
```

- `append()` দিয়ে `40` যোগ করো।
- `extend()` দিয়ে `50` ও `60` যোগ করো।
- একটি element পরিবর্তন করো।
- `pop()` দিয়ে শেষ byte বাদ দাও।

### Exercise 7: Binary File

`"Hello Python"`-কে UTF-8 bytes-এ রূপান্তর করে `"example.bin"` file-এ binary mode-এ লেখো। এরপর file-টি `"rb"` mode-এ পড়ে content decode করো।

### Exercise 8: Understand Byte Length

`"A"`, `"বাংলা"` এবং `"Python"`-কে UTF-8 দিয়ে encode করো। প্রতিটি String-এর character count (`len(text)`) ও byte count (`len(text.encode("utf-8"))`) তুলনা করো।

### Exercise 9: Valid and Invalid Bytes

`bytes([0, 100, 255])` এবং `bytes([256])` চালিয়ে দেখো। দুটি expression-এর ফলাফলের পার্থক্য ব্যাখ্যা করো।

### Exercise 10: Mini Project — Text to Binary and Back

একটি program তৈরি করো, যা:

1. User-এর কাছ থেকে text নেবে।
2. Text-কে UTF-8 bytes-এ encode করবে।
3. Encoded data print করবে।
4. Bytes-কে আবার decode করবে।
5. Original ও decoded text একই কি না পরীক্ষা করবে।

## 17. Key Takeaways

- `bytes` এবং `bytearray` binary data সংরক্ষণের built-in data type।
- `bytes` immutable, কিন্তু `bytearray` mutable।
- প্রতিটি byte-এর numeric value `0` থেকে `255`-এর মধ্যে থাকে।
- `bytes` ও `bytearray` indexing করলে Integer পাওয়া যায়।
- `str` থেকে bytes-এ যেতে `encode()` ব্যবহার করা হয়।
- Bytes থেকে text-এ ফিরতে `decode()` ব্যবহার করা হয়।
- UTF-8 text encoding-এর একটি বহুল ব্যবহৃত standard।
- একটি Unicode character একাধিক byte ব্যবহার করতে পারে।
- Binary file পড়তে `"rb"` এবং লিখতে `"wb"` ব্যবহার করা হয়।
- Network communication ও binary file processing-এ bytes গুরুত্বপূর্ণ।

## 18. Next Topic

পরবর্তী ফাইল:

**`19_Introduction_to_Type_Conversion.md`**

সেখানে Type Conversion কী, কেন প্রয়োজন, Implicit ও Explicit Conversion-এর পার্থক্য এবং Python-এ data type পরিবর্তনের নিয়ম শেখা হবে।