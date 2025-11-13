**Description:**

Can you get the real meaning from this file. Download the file here.

**Steps to solve:**

step1: see what is inside the `enc_flag` file using command `cat enc_flag` and we will see a `base64` encoded string

step2: To decode use command `base64 -d enc_flag > enc_1`, here i am saving the output in `enc_1` file

step3: Now open `enc_1` file using command `cat enc_1` and you will see another encoded string but, here you have to remove single quotations to make it a correct encoded string, here i am using `vim` editor

step4: now decode `enc_1` file  and save in `enc_2` file, using command `base64 -d enc_1 > enc_2`

step5: Now see what is in the `enc_2` file using `cat enc_2` and you will see a string which is similar to flag , so decode using command `decode -d enc_2`, but we will get error called invalid input

step6: So as we observe the string, it can be a `Caesar cipher` encrypted, so use `cyberchef` website to decode the string, and it should be `rotated 19` and we will get the flag.

![image alt](https://github.com/SongaPraneeth/CTF/blob/bc7b51486dba5301ab4f66aec8dce913238ab4e7/CTFs%20Write%20ups/images/picoctf_images/Crypto/Easy/interencdec_1.png)

![image alt](https://github.com/SongaPraneeth/CTF/blob/bc7b51486dba5301ab4f66aec8dce913238ab4e7/CTFs%20Write%20ups/images/picoctf_images/Crypto/Easy/interencdec_2.png)