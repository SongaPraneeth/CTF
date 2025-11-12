Level Goal:

There is a git repository at `ssh://bandit27-git@localhost/home/bandit27-git/repo` via the port `2220`. The password for the user `bandit27-git` is the same as for the user `bandit27`.

Clone the repository and find the password for the next level.

Steps to solve:

step1: change the directory to tmp, `cd /tmp`

step2: Now make a directory in which you will clone and enter the directory, use command `mkdir asd`, and `cd asd`

step3: now clone using command `git clone ssh://bandit27-git@localhost/home/bandit27-git/repo`
in this command the port number is not mentioned , so mention the port number 2220 in it, so the command will be like `git clone ssh://bandit27-git@localhost:2220/home/bandit27-git/repo`  press enter and it will ask for password (enter the current level passowrd), now press enter and the repo will be cloned

step4: enter the repo directory using `cd repo` and using `ls` to list the files and you will see the file README

step5: use `cat README` 

![image alt](https://github.com/SongaPraneeth/CTF/blob/3d95217f6498d1b845e4fcc465afe215e5eea7c1/CTFs%20Write%20ups/images/bandit_images/bandit27.png)