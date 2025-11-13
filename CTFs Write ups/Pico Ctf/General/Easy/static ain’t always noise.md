Description
Can you look at the data in this binary: static? This BASH script might help!

Steps to solve:

step1: we see that static file is executable with command `file static`

step2: To execute the static file, change its permission, with command `chmod +x  static`, now you can execute the file with command `./static` and after executing you will get `Oh hai! Wait what? A flag? Yes, it's around here somewhere!`

step3: So now we have two options use command `strings static | grep “pico”` and you will get the flag if there is a flag in that file, here we will get the flag.

step4: Another way to get the flag is to run the bash file, the command is `bash ltdis.sh static` and you will get two text file , open the text file using command `cat static.ltdis.strings.txt` and see carefully , you will see the flag.

![image alt](https://github.com/SongaPraneeth/CTF/blob/b5e41ef578bfb831de71c691f587fd2c858bd300/CTFs%20Write%20ups/images/picoctf_images/general/Easy/static_aint_always_noise.png)

![image alt](https://github.com/SongaPraneeth/CTF/blob/b5e41ef578bfb831de71c691f587fd2c858bd300/CTFs%20Write%20ups/images/picoctf_images/general/Easy/static_aint_always_noise_1.png)

![image alt](https://github.com/SongaPraneeth/CTF/blob/b5e41ef578bfb831de71c691f587fd2c858bd300/CTFs%20Write%20ups/images/picoctf_images/general/Easy/static_aint_always_noise_2.png)

You can do this directly after the command `./static`

![image alt](https://github.com/SongaPraneeth/CTF/blob/b5e41ef578bfb831de71c691f587fd2c858bd300/CTFs%20Write%20ups/images/picoctf_images/general/Easy/static_aint_always_noise_3.png)