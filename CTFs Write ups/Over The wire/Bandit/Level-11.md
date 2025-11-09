Level Goal :

The password for the next level is stored in the file **data.txt**, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions

Steps to solve:

step1: Use `cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'` to get the password

![image alt](https://github.com/SongaPraneeth/CTF/blob/fae3ccfc95a09337a2390be80f1cf34fbe0b90ce/CTFs%20Write%20ups/images/bandit_images/bandit11.png)

You're using the following command:

```bash
cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
```

### In simple terms:

This reads the contents of `data.txt` and **decodes or encodes it using the ROT13 cipher**, which shifts letters by 13 positions in the alphabet.

---

### Step-by-step explanation:

### 1. `cat data.txt`

- Displays the content of the file `data.txt`.

### 2. `|` (pipe)

- Passes the output (text from the file) to the next command.

### 3. `tr 'A-Za-z' 'N-ZA-Mn-za-m'`

- Translates each letter:
    - `A-Z` → `N-ZA-M` (uppercase letters rotated by 13)
    - `a-z` → `n-za-m` (lowercase letters rotated by 13)
- Numbers, punctuation, and spaces are **not changed**.