Description:

I accidentally wrote the flag down. Good thing I deleted it!

Steps to solve:

step1: unzip the challenge.zip file using command `unzip challenge.zip` and you will get a folder `drop-in`, now enter the folder using command `cd drop-in`.

step2: now use `ls` command to see if there are any files in the folder, we will find a file named `message.txt`, use cat command to see inside the file `cat message.txt` and we see TOP SECRET

step3: In description it was told that flag was written, so check the log using `git log` and we find there was a commit with message create flag

step4: let’s check that commit using `git checkout` with that commit number, `git  checkout 6603cb4ff0c4ea293798c03a32e0d78d5ab12ca2`

step5: now we are switched to `6603cb4ff0c4ea293798c03a32e0d78d5ab12ca2`, so check what is inside the `message.txt` file, `cat message.txt`, and we will find the flag.

![image alt](https://github.com/SongaPraneeth/CTF/blob/b5e41ef578bfb831de71c691f587fd2c858bd300/CTFs%20Write%20ups/images/picoctf_images/general/Easy/commitment_issue_1.png)

![image alt](https://github.com/SongaPraneeth/CTF/blob/b5e41ef578bfb831de71c691f587fd2c858bd300/CTFs%20Write%20ups/images/picoctf_images/general/Easy/commitment_issue_2.png)

![image alt](https://github.com/SongaPraneeth/CTF/blob/b5e41ef578bfb831de71c691f587fd2c858bd300/CTFs%20Write%20ups/images/picoctf_images/general/Easy/commitment_issue_3.png)