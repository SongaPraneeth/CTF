Level Goal:

There are 2 files in the homedirectory: **passwords.old and passwords.new**. The password for the next level is in **passwords.new** and is the only line that has been changed between **passwords.old and passwords.new**

To login to this level :

step1: save the RSA password in the file name sshkey_bandit17.private and change the file permissions using `chmod 600 sshkey_bandit17.private` 

step2: Now use command `ssh -i sshkey_bandit17.private [bandit17@bandit.labs.overthewire.org](mailto:bandit17@bandit.labs.overthewire.org) -p 2220` to login

Steps to solve:

step1: use ls to see the files

step2 : use command `diff [passwords.new](http://passwords.new) passwords.old` 

![image alt](https://github.com/SongaPraneeth/CTF/blob/3d95217f6498d1b845e4fcc465afe215e5eea7c1/CTFs%20Write%20ups/images/bandit_images/bandit17.png)

`diff` command:

```bash
diff passwords.new passwords.old
42c42
< x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO
---
> gvE89l3AhAhg3Mi9G2990zGnn42c8v20

```

### What this means:

- The difference is on **line 42** of both files.
- `42c42` means:
    - Line 42 in `passwords.new` has **changed** (`c`) compared to line 42 in `passwords.old`.
- The `<` line is from **`passwords.new`**
- The `>` line is from **`passwords.old`**

### Interpretation:

Line 42 in the file `passwords.old` had this password:

```
gvE89l3AhAhg3Mi9G2990zGnn42c8v20

```

It was changed to this in `passwords.new`:

```
x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO

```

So, only **one password** was changed between the two files, and it happened on **line 42**.

```bash
diff passwords.new passwords.old

```

### Purpose:

This command compares two files: `passwords.new` and `passwords.old`, **line by line**, and shows the **differences** between them.

---

### Explanation of each part:

| Part | Description |
| --- | --- |
| `diff` | The command-line utility to compare text files and display their differences. |
| `passwords.new` | The first file being compared. Often treated as the "new" or updated version. |
| `passwords.old` | The second file being compared. Often treated as the "original" or older version. |