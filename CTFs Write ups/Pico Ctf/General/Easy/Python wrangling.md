Description:

Python scripts are invoked kind of like programs in the Terminal... Can you run this Python script using this password to get the flag?

Steps to solve:

step1 : After download we get python script is `ende.py` , password is `pw.txt` flag is `flag.txt.en`

step2: As the description said lets run the python file and see what it says, and running we get Usage: ende.py (-e/-d) [file] , as the flag file is encrypted, now we have to decrypt it.

step3: so lets use -d , `python3 ende.py -d flag.txt.en` 

and press enter, now it will ask to enter the password, paste the contents present in the pw.txt file.

step4: Now you will get the flag

![image alt](https://github.com/SongaPraneeth/CTF/blob/b5e41ef578bfb831de71c691f587fd2c858bd300/CTFs%20Write%20ups/images/picoctf_images/general/Easy/Python_wrangling.png)