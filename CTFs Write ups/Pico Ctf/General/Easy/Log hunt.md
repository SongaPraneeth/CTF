Description:
Our server seems to be leaking pieces of a secret flag in its logs. The parts are scattered and sometimes repeated. Can you reconstruct the original flag? Download the logs and figure out the full flag from the fragments

Steps to solve:

step1: use command `head server.log` to get first 10 lines

setp2: Use command `cat server.log | grep “INFO FLAGPART”` and you will get flag in parts, join that , you flag will be picoCTF{us3_y0urlinux_skills_cedfa5fb}

![image alt](https://github.com/SongaPraneeth/CTF/blob/b5e41ef578bfb831de71c691f587fd2c858bd300/CTFs%20Write%20ups/images/picoctf_images/general/Medium/Log_hunt.png)