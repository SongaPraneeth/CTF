**Level Goal:**

The password for the next level is stored in the file **data.txt** in one of the few human-readable strings, preceded by several ‘=’ characters.

Steps to solve:

step1 : Use `strings data.txt | grep "==="` to find the password

![image alt](https://github.com/SongaPraneeth/CTF/blob/fae3ccfc95a09337a2390be80f1cf34fbe0b90ce/CTFs%20Write%20ups/images/bandit_images/bandit9.png)

### Command:

```bash
strings data.txt | grep "==="

```

### What it does:

It looks inside `data.txt` for **any readable line that contains `===`**, even if `data.txt` is a binary or non-text file.

---

### Breaking it down:

### `strings data.txt`

- This extracts **printable (readable) text** from `data.txt`.
- It's useful when the file is **not a normal text file** — for example, a binary or encrypted file.
- It ignores unreadable characters and shows only words or strings that make sense.

### `|` (pipe)

- Sends the readable output from `strings` directly into `grep`.

### `grep "==="`

- Searches for **lines that contain exactly `===`**.
- Only lines with `===` in them will be shown.