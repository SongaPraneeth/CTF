**Level Goal :**

The password for the next level is stored in a hidden file in the **inhere** directory.

Steps to solve:

step1: Use `ls` to find the directory

step2 : Now use `cd inhere` command to enter the directory

step3 : Now use `ls -asl` to find the hidden file 

step3 : use `cat`   to read the file

![image alt](https://github.com/SongaPraneeth/CTF/blob/fae3ccfc95a09337a2390be80f1cf34fbe0b90ce/CTFs%20Write%20ups/images/bandit_images/bandit3.png)

Let's break down the command:

```bash
ls -asl

```

This is a **Linux command** used to **list files in a directory**, showing detailed information.

---

## 🧱 Breakdown of each part:

| Part | What it means |
| --- | --- |
| `ls` | Lists files and directories |
| `-a` | Shows **all files**, including **hidden** ones (those starting with `.`) |
| `-s` | Shows the **size in blocks** of each file |
| `-l` | Shows the **long listing format** (detailed info like permissions, owner, size, etc.) |

## So what does it do?

The command:

```bash
ls -asl

```

- Lists **all files and folders** (even hidden ones)
- Shows **file sizes in blocks**
- Gives **detailed info** like:
    - File permissions (`rw-r--r--`)
    - Number of links
    - Owner and group
    - Size
    - Last modified date
    - File name

---

## 📦 Example Output:

```bash
4 drwxr-xr-x  2 user user 4096 Sep  5 12:00 .
4 drwxr-xr-x 10 user user 4096 Sep  5 11:30 ..
8 -rw-r--r--  1 user user  742 Sep  5 12:00 file.txt
4 -rw-r--r--  1 user user   30 Sep  5 12:00 .hiddenfile

```

### Columns Explained:

| Column | Meaning |
| --- | --- |
| `4`, `8` | Size in blocks (typically 1 block = 1 KB) |
| `drwxr-xr-x` | File type + permissions |
| `2`, `1` | Number of hard links |
| `user user` | Owner and group |
| `4096`, `742` | File size in bytes |
| `Sep 5 12:00` | Last modified date |
| `.` / `..` / `file.txt` | File or directory name |