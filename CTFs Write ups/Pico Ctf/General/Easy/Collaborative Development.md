Description:

My team has been working very hard on new features for our flag printing program! I wonder how they'll work together? 

Steps to solve:

step1: To unzip the challenge.zip folder use command `unzip challenge.zip` and after un zipping the folder you will get a folder called `drop-in`

step2: Now enter the folder using `cd drop-in` command

step3: As given in description, there is a team, so there can be branches, so use `git branch` to find any branch's, and you will find 3 more branches other that main.

step4: Here you can change the branches and see what is going on that branch , but lets just merge all the branches, to main . so use command `git merge feature/part-1` 

step5: After the first merge is successful we can see the change in the `flag.py` file

step6: now lets merge second branch `git merge feature/part-2` , here after merging it will say there is a conflict. so fix conflict and then commit

step5: Lets see what happened inside the file `cat flag.py`, we can see there is more unwanted text, so remove it manually using you preferred text editor, i used vim

step6: Now lets merger third branch `git merge feature/part-3`, but we will get an error, because we have correct the file, but not added and committed. so add the file, using command `git add flag.py` and commit using `git commit -m “add flag.py”`  . Here -m is used to add message, you can just use git commit

step7: Now we can merge third branch, and after merging again edit the file to remove unwanted text.

step8: After removing all the unwanted text run the file , using command `python3 flag.txt` and you will get the flag

![image alt](https://github.com/SongaPraneeth/CTF/blob/b5e41ef578bfb831de71c691f587fd2c858bd300/CTFs%20Write%20ups/images/picoctf_images/general/Easy/collaborative_development_1.png)

![image alt](https://github.com/SongaPraneeth/CTF/blob/b5e41ef578bfb831de71c691f587fd2c858bd300/CTFs%20Write%20ups/images/picoctf_images/general/Easy/collaborative_development_2.png)

![image alt](https://github.com/SongaPraneeth/CTF/blob/b5e41ef578bfb831de71c691f587fd2c858bd300/CTFs%20Write%20ups/images/picoctf_images/general/Easy/collaborative_development_3.png)

![image alt](https://github.com/SongaPraneeth/CTF/blob/b5e41ef578bfb831de71c691f587fd2c858bd300/CTFs%20Write%20ups/images/picoctf_images/general/Easy/collaborative_development_4.png)