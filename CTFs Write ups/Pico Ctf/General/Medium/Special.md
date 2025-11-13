**Description:** 

Don't power users get tired of making spelling mistakes in the shell? Not anymore! Enter Special, the Spell Checked Interface for Affecting Linux. Now, every word is properly spelled and capitalized... automatically and behind-the-scenes! Be the first to test Special in beta, and feel free to tell us all about how Special streamlines every development process that you face. When your co-workers see your amazing shell interface, just tell them: That's Special (TM) Start your instance to see connection details.

Additional details will be available after launching your challenge instance.

**Steps to solve:**

step1: After connecting we will use `${parameter:=ls}` because as the first letter is being capitalized, this will make ls command run directly

step2: Now we will know that there is a directory `blargh`

step3: Now see what is inside `blargh` with command `${parameter:=ls blargh}` and you will see `flag.txt` file

step4: To read that file use command `${paramter:=cat blargh/flag.txt}` and you will get the flag

`${parameter:=word}` is used for **default assignment**.

- If `parameter` **is unset or null**, it gets assigned the value of `word`.
- The **result of the expression** is the value of `parameter` **after the assignment**.

---

### **Step by Step**

1. **Check if `parameter` is set**
    - If yes → use its value.
    - If no → assign `word` to it.
2. **Return the value**
    - After the assignment, `${parameter:=word}` evaluates to the new value of `parameter`.
    

![image alt](https://github.com/SongaPraneeth/CTF/blob/33eda6bda3a3f5beac71d950140ed4b90264a9a9/CTFs%20Write%20ups/images/picoctf_images/general/Medium/Special.png)