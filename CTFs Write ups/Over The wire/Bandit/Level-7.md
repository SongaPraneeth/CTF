**Level Goal :**

The password for the next level is stored in the file **data.txt** next to the word **millionth**

Steps to solve:

step1 : Use `ls` to find data.txt

step2 : Now use `grep “millionth” data.txt` to find the password

![image alt](https://github.com/SongaPraneeth/CTF/blob/fae3ccfc95a09337a2390be80f1cf34fbe0b90ce/CTFs%20Write%20ups/images/bandit_images/bandit7.png)

Here's a clean explanation of the command:

### Command:

```bash
grep "millionth" data.txt

```

### What it does:

This command searches for lines in the file `data.txt` that contain the word `millionth`.

---

### Breakdown:

- `grep`: A command-line tool used to search for specific text within files.
- `"millionth"`: The word you're searching for.
- `data.txt`: The file you want to search in.

---

### In plain terms:

You're telling the system:

**"Show me any line in the file `data.txt` that has the word `millionth` in it."**