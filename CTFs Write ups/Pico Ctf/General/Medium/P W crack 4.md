**Description:**

Can you crack the password to get the flag? Download the password checker here and you'll need the encrypted flag and the hash in the same directory too. There are 100 potential passwords with only 1 being correct. You can find these by examining the password checker script.

**Steps to solve:**

step1: Use any editor and you will see a variable `pos_pw_list` which contains passwords

step2: Now take that variable and place above the function `def level_4_pw_check()`

step3: Now we will do changes in the `def level_4_pw_check()` function, here `user_pw` variable is taking input from the user, now remove that line,

step4: Because we will create a `for` loop in side the function, which will run until correct password is found and each password is taken from the variable `pos_pw_list`, when it is found, the flag is printed. (see photos for code)

step5: Now after doing changes in code, run the file using command `python3 level4.py`

![image alt](https://github.com/SongaPraneeth/CTF/blob/33eda6bda3a3f5beac71d950140ed4b90264a9a9/CTFs%20Write%20ups/images/picoctf_images/general/Medium/PW_crack_4_3.png)

Before correcting the code:

![image alt](https://github.com/SongaPraneeth/CTF/blob/33eda6bda3a3f5beac71d950140ed4b90264a9a9/CTFs%20Write%20ups/images/picoctf_images/general/Medium/PW_crack_4_1.png)

After correcting the code:

![image alt](https://github.com/SongaPraneeth/CTF/blob/33eda6bda3a3f5beac71d950140ed4b90264a9a9/CTFs%20Write%20ups/images/picoctf_images/general/Medium/PW_crack_4_2.png)

![image alt](https://github.com/SongaPraneeth/CTF/blob/33eda6bda3a3f5beac71d950140ed4b90264a9a9/CTFs%20Write%20ups/images/picoctf_images/general/Medium/PW_crack_4_4.png)
