Level Goal :

There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a command line argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).

**NOTE:** Try connecting to your own network daemon to see if it works as you think

Steps to solve:

step1: Open two tabs and enter the  level 20 

step2: In one tab create a listening server using `nc -lvp 1122`

step3: now in another tab use the setuid binary and enter command `./suconnect 1122`

step4: In tab one we will see a connect received from local host

step5: Now enter the current level password and you will receive  the password for the next level

![image alt](https://github.com/SongaPraneeth/CTF/blob/3d95217f6498d1b845e4fcc465afe215e5eea7c1/CTFs%20Write%20ups/images/bandit_images/bandit20.1.png)

![image alt](https://github.com/SongaPraneeth/CTF/blob/3d95217f6498d1b845e4fcc465afe215e5eea7c1/CTFs%20Write%20ups/images/bandit_images/bandit20.png)