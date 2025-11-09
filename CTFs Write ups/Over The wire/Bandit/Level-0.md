The goal of this level is for you to log into the game using SSH. The host to which you need to connect is **bandit.labs.overthewire.org**, on port 2220. The username is **bandit0** and the password is **bandit0**. Once logged in, go to the [Level 1](https://overthewire.org/wargames/bandit/bandit1.html) page to find out how to beat Level 1.

### What is SSH?

**SSH (Secure Shell)** is a secure protocol used to remotely access and manage devices over an unsecured network. It allows encrypted communication between a client (your computer) and a server (the remote machine).

You typically use SSH to:

- Log into remote servers.
- Execute commands remotely.
- Transfer files securely (via `scp` or `sftp`).
- Tunnel or forward ports securely.

---

### The Command Explained

```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220

```

This is an SSH command to log into the **Bandit wargame server** on **OverTheWire.org**, which is a popular platform for learning Linux and cybersecurity.

Let’s break it down:

| Part | Meaning |
| --- | --- |
| `ssh` | Invokes the SSH client (secure shell). |
| `bandit0` | This is the **username** you are logging in as (the first level in the Bandit game). |
| `@bandit.labs.overthewire.org` | This is the **hostname** or **domain** of the server you're connecting to. |
| `-p 2220` | This specifies the **port number**. Normally, SSH uses port `22`, but this server is running SSH on **port 2220**. |

---

### What Happens When You Run It?

When you execute that command:

1. The SSH client connects to `bandit.labs.overthewire.org` on port `2220`.
2. It tries to log in using the username `bandit0`.
3. It will prompt you for the password for `bandit0`.
4. After entering the correct password (found on the OverTheWire website), you'll have terminal access to the server as the user `bandit0`.
5. From there, you can complete the challenges by exploring the file system, reading files, and moving to the next level.

---

### TL;DR

The command:

```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220

```

is used to connect securely to the **Bandit wargame server** as user `bandit0`, using SSH on **port 2220**. It's your entry point to solving OverTheWire’s Bandit security challenges.

Now as we know how to access the bandit server now the 

## Level Goal

The password for the next level(level 1) is stored in a file called **readme** located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.

Steps to solve

step 1 : Use the `ls`  command 

step2 : Now use  `cat` use read the content in the file, then you will find the password

![image alt](https://github.com/SongaPraneeth/CTF/blob/fae3ccfc95a09337a2390be80f1cf34fbe0b90ce/CTFs%20Write%20ups/images/bandit_images/bandit0.png)
