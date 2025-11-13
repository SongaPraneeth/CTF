**Description:**

There's an interesting script in the user's home directory The work computer is running SSH. We've been given a script which performs some basic calculations, explore the script and find a flag.

Hostname: saturn.picoctf.net
Port:     49515
Username: picoplayer
Password: password

**Steps to solve:**

step1: Use command `ssh picoplayer@saturn.picoctf.net -p 49515` and connect to the sever.

step2: After connecting you command `ls` command to find the file `useless`, now we can see that the color of the file is different, so to find what type of the file use command `file useless`.

step3: Now we find that it is executable file. so execute the file by command `./useless` , after executing , it will say to read the file first. so use `cat` command to read , and we will know how to use this file and at end of the file it tells to read manual.

step4: So to read the manual, we will use command `man useless`, and in that manual we will find the flag.

![image alt](https://github.com/SongaPraneeth/CTF/blob/33eda6bda3a3f5beac71d950140ed4b90264a9a9/CTFs%20Write%20ups/images/picoctf_images/general/Medium/Useless_1.png)

![image alt](https://github.com/SongaPraneeth/CTF/blob/33eda6bda3a3f5beac71d950140ed4b90264a9a9/CTFs%20Write%20ups/images/picoctf_images/general/Medium/Useless_2.png)

![image alt](https://github.com/SongaPraneeth/CTF/blob/33eda6bda3a3f5beac71d950140ed4b90264a9a9/CTFs%20Write%20ups/images/picoctf_images/general/Medium/Useless_3.png)