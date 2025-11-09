Level Goal:

The password for the next level is stored in **/etc/bandit_pass/bandit14 and can only be read by user bandit14**. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level. **Note:** **localhost** is a hostname that refers to the machine you are working on

Steps to solve: 

step1: use ls to find the private key

step2: Now use command `ssh -i sshprivate.key ****[bandit14@localhost](mailto:bandit14@localhost) ****-p 2220` to access the bandit14
step3: now we will be logged into the bandit14 and now use `cat /etc/bandit_pass/bandit14`   ****to read the password.

![image alt](https://github.com/SongaPraneeth/CTF/blob/fae3ccfc95a09337a2390be80f1cf34fbe0b90ce/CTFs%20Write%20ups/images/bandit_images/bandit13.png)

![image alt](https://github.com/SongaPraneeth/CTF/blob/fae3ccfc95a09337a2390be80f1cf34fbe0b90ce/CTFs%20Write%20ups/images/bandit_images/bandit13.1.png)

Let's break it down:
ssh: The command to initiate an SSH (Secure Shell) connection.

```bash
ssh -i sshkey.private bandit14@localhost -p 2220

```

- i sshkey.private: Specifies the private key file to use for authentication (sshkey.private).

bandit14@localhost: You're logging in as user bandit14 on the local machine (localhost).

- p 2220: Specifies the non-standard SSH port (2220) that the server is listening on.