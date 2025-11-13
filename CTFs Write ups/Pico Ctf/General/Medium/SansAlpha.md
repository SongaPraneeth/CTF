# SansAlpha

**Description:**

The Multiverse is within your grasp! Unfortunately, the server that contains the secrets of the multiverse is in a universe where keyboards only have numbers and (most) symbols.

**Steps to solve:**

step1: After connecting we cant use commands, so will use some wild cards like 

- **`?`** : match 1 character, ex. /**???** -> /**bin** /**dev** /**etc** /**lib**
- `*` : match 0 or more characters, ex. /lib* -> /lib /lib**32** /lib**64**
- **`[ ]`** : matches any single character within the specified range or set, ex. file**[345]**.txt or file**[3–5]**.txt -> file**3**.txt, file**4**.txt, file**5**.txt, file**6**.txt
- **`[!]`** : matches any character that is not in the specified range or set, ex. file**[!12]**.txt -> any files from file**0**.txt-file**9**.txt, except file**1**.txt and file**2**.txt

step2: Now use `*` and we will find a blargh and now try to enter by command `*/*`  and we will find the `flag.txt` file

step3: So now lets try to find a file that can be used to read this file, so use ? to find, so first use `/???` and you will find /bin , second `/???/????` you will find bash and thrid `/???/??????` you will find base64

step4: Now lets use base64 file to get the contents in the flag.txt file, which will be base64 encode but we can decode it to get the flag, so now use the command 

`/???/????64 ?????/??????????/??????/????????`  (as we know the path of the flag.txt is /home/ctf-player/blargh/flag.txt), when we execute we will get that x86_64 is being find used , so we will remove it by placing `[!_]` on the fourth place, its says that avoid which has underscore. and the command will become `/???/???[!_]64 ?????/??????????/??????/????????`

step5: After running the code you will get the encoded flag, so now exit from that server and decode that encoded flag using code `echo ‘encoded_flag’ | base64 -d` and you will get the flag.

![image alt](https://github.com/SongaPraneeth/CTF/blob/33eda6bda3a3f5beac71d950140ed4b90264a9a9/CTFs%20Write%20ups/images/picoctf_images/general/Medium/SansAlpha_1.png)

![image alt](https://github.com/SongaPraneeth/CTF/blob/33eda6bda3a3f5beac71d950140ed4b90264a9a9/CTFs%20Write%20ups/images/picoctf_images/general/Medium/SansAlpha_2.png)