Level Goal: 

There is a git repository at `ssh://bandit31-git@localhost/home/bandit31-git/repo` via the port `2220`. The password for the user `bandit31-git` is the same as for the user `bandit31`.

Clone the repository and find the password for the next level.

Steps to solve:

step1: change the directory to /tmp using `cd /tmp` and make a new directory and change to it using commands, `mkdir aaa` and `cd aaa`

step2: Now clone the repository using

`gitclonessh://bandit31git@localhost:2220/home/bandit31-git/repo` 

step3: change into repo directory `cd repo` and read the file [README.md](http://README.md) `cat README.md`, and now we will see instruction to push a key.txt file , with content of May I come in?
step4: so make the file using command `echo “ May I come in?” > key.txt` 

step5: Ok now move the file into gits staging area with command git add key.txt

step6: now commit the file with `git commit -m “hi”`

step7: now push the commit, `git push`

![image alt](https://github.com/SongaPraneeth/CTF/blob/3d95217f6498d1b845e4fcc465afe215e5eea7c1/CTFs%20Write%20ups/images/bandit_images/bandit31.png)

![image alt](https://github.com/SongaPraneeth/CTF/blob/3d95217f6498d1b845e4fcc465afe215e5eea7c1/CTFs%20Write%20ups/images/bandit_images/bandit31.1.png)

![image alt](https://github.com/SongaPraneeth/CTF/blob/3d95217f6498d1b845e4fcc465afe215e5eea7c1/CTFs%20Write%20ups/images/bandit_images/bandit31.2.png)

## Step 1: Initialize or connect to a repo

```bash
git init

```

- Creates a new empty Git repository in your folder.
- Without this, Git has no place to track your file changes.

```bash
git remote add origin <remote-url>

```

- Links your local repo to a remote one (e.g., GitHub).
- `origin` is just a nickname for that remote URL.
- Without this, `git push` has no idea where to send your commits.

---

## 🔹 Step 2: Create the file

```bash
echo "hello world" > myfile.txt

```

- This just makes the file.
- Git doesn’t automatically know about it; it’s just a file in your system right now.

---

## 🔹 Step 3: Stage the file

```bash
git add myfile.txt

```

- Moves the file into Git’s **staging area** (like a “shopping cart” before checkout).
- You tell Git: *“I want to include this file in my next commit.”*
- Without `git add`, Git won’t include the file in your commit.

---

## 🔹 Step 4: Commit the file

```bash
git commit -m "Add myfile.txt"

```

- Saves a snapshot of your staged files into Git history.
- The `m` lets you write a commit message.
- Without a commit, there’s nothing to push — Git only pushes commits, not raw files.

---

## 🔹 Step 5: Push the commit

```bash
git push origin main

```

- Sends your commits from the local repo to the remote repo (`origin`).
- `main` tells Git which branch to push to.
- Without pushing, your changes stay local and won’t appear on GitHub/GitLab/etc.

---

### 📌 Summary

- **`git init` / `git clone`** → set up repository
- **`git remote add`** → connect to remote
- **`git add`** → stage files
- **`git commit`** → record changes in history
- **`git push`** → upload commits to remote