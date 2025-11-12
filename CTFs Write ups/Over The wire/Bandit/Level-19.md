Level Goal : 

To gain access to the next level, you should use the setuid binary in the homedirectory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (/etc/bandit_pass), after you have used the setuid binary.

Steps to solve :

step1: use ls to find the setuid binary

step2: use command `./bandit20-do cat /etc/bandit_pass/bandit20` to get the password

![image alt](https://github.com/SongaPraneeth/CTF/blob/3d95217f6498d1b845e4fcc465afe215e5eea7c1/CTFs%20Write%20ups/images/bandit_images/bandit19.png)

the command:

```bash
./bandit20-do cat /etc/bandit_pass/bandit20

```

This command is central to **Bandit Level 20**, and it uses a **setuid binary** to access something you normally can’t.

---

## 🔍 Full Breakdown:

### 🧩 1. `./bandit20-do`

- `./` means: run the file named `bandit20-do` in **the current directory**.
- `bandit20-do` is a **setuid binary**, meaning:
    - It's an executable file that **runs with the permissions of its owner**, no matter who launches it.
    - It is owned by the user `bandit20`, so when you run it, **you temporarily have the permissions of `bandit20`**, just for the command it runs.

✅ **Purpose**: It lets you run a command **as user `bandit20`**, which is normally not allowed.

---

### 🧩 2. `cat`

- `cat` is a standard Linux command that **reads and prints the contents** of a file to the terminal.
- Example:
    
    ```bash
    cat file.txt
    
    ```
    
    This would print the contents of `file.txt`.
    

---

### 🧩 3. `/etc/bandit_pass/bandit20`

- This is the **file** containing the password for the next level (`bandit21`).
- It is **only readable by user `bandit20`**, not by your current user.

---

## 🧠 Putting It All Together

```bash
./bandit20-do cat /etc/bandit_pass/bandit20

```

Means:

> "Use the bandit20-do program to run the command cat /etc/bandit_pass/bandit20 as user bandit20, so I can read the password file."
> 

## ❌ **The Problem**

You **can't directly read** that file with your current user (which is `bandit20`), because you **don’t have permission** to do so.

If you try:

```bash
cat /etc/bandit_pass/bandit20

```

You get:

```
Permission denied

```

---

## ✅ **The Solution**

You're given a **special program** in your home directory:

```bash
./bandit20-do

```

This program is **Set-UID**, meaning:

- Even though *you* run it, it runs as **user `bandit20`**.
- It lets you run **one command as user `bandit20`** (you’re temporarily "impersonating" `bandit20`).

Since the file `/etc/bandit_pass/bandit20` is **owned by `bandit20`**, this program gives you a way to access it.

---

## 🔍 Step-by-Step Instructions

### 1. Try running it without arguments:

```bash
./bandit20-do

```

You will see something like:

```
Run a command as another user.
Usage: ./bandit20-do <command>

```

It tells you: **give it a command**, and it will run that command **as `bandit20`**.

---

### 2. Run the `cat` command through it:

```bash
./bandit20-do cat /etc/bandit_pass/bandit20

```

This tells the `bandit20-do` program:

> "Please run cat /etc/bandit_pass/bandit20 as user bandit20"
> 

✅ And it works! You saw the output:

```
0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO

```

This is the password for the **next level**.