Description:

Can you crack the password to get the flag? Download the password checker file and you'll need the encrypted file in the same directory too.

Steps to solve:

Step1: After downloading the files, see what is present in both the files using the cat command `cat level2.flag.txt.enc` and `cat level2.py`

Step2: Now in `level2.py` file we see that in level_2_pw_check function is comparing the user given password with `chr(0x34) + chr(0x65) + chr(0x63) + chr(0x39)`, Here the values like `0x34` are hexadecimal numbers, so the built in function `chr()` converters into its corresponding character

Step3: So there are two ways to get the password. First way is so search the value of `chr(0x34) + chr(0x65) + chr(0x63) + chr(0x39)` in google. Second way is to run the `print(chr(0x34) + chr(0x65) + chr(0x63) + chr(0x39))` in terminal . so use command python3 and press enter, now you can run python commands, so now run `print(chr(0x34) + chr(0x65) + chr(0x63) + chr(0x39))` and you will get the password. 

step4: After you got the password, now run the [level2.py](http://level2.py) file using command `python3 level2.py` and enter the password, you will get the flag.

![image alt](https://github.com/SongaPraneeth/CTF/blob/b5e41ef578bfb831de71c691f587fd2c858bd300/CTFs%20Write%20ups/images/picoctf_images/general/Easy/P%20W%20crack%202.png)

![image alt](https://github.com/SongaPraneeth/CTF/blob/b5e41ef578bfb831de71c691f587fd2c858bd300/CTFs%20Write%20ups/images/picoctf_images/general/Easy/P%20W%20crack%202%20(2).png)