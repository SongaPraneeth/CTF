**Description:**

I wonder what this really is... enc ''.join([chr((ord(flag[i]) << 8) + ord(flag[i + 1])) for i in range(0, len(flag), 2)])

`Steps to solve:`

step1: Open `enc` file using command `cat enc` and you will find some Chinese like characters.

step2: Now we have also given a `code`, which is shifting the first letter `8 bits` to the left and then `adding` the second letter, for each two letters in the string. As we know that each character is 8 bits long

step3: Now lets run the given code,

lets take `flag = picoCTF{.}` and `word = “”`

and make small changes in the given code and here we will see that the flag is changed into the characters in the `enc` file

```python
flag = 'picoCTF{.}'
word = ""

for i in range(0, len(flag), 2):
  word += chr((ord(flag[i]) << 8) + ord(flag[i + 1]))

print(word) #output is : 灩捯䍔䙻⹽
```

Let’s say your `flag` starts with `"pi"`.

So:

```python
flag[i]     = 'p'
flag[i + 1] = 'i'

```

We’ll now look at:

```python
chr((ord('p') << 8) + ord('i'))

```

---

## 1️⃣ Step 1: Convert each character to its ASCII number

| Character | ASCII (Decimal) | Binary (8 bits) |
| --- | --- | --- |
| `'p'` | 112 | `01110000` |
| `'i'` | 105 | `01101001` |

---

## 2️⃣ Step 2: Shift `'p'` left by 8 bits (`<< 8`)

When you do `ord('p') << 8`,

it’s like moving `'p'` to the **upper 8 bits** of a 16-bit number.

```
01110000 00000000

```

Decimal value:

```
112 × 256 = 28672

```

---

## 3️⃣ Step 3: Add `ord('i')` (the low 8 bits)

```
01110000 00000000   (28672)
+          01101001 (105)
------------------
01110000 01101001   (28777)

```

So now, the **combined 16-bit binary** = `01110000 01101001`

Decimal value:

```
28672 + 105 = 28777

```

---

## 4️⃣ Step 4: Convert 28777 to a Unicode character

```python
chr(28777)  →  '灩'

```

✅ So `'灩'` is a single Unicode character that internally represents both `'p'` and `'i'`.

---

## 🧠 Visualization

| Part | Meaning | Binary (16 bits) | Decimal |
| --- | --- | --- | --- |
| `'p'` high byte | `01110000` |  | 112 |
| `'i'` low byte | `01101001` |  | 105 |
| Combined | `01110000 01101001` | 28777 |  |
| Unicode char | `'灩'` |  |  |

So `'灩'` is **made of both 'p' and 'i' packed together** — `'p'` in the high byte and `'i'` in the low byte.

---

## 5️⃣ Step 5: What happens if we decode?

To get `'p'` and `'i'` back:

```python
ord('灩') >> 8          # gives 112 ('p')
ord('灩') - (112 << 8)  # gives 105 ('i')

```

Boom 💥 — back to `'pi'`.

---

### 🔁 Summary of `chr((ord(flag[i]) << 8) + ord(flag[i+1]))`

| Step | Operation | Meaning |
| --- | --- | --- |
| `ord(flag[i])` | Convert 1st char → number |  |
| `<< 8` | Move to upper 8 bits |  |
| `+ ord(flag[i+1])` | Add 2nd char in lower 8 bits |  |
| `chr(...)` | Turn 16-bit value into one Unicode symbol |  |

step4: Now we have understood the mechanism, now we just have to reverse it, for this, i have written code: 

```python
encoded = "灩捯䍔䙻ㄶ形楴獟楮獴㌴摟潦弸弰㑣〷㘰摽"
decoded = ''
for i in range(len(encoded)):
  a = chr(ord(encoded[i]) >> 8)
  flag = chr(ord(encoded[i])- (ord(a) << 8))
  decoded = decoded + (a + flag)

print(decoded) #out put is : picoCTF{16_bits_inst34d_of_8_04c0760d}
```

Now lets understand, how the code is working internally:

## 🧠 Step-by-step explanation

### 1️⃣ The `encoded` string

This strange string —

```
灩捯䍔䙻ㄶ形楴獟楮獴㌴摟潦弸弰㑣〷㘰摽

```

— looks like random Chinese characters, but each of those characters **actually hides two English letters** inside it!

Each one is a **16-bit Unicode number**, made by combining two 8-bit ASCII letters.

---

### 2️⃣ Looping through each encoded character

```python
for i in range(len(encoded)):

```

Each time, `encoded[i]` is one of those strange characters:

```
'灩', '捯', '䍔', ...

```

---

### 3️⃣ `ord(encoded[i])`

`ord()` gives you the Unicode code (a number) for that character.

Example:

```python
ord('灩') = 28777

```

So now, `28777` is a 16-bit number made from two 8-bit letters.

Let’s see how.

---

### 4️⃣ How the packing was done earlier (for understanding)

When the original message (like `"pi"`) was encoded, it was done like this:

```python
encoded_char = chr((ord('p') << 8) + ord('i'))

```

Let’s calculate that:

| Character | ASCII | Binary (8 bits) |
| --- | --- | --- |
| `'p'` | 112 | `01110000` |
| `'i'` | 105 | `01101001` |

When you shift `'p'` left 8 bits (`112 << 8`), you get:

```
01110000 00000000

```

Then add `'i'`:

```
01110000 01101001

```

That’s one 16-bit number = `28777`, which corresponds to `'灩'`.

---

### 5️⃣ Now we reverse that process (decode)

### Step A:

```python
a = chr(ord(encoded[i]) >> 8)

```

Let’s plug in our example with `'灩'`:

```
ord('灩') = 28777
28777 >> 8 = 112
chr(112) = 'p'

```

So `a = 'p'`.

✅ This extracts the **first (high)** byte — `'p'`.

---

### Step B:

```python
flag = chr(ord(encoded[i]) - (ord(a) << 8))

```

Let’s plug in numbers again:

```
ord('encoded[i]') = 28777
ord(a) = 112
ord(a) << 8 = 112 * 256 = 28672
28777 - 28672 = 105
chr(105) = 'i'

```

✅ So `flag = 'i'`.

That gives us the **second (low)** byte.

---

### Step C:

```python
decoded = decoded + (a + flag)

```

Now we add `'p' + 'i'` → `"pi"` to our result string.

---

### 6️⃣ This repeats for every encoded symbol

| Encoded | ord() | → `>>8` (high) | → `- (high<<8)` (low) | Adds to decoded |
| --- | --- | --- | --- | --- |
| `'灩'` | 28777 | `'p'` | `'i'` | `"pi"` |
| `'捯'` | 25583 | `'c'` | `'o'` | `"co"` |
| `'䍔'` | 19540 | `'C'` | `'T'` | `"CT"` |
| ... | ... | ... | ... | ... |

---

### 7️⃣ Final Output

After the whole loop finishes, `decoded` becomes:

```
picoCTF{16_bits_inst34d_of_8_byt3s_3070db}

```

🎉 That’s the hidden message!

---

## 🔍 What’s really happening inside (visually)

Each “weird” symbol hides 2 normal letters like this:

```
灩 → 01110000 01101001 → 'p' 'i'
捯 → 01100011 01101111 → 'c' 'o'
䍔 → 01000011 01010100 → 'C' 'T'
䙻 → 01000110 01111011 → 'F' '{'

```

Then the loop:

- Extracts the **left 8 bits** (`>> 8`) → first letter
- Extracts the **right 8 bits** (`(left<<8)`) → second letter

Combining all gives you the original ASCII message.

![image alt](https://github.com/SongaPraneeth/CTF/blob/f4ed576e8314c51fd25e5140d1b2c712fc7ee648/CTFs%20Write%20ups/images/picoctf_images/Reverse/Easy/Transformation_3.png)

![image alt](https://github.com/SongaPraneeth/CTF/blob/f4ed576e8314c51fd25e5140d1b2c712fc7ee648/CTFs%20Write%20ups/images/picoctf_images/Reverse/Easy/Transformation_1.png)

![image alt](https://github.com/SongaPraneeth/CTF/blob/f4ed576e8314c51fd25e5140d1b2c712fc7ee648/CTFs%20Write%20ups/images/picoctf_images/Reverse/Easy/Transformation_2.png)