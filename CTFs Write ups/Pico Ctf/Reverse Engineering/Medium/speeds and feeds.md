**Description:**

There is something on my shop network running at nc [mercury.picoctf.net](http://mercury.picoctf.net/) 16524, but I can't tell what it is. Can you?

**Steps to solve:** 

step1: execute the command `nc mercury.picoctf.net 16524` and we will get `g` code commands

step2: so to execute these commands, lets save this in a file, so use the command `nc mercury.picoctf.net 16524 > g_file.txt`

step3: To execute the commands, lets use a website https://ncviewer.com/ and open the file and press `PLOT` and you will get the flag. 

 (information about the website: 

An NC viewer is used to visualize, simulate, and analyze NC (G-code) files for CNC machines, allowing users to understand and test machine toolpaths before a physical run. It helps in creating, editing, and troubleshooting G-code by showing a 3D rendering of the toolpath, which can prevent errors and estimate run times. There is also a different product called NC Viewer for augmented reality content created with the Nextcreate AR authoring tool.)

what is g code and where does it is used ?

answer: 

The purpose of G-code is to control Computer Numerical Control (CNC) machines by providing instructions on how to perform tasks, including where to move, what speed to move at, and which path to follow. It is the standard programming language for machines used in manufacturing, such as mills and lathes, and for applications like 3D printing, allowing for precise and repeatable operations to be performed automatically. 

![image alt](https://github.com/SongaPraneeth/CTF/blob/f4ed576e8314c51fd25e5140d1b2c712fc7ee648/CTFs%20Write%20ups/images/picoctf_images/Reverse/Medium/speeds_and_feeds_2.png)

![image alt](https://github.com/SongaPraneeth/CTF/blob/f4ed576e8314c51fd25e5140d1b2c712fc7ee648/CTFs%20Write%20ups/images/picoctf_images/Reverse/Medium/speeds_and_feeds_3.png)

![image alt](https://github.com/SongaPraneeth/CTF/blob/f4ed576e8314c51fd25e5140d1b2c712fc7ee648/CTFs%20Write%20ups/images/picoctf_images/Reverse/Medium/speeds_and_feeds_1.png)