Description:

Do you know how to move between directories and read files in the shell? Start the container, ssh to it, and then ls once connected to begin. Login via ssh as ctf-player with the password, 8c606eb1 on the host wily-courier.picoctf.net and port 63235.

Steps to solve:

step1: Use command `ssh ctf-player@courier.picoctf.net -p 63235` to login

step2: now use `ls` command and you will see two text file, use `cat` command to read those, One file will have a small part of flag, and another file will tell you, where to go next, so now we have to go to the `root` directory which is `/`

step3: First we will use `pwd` command to know where we are and now use `cd ..` to exit, the directory.

step4: Now repeat step2 and now you will have all parts of the flag. copy and paste it in one place, and you will get complete flag.

![image alt](attachment:1ef65697-f8a5-4769-b4b5-382557e040ba:Magikarp_Ground_Mission.png)