Description: 

Lyrics jump from verses to the refrain kind of like a subroutine call. There's a hidden refrain this program doesn't print by default. Can you get it to print it? There might be something in it for you. The program's source code can be downloaded here. Connect to the program with netcat: $ nc verbal-sleep.picoctf.net 61497

step1: First download the `source code` and lets see what it does

step2: In the code below the comment of `print lyrics`, we can see that it is print the lyrics at the end of the line and in the `for` loop it is splitting a line into `2 parts`, if there is a semicolon(`;`) and if the line is equal to `REFRAIN` it will directly jump to that line, to start printing

step3: When the `CROWD` is found in the line, it will ask for `user’s input`, and prints it. Now at the last `elif` condition it check for the line staring with `RETURN` and an `number`.

step4: So lets try, first connect with `nc` and when the `CROWD` asks for `input`, enter `RETURN 1`, and wait for again `CROWD` to appear, and when it appear, it just prints `RETURN 1`, so the `CROWD` is taking as an input

step5: Now ask we know the in the `for` loop if we have a `semicolon`, it will split into `two parts`, so lets try that here, now when the `CROWD` comes enter `test1;test2` and now we can see that the `test 2` is in the new line

step6: So now in the `CROWD` enter `test1;RETURN 1` and wait what it will print, now we will get the flag.

![flag_hunters_1.png](https://github.com/SongaPraneeth/CTF/blob/f4ed576e8314c51fd25e5140d1b2c712fc7ee648/CTFs%20Write%20ups/images/picoctf_images/Reverse/Easy/flag_hunters_1.png)

![flag_hunters_5.png](https://github.com/SongaPraneeth/CTF/blob/f4ed576e8314c51fd25e5140d1b2c712fc7ee648/CTFs%20Write%20ups/images/picoctf_images/Reverse/Easy/flag_hunters_5.png)

![flag_hunters_2.png](https://github.com/SongaPraneeth/CTF/blob/f4ed576e8314c51fd25e5140d1b2c712fc7ee648/CTFs%20Write%20ups/images/picoctf_images/Reverse/Easy/flag_hunters_2.png)

![flag_hunters_3.png](https://github.com/SongaPraneeth/CTF/blob/f4ed576e8314c51fd25e5140d1b2c712fc7ee648/CTFs%20Write%20ups/images/picoctf_images/Reverse/Easy/flag_hunters_3.png)

![flag_hunters_4.png](https://github.com/SongaPraneeth/CTF/blob/f4ed576e8314c51fd25e5140d1b2c712fc7ee648/CTFs%20Write%20ups/images/picoctf_images/Reverse/Easy/flag_hunters_4.png)