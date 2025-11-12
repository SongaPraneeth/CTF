Level Goal: 

A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

Steps to solve:

step1 : use cd /etc/cron.d 

step2: use ls 

step3: use cat to see the contents in the file , `cat cronjob_bandit22`

step4: now we will know the path, so use `cat  /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv` to know the password

![image alt](https://github.com/SongaPraneeth/CTF/blob/3d95217f6498d1b845e4fcc465afe215e5eea7c1/CTFs%20Write%20ups/images/bandit_images/bandit21.png)

# **Cron – Simple Summary**

### **Definition:**

- `cron` is a **background service (daemon)** in Unix/Linux that runs commands or scripts automatically at scheduled times.
- Think of it as a **robot worker** that never stops running.

---

### **Key Points:**

1. **cron runs nonstop** in the background.
2. **crontab** = the schedule/instructions for cron.
    - Tells cron *what to run* and *when to run it*.
3. **Scripts or commands** are stored in `.sh` files (or any executable), which cron executes.
4. Cron **does not live inside the script**; the script just contains commands.

---

### **Crontab Format:**

```
* * * * * /path/to/script.sh

```

| Field | Meaning |
| --- | --- |
| Minute | 0–59 |
| Hour | 0–23 |
| Day of Month | 1–31 |
| Month | 1–12 |
| Day of Week | 0–7 (0 or 7 = Sunday) |
- → “every” possible value for that field

---

### **Examples:**

1. **Every minute:**

```
* * * * * /home/user/hello.sh

```

1. **Every day at 5 AM:**

```
0 5 * * * /home/user/myscript.sh

```

1. **Every Monday at 3:30 PM:**

```
30 15 * * 1 /home/user/report.sh

```