Description:

Our flag printing service has started glitching! Additional details will be available after launching your challenge instance.

Steps to solve:

step1: Click the Launch Instance and you will get a command like `nc [saturn.picoctf.net](http://saturn.picoctf.net/) 58247`  

step2: now open command line and paste the command and press enter, then the remote service will print `'picoCTF{gl17ch_m3_n07_' + chr(0x62) + chr(0x64) + chr(0x61) + chr(0x36) + chr(0x38) + chr(0x66) + chr(0x37) + chr(0x35) + '}'`
step3: so now enter `python` in the terminal and press enter then, The terminal launches the Python interpreter.

step4: The `chr()` function converts a **Unicode code point (integer)** into the **character** it represents. Each number here is written in **hexadecimal** (starts with `0x`), which Python automatically understands as a number. so now we will print using the command 

`print('picoCTF{gl17ch_m3_n07_' + chr(0x62) + chr(0x64) + chr(0x61) + chr(0x36) + chr(0x38) + chr(0x66) + chr(0x37) + chr(0x35) + '}')`

step5: now we will get the flag 

![image alt](https://github.com/SongaPraneeth/CTF/blob/b5e41ef578bfb831de71c691f587fd2c858bd300/CTFs%20Write%20ups/images/picoctf_images/general/Easy/Glitch_cat.png)