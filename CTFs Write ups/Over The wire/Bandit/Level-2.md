**Level Goal:**

The password for the next level is stored in a file called `--spaces in this filename--` located in the home directory.

Steps to solve:

step1 : Use `ls` to find the file

step2 : Then use `cat ./--spaces\ in\ this\ filename--` command to read the file

![image alt](https://github.com/SongaPraneeth/CTF/blob/fae3ccfc95a09337a2390be80f1cf34fbe0b90ce/CTFs%20Write%20ups/images/bandit_images/bandit2.png)

Let's break down **this exact command**:

```bash
cat ./--spaces\ in\ this\ filename--

```

---

## ✅ What it does :

This command **reads a file** named:

```
--spaces in this filename--

```

...and **prints its content** to the screen.

## 🧱 Explanation of each part:

| Part | Meaning |
| --- | --- |
| `cat` | Command to **print the contents** of a file. |
| `./` | Means “**current directory**” — look for the file here. |
| `--spaces\ in\ this\ filename--` | This is the **filename**, but the **spaces are escaped** using `\` so the shell treats it as **one word**. |

---

## 🚨 Why use `\` before spaces?

In the terminal, **spaces normally separate words** (or commands and arguments).

So if you wrote:

```bash
cat ./--spaces in this filename--

```

The shell would see **5 different arguments**, not one filename — and you'd get an error.

To fix that, you **escape** the spaces with a backslash `\`:

```bash
--spaces\ in\ this\ filename--

```

This tells the shell:

🗣️ “These spaces are part of the name. Don’t split them.”

---

## ✅ This works exactly the same as:

```bash
cat "./--spaces in this filename--"

```

Both are correct — use **either quotes** or **backslashes** to handle filenames with spaces.

---

## TL;DR:

- `cat` = show file contents.
- `./` = current directory.
- `\` escapes spaces so the shell treats the filename correctly.
- Used when a file **has spaces in its name**.