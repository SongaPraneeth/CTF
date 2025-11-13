**Description:**

Can you crack the password to get the flag? Download the password checker here and you'll need the encrypted flag and the hash in the same directory too. Here's a dictionary with all possible passwords based on the password conventions we've seen so far.

**Steps to solve:**

step1: Use any editor and open the `level5.py` file and as we have dictionary with all possible passwords, so we will open the dictionary in the code 

step2: Now lets use `with` keyword and open the `dictionary.txt` file as `fi`

step3: now lets read all lines from `fi` and store in a variable `fil`

step4: Now create a `for` loop and take each possible password and while taking strip the password `.strip()` to remove trailing newline/whitespace. (See the photo for code)

step5: Now run the file using command `python3 level5.py` 

![image alt](https://github.com/SongaPraneeth/CTF/blob/33eda6bda3a3f5beac71d950140ed4b90264a9a9/CTFs%20Write%20ups/images/picoctf_images/general/Medium/PW_crack_5_2.png)

Before correcting the code:

![image alt](https://github.com/SongaPraneeth/CTF/blob/33eda6bda3a3f5beac71d950140ed4b90264a9a9/CTFs%20Write%20ups/images/picoctf_images/general/Medium/PW_crack_5_1.png)

After correcting the code:

![image alt](https://github.com/SongaPraneeth/CTF/blob/33eda6bda3a3f5beac71d950140ed4b90264a9a9/CTFs%20Write%20ups/images/picoctf_images/general/Medium/PW_crack_5_2.png)