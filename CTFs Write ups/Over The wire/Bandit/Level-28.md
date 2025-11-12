Level Goal:

There is a git repository at `ssh://bandit28-git@localhost/home/bandit28-git/repo` via the port `2220`. The password for the user `bandit28-git` is the same as for the user `bandit28`.

Steps to solve:

step1: enter /tmp directory using `cd /tmp` and make a directory using `mkdir abcd` and enter it by `cd /abcd`

step2: Now clone the repository using command `git clone  ssh://bandit28-git@localhost:2220/home/bandit28-git/repo`  

step3: After cloning completed we will get the repo directory, now enter repo directory , `cd repo` and after entering we will see [README.md](http://README.md) , now use `cat README.md` , now we will see user and but password is not present

step4: so we don’t have password, now as it is git , we will use logs to see, so use command `git log`  

step5: Now use command `git checkout a158f9a82c29a16dcea474458a5ccf692a385cd4`  and  `git checkout 68314e012fbaa192abfc9b78ac369c82b75fab8f`

step6: now read the [README.md](http://README.md) using `cat README.md` 

![image alt](https://github.com/SongaPraneeth/CTF/blob/3d95217f6498d1b845e4fcc465afe215e5eea7c1/CTFs%20Write%20ups/images/bandit_images/bandit28.png)

![image alt](https://github.com/SongaPraneeth/CTF/blob/3d95217f6498d1b845e4fcc465afe215e5eea7c1/CTFs%20Write%20ups/images/bandit_images/bandit28.1.png)

![image alt](https://github.com/SongaPraneeth/CTF/blob/3d95217f6498d1b845e4fcc465afe215e5eea7c1/CTFs%20Write%20ups/images/bandit_images/bandit28.2.png)

### Purpose of `git checkout`

Its job is to **move you around inside your repository** — like a time machine.

- **Switch branches** → jump between different lines of development.
- **Move to a past commit** → see the project as it looked at that point.
- **Restore files** → bring back an older version of a file.

---

### In one sentence:

👉 `git checkout` lets you **switch context** in Git — to a branch, commit, or file version — so you can work on or view different states of your code.

### **`git log`**

`git log` shows the **history of commits** in your repository — who made them, when, and with what message.

It’s like a **diary of your project’s changes**.

---

### **Basic use**

```bash
git log

```

Shows each commit with:

- Commit ID (a unique hash)
- Author (who made it)
- Date
- Commit message

Example:

```
commit a3f5c2d9e1234567abcd...
Author: Prane <prane@example.com>
Date:   Sat Sep 14 12:34 2025 +0530

    Fixed login bug

```

---

### **Useful variations**

- `git log --oneline` → one-line summary per commit
- `git log --graph --oneline --decorate` → visual branch/merge tree
- `git log -n 5` → last 5 commits

---

👉 In short:

**`git log` = the history book of your Git repo.**