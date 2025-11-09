**Level Goal :** 

The password for the next level is stored in the file **data.txt** and is the only line of text that occurs only once

steps to solve:

 step 1 : Use `sort data.txt | uniq -u` to find the password

![image alt](https://github.com/SongaPraneeth/CTF/blob/fae3ccfc95a09337a2390be80f1cf34fbe0b90ce/CTFs%20Write%20ups/images/bandit_images/bandit8.png)

## Command:

```bash
sort data.txt | uniq -u
```

## What it does:

This command finds and prints **only the lines that appear exactly once** in `data.txt`.

---

## Step-by-step Explanation:

### 1. `sort data.txt`

- This **sorts** all the lines in `data.txt` **alphabetically**.
- Sorting is necessary because `uniq` only works on **adjacent** (neighboring) lines.

### 2. `|` (pipe)

- Sends the **output of `sort`** directly into the next command (`uniq -u`).

### 3. `uniq -u`

- Filters out all **repeated lines**.
- It only keeps **unique lines** — lines that occur **once and only once**.