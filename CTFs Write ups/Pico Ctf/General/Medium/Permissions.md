**Description:**

Can you read files in the root file? The system admin has provisioned an account for you on the main server: ssh -p 64844 picoplayer@saturn.picoctf.net Password: vCR2tuwCRm Can you login and read the root file?

**Steps to solve:**

step1: After pressing the start instance you will get `ssh -p 64844 picoplayer@saturn.picoctf.net` and password, now use these to connect

step2: Now as we know that we have to read the root file, so go up to the `/` directory and use `ls` command and you will find `root` directory.

step3: Now if we try to use cd command, it will say permission denied. so let’s use `sudo -l` command to know what are all the sudo commands that we have access to . After running the command we will know that `vi` can be used.

step4: Use `sudo vi` command to enter the `vi` editor, To run command in `vi`, first press `esc` button and after that type `:!` and use you command, the command will be like `:! ls /root` and after this command we found nothing, Now again enter the editor by pressing `enter` or again enter `sudo vi` , now use `:! ls -al /root` , this command is used to list all hidden files and folders, and now we will see a folder named `.flag.txt`, now again enter the editor and use command `:! cat /root/.flag.txt` and you will get you flag.

![Permissions_1.png](https://github.com/SongaPraneeth/CTF/blob/33eda6bda3a3f5beac71d950140ed4b90264a9a9/CTFs%20Write%20ups/images/picoctf_images/general/Medium/Permissions_1.png)

![Permissions_5.png](https://github.com/SongaPraneeth/CTF/blob/33eda6bda3a3f5beac71d950140ed4b90264a9a9/CTFs%20Write%20ups/images/picoctf_images/general/Medium/Permissions_5.png)

![Permissions_2.png](https://github.com/SongaPraneeth/CTF/blob/33eda6bda3a3f5beac71d950140ed4b90264a9a9/CTFs%20Write%20ups/images/picoctf_images/general/Medium/Permissions_2.png)

![Permissions_3.png](https://github.com/SongaPraneeth/CTF/blob/33eda6bda3a3f5beac71d950140ed4b90264a9a9/CTFs%20Write%20ups/images/picoctf_images/general/Medium/Permissions_3.png)

![Permissions_4.png](https://github.com/SongaPraneeth/CTF/blob/33eda6bda3a3f5beac71d950140ed4b90264a9a9/CTFs%20Write%20ups/images/picoctf_images/general/Medium/Permissions_4.png)