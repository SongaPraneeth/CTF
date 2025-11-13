**Description**: 

Someone's commits seems to be preventing the program from working. Who is it?

**Steps to solve:**

step1: Download challenge file

step2: unzip the file using the command `unzip challenge.zip` and you will get `drop-in` directory

step3: Now enter the directory using command `cd drop-in`

step4: Now see what  files are present in the directory using `ls` command, after using the command we will get a file  `message.py`

step5: Now we have to find the commit done to that file, use the command `git log message.py`, and it will show who made the changes, and you will find the flag. The flag is the author’s name shown in the commit.

![image alt](https://github.com/SongaPraneeth/CTF/blob/b5e41ef578bfb831de71c691f587fd2c858bd300/CTFs%20Write%20ups/images/picoctf_images/general/Easy/Blame_game.png)

![image alt](https://github.com/SongaPraneeth/CTF/blob/b5e41ef578bfb831de71c691f587fd2c858bd300/CTFs%20Write%20ups/images/picoctf_images/general/Easy/Blame_game1.png)