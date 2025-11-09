**Level Goal:**

The password for the next level is stored in a file called **-** located in the home directory

Steps to Solve:

step1: Use `ls` to find the file 

step2: Then use `cat ./-` command to read the file 


![image alt](https://github.com/SongaPraneeth/CTF/blob/fae3ccfc95a09337a2390be80f1cf34fbe0b90ce/CTFs%20Write%20ups/images/bandit_images/bandit1.png)


This type of approach has a lot of misunderstanding because using **`-`** as an argument refers to **STDIN/STDOUT** i.e **dev/stdin** or **dev/stdout** .So if you want to open this type of file you have to specify the full location of the file such as **`./-**` 

The command:

```bash
cat ./-

```

can look confusing, so let’s break it down:

---

### ✅ **What it does:**

This command attempts to use `cat` to read a file **literally named `-`** (a dash), located in the **current directory (`./`)**.

- `./-` refers to a file called `-` in the current directory.
- `cat` normally interprets `-` as a special argument meaning “**read from standard input**” (i.e. keyboard input).
- To avoid that interpretation, you prefix it with `./` to **explicitly reference the file** named .