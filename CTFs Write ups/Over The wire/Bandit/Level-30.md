Level Goal:

There is a git repository at `ssh://bandit30-git@localhost/home/bandit30-git/repo` via the port `2220`. The password for the user `bandit30-git` is the same as for the user `bandit30`.

Clone the repository and find the password for the next level.

steps to solve:

1. **Cloning the repo**
    
    ```bash
    git clone ssh://bandit30-git@localhost:2220/home/bandit30-git/repo
    
    ```
    
    - You pulled a Git repo that belongs to `bandit30-git`.
    - This repo contains the clue/password.

---

1. **Checking the contents**
    
    ```bash
    cat README.md
    
    ```
    
    - It said:
        
        ```
        just an epmty file... muahaha
        
        ```
        
    - That’s a red herring — the password isn’t in plain sight.

---

1. **Looking at commit history**
    
    ```bash
    git log
    
    ```
    
    - Only **one commit** existed → no useful history to dig through.
    - This tells you: *if the secret isn’t in commits or branches, maybe it’s hidden elsewhere in Git features.*

---

1. **Checking branches**
    
    ```bash
    git branch -a
    
    ```
    
    - Only `master` branch existed, no `dev` or hidden branch.
    - So, not hidden in branches.

---

1. **Discovering tags**
    
    ```bash
    git tag
    
    ```
    
    - You found a tag named `secret`.
    - **Tags in Git** are like labels pointing to a specific commit, often used to mark releases.
    - Developers sometimes hide data in tags.

---

1. **Inspecting the tag**
    
    ```bash
    git show secret
    
    ```
    
    - Output:
        
        ```
        fb5S2xb7bRyFmAvQYQGEqsbhVyJqhnDy
        
        ```
        
    - That’s the **password for bandit31**. ✅
    
    ### What a Git Tag Is
    
    - A **tag** in Git is basically a **label that points to a commit**.
    - Developers usually use tags for marking versions, e.g., `v1.0`, `release-2.3`.
    - Unlike branches, tags don’t move — they stay fixed on a commit forever.
    
    ---
    
    ### Why Bandit Uses a Tag Here
    
    1. **Trick learners**
        - In previous levels, you learned to check commits (`git log`) and branches (`git branch -a`).
        - Here, they want to show you that secrets can also be hidden in **tags**, which are easy to overlook.
    2. **Real-world relevance**
        - In real projects, developers sometimes accidentally include sensitive info in tags (like API keys or credentials).
        - Since tags get pushed to remote repos (like GitHub), anyone can see them if they’re not cleaned up.
    3. **New lesson**
        - Each Bandit level teaches a different Git feature.
        - This level specifically wants you to **explore tags** with:
            
            ```bash
            git tag
            git show <tagname>
            
            ```
            
    
    ---
    
    ✅ **In short:**
    
    The password was hidden in a tag to teach you:
    
    👉 *Always check tags in a Git repository, because they can contain secrets just like commits or branches.*
    
    ![image alt](https://github.com/SongaPraneeth/CTF/blob/3d95217f6498d1b845e4fcc465afe215e5eea7c1/CTFs%20Write%20ups/images/bandit_images/bandit30.png)
    
    ![image alt](https://github.com/SongaPraneeth/CTF/blob/3d95217f6498d1b845e4fcc465afe215e5eea7c1/CTFs%20Write%20ups/images/bandit_images/bandit30.1.png)
    
    ![image alt](https://github.com/SongaPraneeth/CTF/blob/3d95217f6498d1b845e4fcc465afe215e5eea7c1/CTFs%20Write%20ups/images/bandit_images/bandit30.2.png)
    
    ![image alt](https://github.com/SongaPraneeth/CTF/blob/3d95217f6498d1b845e4fcc465afe215e5eea7c1/CTFs%20Write%20ups/images/bandit_images/bandit30.3.png)