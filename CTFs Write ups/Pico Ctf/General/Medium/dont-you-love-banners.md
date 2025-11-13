**Description:**

Can you abuse the banner? The server has been leaking some crucial information on tethys.picoctf.net 64551. Use the leaked information to get to the server. To connect to the running application use nc tethys.picoctf.net 57833. From the above information abuse the machine and find the flag in the /root directory.

**Steps to solve:**

step1: First connect to the `tethys.picoctf.net 64551` , using command `nc tethys.picoctf.net 64551` and now you will be displayed with a password

step2: Now connect to another server using command `nc tethys.picoctf.net 57833` and enter the password, which was taken from the first server, the password is `My_Passw@rd_@1234`

step3: After entering the password, it will ask two questions, you can search the answers on google or you can answer if you know it and after answering it  will give you the shell.

step4: We know that the flag is in root directory, so list all the files present in the root directory using command `ls -asl /root` 

step5: You will find two files, `flag.txt` and `script.txt`, if you try to read the `flag.txt` file it will give permission denied, so read what is present in `script.txt` file using command `cat script.txt`, It is the code that is executed, when we connect to the server. If we observe correctly a file is being opened in the try block and printed.

step6: So lets create a soft link of the `flag.txt` file, but first remove `banner` file, with command `rm banner`, and now to create a soft link of the file use command `ln -s /root/flag.txt /home/player/banner` , So now when we connect to server the `banner`file which is pointing to the flag.txt will be read and printed and we will get the flag.

![image alt](https://github.com/SongaPraneeth/CTF/blob/33eda6bda3a3f5beac71d950140ed4b90264a9a9/CTFs%20Write%20ups/images/picoctf_images/general/Medium/dont-you-love-banners_1.png)

![image alt](https://github.com/SongaPraneeth/CTF/blob/33eda6bda3a3f5beac71d950140ed4b90264a9a9/CTFs%20Write%20ups/images/picoctf_images/general/Medium/dont-you-love-banners_2.png)

![image alt](https://github.com/SongaPraneeth/CTF/blob/33eda6bda3a3f5beac71d950140ed4b90264a9a9/CTFs%20Write%20ups/images/picoctf_images/general/Medium/dont-you-love-banners_3.png)

## What is `ln`?

`ln` means **link** — it’s used to **create links** between files.

There are **two types of links**:

1. **Hard link**
2. **Soft (symbolic) link**

---

## 1. Hard Link

A **hard link** is like creating another *name* for the same file.

Both files point to the **same data** on disk.

### Example:

```bash
$ echo "Hello World" > file1.txt
$ ln file1.txt file2.txt

```

Now you have two files:

```
file1.txt
file2.txt

```

Both point to the same data.

If you change one:

```bash
$ echo "Hi" >> file2.txt

```

Then check the other:

```bash
$ cat file1.txt

```

Output:

```
Hello World
Hi

```

✅ Changes in one file appear in the other.

If you delete one:

```bash
$ rm file1.txt
$ cat file2.txt

```

Still works! Because the data still exists on disk (until **all** links are deleted).

---

## 2. Symbolic (Soft) Link

A **symbolic link** is like a **shortcut** — it *points* to another file’s **path**.

### Example:

```bash
$ ln -s file1.txt link1.txt

```

Now:

```
link1.txt → file1.txt

```

If you read:

```bash
$ cat link1.txt

```

Output:

```
Hello World
Hi

```

But if you delete the original:

```bash
$ rm file1.txt
$ cat link1.txt

```

❌ Error:

```
cat: link1.txt: No such file or directory

```

Because the shortcut (symlink) is broken.