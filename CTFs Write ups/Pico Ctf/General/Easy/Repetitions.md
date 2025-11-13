**Description**: 

Can you make sense of this file?

**Steps to solve:**

step1: After you have downloaded the file, see what is inside the file using the command `cat enc_flag`

step2: We will see that the flag is encoded, so we will decode using the command `base64 -d enc_flag`

step3: But the value is not decoded, So now lets pipe the value and again decode it `base64 -d enc_flag | base64 -d` , so now we are gonna see some changes in it 

step4: Now pipe multiple times to get the decode value. and the command is `base64 -d enc_flag | base64 -d | base64 -d | base64 -d | base64 -d | base64 -d`

![image alt](https://github.com/SongaPraneeth/CTF/blob/b5e41ef578bfb831de71c691f587fd2c858bd300/CTFs%20Write%20ups/images/picoctf_images/general/Easy/repititoins.png)