**Description:**

crackme.py

**Steps to solve:**

step1: Download the file and open with `vim`, the command is `vim crackme.py`

step2: In that code, we can observe that there are two function, first function decodes the flag using `rot 47`, second function compares two numbers and prints largest, so lets run the code

step3: But when we run the code, it only checks two numbers, so open the file again, if we clearly, observe the code, we can see that the first function is not called, so just call the function and pass a parameter  `bezos_cc_secret`.  and just remove the comparing code.

step4: Now run the file and you will get the flag.

![image alt](https://github.com/SongaPraneeth/CTF/blob/b468782d800ff72b63e3989fb971c1d7b96d7166/CTFs%20Write%20ups/images/picoctf_images/Reverse/Medium/crackme-py_3.png)

Before doing changes in code:

![image alt](https://github.com/SongaPraneeth/CTF/blob/b468782d800ff72b63e3989fb971c1d7b96d7166/CTFs%20Write%20ups/images/picoctf_images/Reverse/Medium/crackme-py_1.png)

After doing changes in code:

![image alt](https://github.com/SongaPraneeth/CTF/blob/b468782d800ff72b63e3989fb971c1d7b96d7166/CTFs%20Write%20ups/images/picoctf_images/Reverse/Medium/crackme-py_2.png)