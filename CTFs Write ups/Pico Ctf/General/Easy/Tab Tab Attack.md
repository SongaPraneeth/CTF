Description:

Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames.

Steps to solve:

step1: Download the file and unzip the file using the command `unzip Addadshashanammu.zip`

step2: Now you will get a directory, so enter the directory using the command `cd Addadshashanammu`

step3: Now continue to enter the directories, but remember don’t type entire directory name just use `tab` button after writing `cd` 

step4: After entering few directories you will find a executable file, execute file using command  `./fang-of-haynekhtnamet` and you will get your flag.

1. `./fang-of-haynekhtnamet`

- `./` means: run the file named `fang-of-haynekhtnamet` in **the current directory**.
- `fang-of-haynekhtnamet` is a **setuid binary**, meaning:
    - It's an executable file that **runs with the permissions of its owner**, no matter who launches it.

![image alt](https://github.com/SongaPraneeth/CTF/blob/b5e41ef578bfb831de71c691f587fd2c858bd300/CTFs%20Write%20ups/images/picoctf_images/general/Easy/Tab_tab_attack_1.png)

![image alt](https://github.com/SongaPraneeth/CTF/blob/b5e41ef578bfb831de71c691f587fd2c858bd300/CTFs%20Write%20ups/images/picoctf_images/general/Easy/Tab_tab_attack_2.png)