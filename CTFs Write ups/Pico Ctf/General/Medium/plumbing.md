**Description:** 

Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag? Connect to [jupiter.challenges.picoctf.org](http://jupiter.challenges.picoctf.org/) 14291.

**Steps to solve:**

step1: Use command `nc  jupiter.challenges.picoctf.org 14291` to connect and you will get a huge number of data

step2: So now we will use pipe and grep to catch the flag. The command is `nc  jupiter.challenges.picoctf.org 14291 | grep picoCTF` and you will get the flag.

![image alt](https://github.com/SongaPraneeth/CTF/blob/33eda6bda3a3f5beac71d950140ed4b90264a9a9/CTFs%20Write%20ups/images/picoctf_images/general/Medium/plumbing_1.png)

![image alt](https://github.com/SongaPraneeth/CTF/blob/33eda6bda3a3f5beac71d950140ed4b90264a9a9/CTFs%20Write%20ups/images/picoctf_images/general/Medium/plumbing_2.png)