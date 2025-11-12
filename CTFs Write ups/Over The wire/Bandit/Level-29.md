Level Goal:

There is a git repository at `ssh://bandit29-git@localhost/home/bandit29-git/repo` via the port `2220`. The password for the user `bandit29-git` is the same as for the user `bandit29`.

Clone the repository and find the password for the next level.

Steps to solve:

1. **`git clone ssh://...`**
    - You cloned a repository that belongs to `bandit29-git`.
    - Reason: this repo contains notes (and somewhere inside, the password for bandit30).

---

1. **`cat README.md` (on master branch)**
    - You checked the default branch (master).
    - It showed:
        
        ```
        username: bandit30
        password: <no passwords in production!>
        
        ```
        
    - Reason: The current version **hides the password**. This means you need to look into history or other branches.

---

1. **`git log` + `git checkout <commit>`**
    - You looked at older commits.
    - In the first commit (`e915edf...`), the README said:
        
        ```
        username: bandit29
        password: <no passwords in production!>
        
        ```
        
    - Reason: The password was changed in history, but even the older commit didn’t reveal it. This hints the real password might not be in the main branch at all.

---

1. **`git branch -a`**
    - You checked for other branches.
    - Found: `dev`, `sploits-dev`.
    - Reason: Developers often keep sensitive stuff (or work-in-progress notes) in non-master branches.

---

1. **`git checkout dev`**
    - You switched to the `dev` branch.
    - Inside, there was extra content (`code/` folder + modified README).
    - The README here finally had:
        
        ```
        username: bandit30
        password: qp30ex3VLz5MDG1n91YowTv4Q8l7CDZL
        
        ```
        
    - Reason: That’s the actual password, left in the `dev` branch.

---

### 🧠 Big Picture Explanation

- The game is teaching you that in real life, secrets often get **exposed in Git repositories**.
- Even if they’re removed from the main branch, they may still exist in **older commits** or **side branches**.
- As an attacker or penetration tester, checking **history (`git log`)** and **other branches (`git branch -a`)** can reveal sensitive information that wasn’t meant to be public.

---

✅ So, in simple words:

You explored the Git repository’s **history and branches** because developers sometimes hide or overwrite sensitive info, but Git keeps a record. By looking deeper (instead of trusting the latest version), you uncovered the **real password for bandit30**.

![image alt](https://github.com/SongaPraneeth/CTF/blob/3d95217f6498d1b845e4fcc465afe215e5eea7c1/CTFs%20Write%20ups/images/bandit_images/bandit29.png)

![image alt](https://github.com/SongaPraneeth/CTF/blob/3d95217f6498d1b845e4fcc465afe215e5eea7c1/CTFs%20Write%20ups/images/bandit_images/bandit29.1.png)

![image alt](https://github.com/SongaPraneeth/CTF/blob/3d95217f6498d1b845e4fcc465afe215e5eea7c1/CTFs%20Write%20ups/images/bandit_images/bandit29.2.png)

![image alt](https://github.com/SongaPraneeth/CTF/blob/3d95217f6498d1b845e4fcc465afe215e5eea7c1/CTFs%20Write%20ups/images/bandit_images/bandit29.3.png)

![image alt](https://github.com/SongaPraneeth/CTF/blob/3d95217f6498d1b845e4fcc465afe215e5eea7c1/CTFs%20Write%20ups/images/bandit_images/bandit29.4.png)

![image alt](https://github.com/SongaPraneeth/CTF/blob/3d95217f6498d1b845e4fcc465afe215e5eea7c1/CTFs%20Write%20ups/images/bandit_images/bandit29.5.png)

![image alt](https://github.com/SongaPraneeth/CTF/blob/3d95217f6498d1b845e4fcc465afe215e5eea7c1/CTFs%20Write%20ups/images/bandit_images/bandit29.6.png)