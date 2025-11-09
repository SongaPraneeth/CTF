**Level Goal:**

The password for the next level is stored in the only human-readable file in the **inhere** directory

Steps to solve:

step1 : Use `ls` to find the inhere directory

step2 : use `cd inhere` to enter the directory

step3 : use `ls` to list the files in the directory

step4 : Now use `file` command to find the human-readable file 

step5: After finding the human readable file use `cat ./file_name` to read the file

![image alt](https://github.com/SongaPraneeth/CTF/blob/fae3ccfc95a09337a2390be80f1cf34fbe0b90ce/CTFs%20Write%20ups/images/bandit_images/bandit4.png)

Let's break down the command:

```
file ./-file07

```

This command is used in **Unix/Linux** systems to determine the **type of a file**. Here's what each part means:

### 1. `file`

- This is the command used to find out **what kind of file** something is (e.g., text file, image, executable, etc.).
- It doesn’t care about the file name extension — it looks at the actual **content**.

### 2. `./-file07`

- This refers to a **file named `file07`** that is in the **current directory** (`./` means "current directory").

### So what's the tricky part?

Normally, filenames starting with a `-` are treated as **options or flags** by commands. For example:

```
file -v

```

That would show the version of the `file` command.

But in your case, the file name **starts with a dash** (`-file07`), so to prevent the command from thinking it’s an option, you tell it explicitly:

- `./-file07` → means “this is a file in the current directory, and its name really does start with a dash.”

---

### ✅ In simple terms:

You're using the `file` command to check what kind of file `-file07` is, and you're being careful to avoid confusing the command by writing `./-file07`.