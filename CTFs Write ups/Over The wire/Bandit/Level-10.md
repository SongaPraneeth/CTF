**Level Goal :**

The password for the next level is stored in the file **data.txt**, which contains base64 encoded data.

Steps to solve:

step1: Use `base64 -d data.txt` to get the password

![image alt](https://github.com/SongaPraneeth/CTF/blob/fae3ccfc95a09337a2390be80f1cf34fbe0b90ce/CTFs%20Write%20ups/images/bandit_images/bandit10.png)

### Command:

```bash
base64 -d data.txt
```

### What it does:

This command **decodes** Base64-encoded data stored in the file `data.txt`.

---

### Breaking it down:

### `base64`

- A command-line tool to **encode** or **decode** data in Base64 format.

### `d`

- Stands for **decode**.
- Tells the command to **convert Base64 back to normal (original) text or binary**.

### `data.txt`

- The input file that contains the Base64-encoded text.