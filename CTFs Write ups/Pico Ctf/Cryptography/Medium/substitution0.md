**Description:**

A message has come in but it seems to be all scrambled. Luckily it seems to have the key at the beginning. Can you crack this substitution cipher? Download the message here.

**Steps to solve:**

step1: Open the file using command cat message.txt

step2: Now as we know that it is a substitution cipher, we also have a key, so lets use an online website that decodes and get us the flag. the website is https://cryptii.com/pipes/alphabetical-substitution 

step3: With the above steps you will get the flag, but i have written a code that decodes the substitution cipher with inputs key and cipher text.

![image alt](https://github.com/SongaPraneeth/CTF/blob/5da6ccb7470e936926e10ee59020db1a60989148/CTFs%20Write%20ups/images/picoctf_images/Crypto/Medium/substitution0_1.png)

![image alt](https://github.com/SongaPraneeth/CTF/blob/5da6ccb7470e936926e10ee59020db1a60989148/CTFs%20Write%20ups/images/picoctf_images/Crypto/Medium/substitution0_2.png)

I have written a code for the substitution cipher with decodes with key and cipher text:

```python
import string

upper_letter = list(string.ascii_uppercase)
lower_letter = list(string.ascii_lowercase)

ciphertext = input("enter the cipher text: ")
key = input("Enter the key: ")
key_small = key.lower()

plain_text = ''

for i in ciphertext:
  if i.islower():
    indexinkeysmall = key_small.index(i)
    plain_text += lower_letter[indexinkeysmall]
  
  elif i.isupper():
    indexinkey = key.index(i) 
    plain_text += upper_letter[indexinkey]
    
  else:
    plain_text += i
    
    
print(plain_text)
```

Before explanation of code lets understand Substitution cipher, This cipher encrypt the text by replacing each character with another character of the key. And the key always will be 26 characters because we are taking alphabets.

lets say : 

`key` = EFGHIKLMNOPQRSTUVWXYZABCD

now if you want to encrypt a message let's take : `HELLO`

Now: 

A → E
B → F
C → G
D → H
E → I
F → J
G → K
H → L
I → M
J → N
K → O
L → P
M → Q
N → R
O → S
P → T
Q → U
R → V
S → W
T → X
U → Y
V → Z
W → A
X → B
Y → C
Z → D

So, for `HELLO`

H  → L

E  → I

L  → P

L  → P

O → S

encrypted = `LIPPS`

so, to decrypt the cipher text `LIPPS`, we need the same `key`:

Now :

E → A
F → B
G → C
H → D
I → E
J → F
K → G
L → H
M → I
N → J
O → K
P → L
Q → M
R → N
S → O
T → P
U → Q
V → R
W → S
X → T
Y → U
Z → V
A → W
B → X
C → Y
D → Z

So, for `LIPPS`

L  → H

I  → E

P  → L

P  → L

S  → O

decrypted = `HELLO`

## **Code Explanation**

### 1. Importing and preparing alphabets

```python
upper_letter = list(string.ascii_uppercase)
lower_letter = list(string.ascii_lowercase)

```

**Explanation:**

- `string.ascii_uppercase` gives: `ABCDEFGHIJKLMNOPQRSTUVWXYZ`
- `string.ascii_lowercase` gives: `abcdefghijklmnopqrstuvwxyz`
- Converting them to lists allows us to access letters by index.

You use these lists during decryption to **map the position of a ciphertext letter back to the original plaintext letter**.

In simple words:

**These lists help you find which plaintext letter corresponds to each ciphertext letter using its index.**

### 2. Taking user input

```python
ciphertext = input("enter the cipher text: ")
key = input("Enter the key: ")
key_small = key.lower()

```

- `ciphertext`: the encrypted text
- `key`: substitution key
- `key_small`: for matching lowercase letters when decrypting

### 3. Prepare an empty string

```python
plain_text = ''

```

### 4. Decryption logic

```python
for i in ciphertext:
    if i.islower():
        indexinkeysmall = key_small.index(i)
        plain_text += lower_letter[indexinkeysmall]

```

- Find the index of ciphertext letter in the key
- The index tells which plaintext letter it corresponds to
- Add that to plaintext letter

Uppercase works the same way:

```python
elif i.isupper():
    indexinkey = key.index(i)
    plain_text += upper_letter[indexinkey]

```

If the character is not a letter (e.g., space, number, punctuation), add it directly:

```python
else:
    plain_text += i

```

### 5. Final output

```python
print(plain_text)

```

When the code is executed we got the expected output:

![image alt](https://github.com/SongaPraneeth/CTF/blob/5da6ccb7470e936926e10ee59020db1a60989148/CTFs%20Write%20ups/images/picoctf_images/Crypto/Medium/substitution0_3.png)