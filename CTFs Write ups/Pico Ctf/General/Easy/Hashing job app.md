**Description**: 

If you want to hash with the best, beat this test!

**Steps to solve:**

step1: After pressing launch instance, you will get command `nc [saturn.picoctf.net](http://saturn.picoctf.net/) 63150` (it may different) and run the command

step2: Now you will be asked to convert a text given in quotes into md5 hash.

step3: now open new terminal and use command `echo -n ‘given text’`  | md5sum , this command will convert the text into md5 hash

step4: Paste the hash into the first terminal and it will again give you another text, it will continue few times and lastly it will give you the flag

Here’s the **exact difference between using `-n` and not using it** in `echo` when hashing:

---

### 1️⃣ With `n`:

```bash
echo -n 'Cinco de Mayo' | md5sum

```

- The string being hashed is **exactly**:

```
Cinco de Mayo

```

- No newline is added.
- MD5 hash will be **consistent** with the exact text `"Cinco de Mayo"`.

---

### 2️⃣ Without `n`:

```bash
echo 'Cinco de Mayo' | md5sum

```

- The string being hashed is actually:

```
Cinco de Mayo\n

```

- `echo` automatically appends a **newline character (`\n`)** at the end.
- MD5 hash will be **different**, because the newline changes the data being hashed.

terminal-1

![image alt](https://github.com/SongaPraneeth/CTF/blob/b5e41ef578bfb831de71c691f587fd2c858bd300/CTFs%20Write%20ups/images/picoctf_images/general/Easy/Hashing_job_app_1.png)

terminal-2

![image alt](https://github.com/SongaPraneeth/CTF/blob/b5e41ef578bfb831de71c691f587fd2c858bd300/CTFs%20Write%20ups/images/picoctf_images/general/Easy/Hashing_job_app_2.png)