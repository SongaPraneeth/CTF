**Level Goal :**

The password for the next level is stored in a file somewhere under the **inhere** directory and has all of the following properties:

- human-readable
- 1033 bytes in size
- not executable

Steps to solve:

step1 : Use `ls` to find inhere directory

stpe2 : Use `cd inhere` to enter the directory

step3 : Now use `ls` to list all the files or directories

step4 : Now use `find -readable -size 1033c -not -executable`  command to find the file

step5 : use `cat` to read the file

![image alt](https://github.com/SongaPraneeth/CTF/blob/fae3ccfc95a09337a2390be80f1cf34fbe0b90ce/CTFs%20Write%20ups/images/bandit_images/bandit5.png)

or 

We can directly use the `find -readable -size 1033c -not -executable` command instead of first 3 steps.

![image alt](https://github.com/SongaPraneeth/CTF/blob/fae3ccfc95a09337a2390be80f1cf34fbe0b90ce/CTFs%20Write%20ups/images/bandit_images/bandit5.1.png)

```bash
find -readable -size 1033c -not -executable
```

This command is used in Linux to search for files that meet specific conditions.

🧱 Breaking it Down:

### 1. `find`

- This is the **command** used to **search for files and directories**.
- By default, it starts searching in the **current directory and all subdirectories**.

---

### 2. `readable`

- Only find files that are **readable** (you have permission to read them).

---

### 3. `size 1033c`

- Only find files that are exactly **1033 bytes** in size.
- `c` means “**bytes**” (1 byte = 1 character for most text files).

---

### 4. `not -executable`

- Only find files that are **not executable** (you can't run them like a program or script).

---

## 🧠 In simple terms:

> "Find all files in the current directory (and below) that I can read, that are exactly 1033 bytes in size, and that are not executable."
> 

Let's break down the command:

```bash
cat ./inhere/maybehere07/.file2

```

into its **parts**, and explain **each one in simple terms**:

---

### 🧱 1. `cat`

- Stands for **concatenate**.
- It's a command used to **read and display the contents of a file**.
- Example: If the file contains a password or some text, `cat` will show it in your terminal.

---

### 📁 2. `./`

- Means: **"current directory"**.
- You're telling the shell to **start looking from your current location**.
- It helps especially when working with files or folders that have special characters (like `.` or ) in their names.

---

### 📂 3. `inhere/maybehere07/`

- This is a **path to a subfolder**.
- `inhere` is a folder inside your current directory.
- `maybehere07` is another folder **inside** `inhere`.

So you’re going into:

```bash
current directory → inhere → maybehere07

```

---

### 📄 4. `.file2`

- This is the **actual file name**.
- It starts with a dot (`.`), which makes it a **hidden file** in Linux/Unix.
- Hidden files are not shown by default when you run `ls`, unless you use `ls -a`.

---

### ✅ Full Meaning:

When you put it all together:

```bash
cat ./inhere/maybehere07/.file2

```

You're saying:

> "Display the contents of the hidden file named .file2, which is located in the maybehere07 folder inside the inhere folder in the current directory."
>