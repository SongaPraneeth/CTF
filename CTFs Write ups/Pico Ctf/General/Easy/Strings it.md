Description:

Can you find the flag in file without running it?

Steps to solve:

step1: By using command `file`, we find that the file `strings` is a executable file. But in description is said that we have to find flag without running the file.

step2: So, we will use a command `strings`, This command is used to print the sequences of printable characters in files. Then we will pipe it to `grep` to catch the flag, So the command will be: `strings strings | grep “pico”`

![image alt](https://github.com/SongaPraneeth/CTF/blob/b5e41ef578bfb831de71c691f587fd2c858bd300/CTFs%20Write%20ups/images/picoctf_images/general/Easy/Strings_it.png)