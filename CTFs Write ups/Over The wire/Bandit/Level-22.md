Level Goal:

A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

**NOTE:** Looking at shell scripts written by other people is a very useful skill. The script for this level is intentionally made easy to read. If you are having problems understanding what it does, try executing it to see the debug information it prints.

Steps to solve:

step1 : use  `ls ./etc/cron.d`  to see the files

step2: use `cat /etc/cron.d/cronjob_bandit23`  to see the inside cron running

step3: Now use cat to see the content the the file `cat /usr/bin/cronjob_bandit23.sh`

step4: Now as we know the error in the bash code after we have runned.
step5: so execute the codes in the terminal by assigning the value `, myname=bandit23` press enter.

step6: use `echo I am user bandit23 | md5sum | cut -d ' ' -f 1`
so we will get hash value 

step7: so, use `cat /tmp/8169b67bd894ddbb4412f91573b38db3`

![image alt](https://github.com/SongaPraneeth/CTF/blob/3d95217f6498d1b845e4fcc465afe215e5eea7c1/CTFs%20Write%20ups/images/bandit_images/bandit22.png)

### The script:

```bash
#!/bin/bash

myname=$(whoami)
mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)

echo "Copying passwordfile /etc/bandit_pass/$myname to /tmp/$mytarget"

cat /etc/bandit_pass/$myname > /tmp/$mytarget

```

---

### 🔎 Step-by-step explanation:

1. **Shebang line**
    
    ```bash
    #!/bin/bash
    
    ```
    
    - Tells the system: “Run this script using the Bash shell.”

---

1. **Get the current username**
    
    ```bash
    myname=$(whoami)
    
    ```
    
    - `whoami` prints the current logged-in user (in this case, `bandit22`).
    - The output is stored in a variable `myname`.
    - Example:
        
        ```bash
        myname="bandit22"
        
        ```
        

---

1. **Generate a target filename**
    
    ```bash
    mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)
    
    ```
    
    - `echo I am user bandit22` → produces the text:
        
        ```
        I am user bandit22
        
        ```
        
    - `md5sum` → computes the MD5 hash of that text.
        
        Example:
        
        ```
        8169b67bd894ddbb4412f91573b38db3  -
        
        ```
        
    - `cut -d ' ' -f 1` → cuts the string at spaces, keeps only the **first field** (the hash itself, no ).
    - So now:
        
        ```bash
        mytarget="8169b67bd894ddbb4412f91573b38db3"
        
        ```
        

---

1. **Print what it’s doing**
    
    ```bash
    echo "Copying passwordfile /etc/bandit_pass/$myname to /tmp/$mytarget"
    
    ```
    
    - Just an informational message: tells you it’s copying the password file for user `$myname` (bandit22) into `/tmp/$mytarget`.

---

1. **Copy the actual password**
    
    ```bash
    cat /etc/bandit_pass/$myname > /tmp/$mytarget
    
    ```
    
    - Reads the password file:
        
        ```
        /etc/bandit_pass/bandit22
        
        ```
        
    - Redirects (`>`) its contents into the new file:
        
        ```
        /tmp/8169b67bd894ddbb4412f91573b38db3
        
        ```
        
    - This is how the password for the next level is hidden — you just need to find the correct `/tmp` file.

---

### ✅ In short:

- The script figures out the username.
- Hashes the phrase `"I am user <username>"` to generate a unique filename.
- Copies that user’s password file into `/tmp/<hash>`.
- That’s where you found the Bandit22 password.