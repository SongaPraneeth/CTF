Level Goal:

Logging in to bandit26 from bandit25 should be fairly easy… The shell for user bandit26 is not **/bin/bash**, but something else. Find out what it is, how it works and how to break out of it.

Steps to solve:

step1: first use ls to find any files and then after using we will find bandit26.sshkey

step2: so we know that the bandit 26 shell is not /bin/bash . so find the shell by searching in the /etc/passwd because it stores the type of shell. So now use command `cat /etc/passwd | grep “bandit26”` 

step3: we will know that the shell the bandit 26 is using is /usr/bin/showtext. Use cat /usr/bin/showtext to see the contents

![image alt](https://github.com/SongaPraneeth/CTF/blob/3d95217f6498d1b845e4fcc465afe215e5eea7c1/CTFs%20Write%20ups/images/bandit_images/bandit25.png)

`/usr/bin/showtext` is the program that runs right after you log in (typical in Bandit wargames), and it contains the lines you showed earlier:

```bash
export TERM=linux
exec more ~/text.txt
exit 0

```

Here’s what will happen when you `ssh -i bandit26.ssh bandit26@localhost -p 2220` and then make your terminal window smaller.

# What runs immediately on login

- The script sets the environment variable `TERM` to `linux` for the session (`export TERM=linux`).
- `exec more ~/text.txt` replaces the shell process with `more` displaying `~/text.txt`. Because `exec` is used, nothing after that in the script runs (so `exit 0` is irrelevant).

# How terminal size and TERM interact

- **Window size (rows/columns)** is reported separately from `TERM`. The SSH client tells the remote process the current window size (via the kernel ioctl / TIOCGWINSZ). Programs like `more` and `vi` get the *actual* window dimensions from that ioctl (or from environment variables `LINES`/`COLUMNS`), not from the `TERM` name.
- **The `TERM` variable only tells programs which control sequences to use** (what the terminal can do). If `TERM` is wrong for your terminal emulator, control sequences may be interpreted incorrectly and the display can look messy.

# So when you **make the screen small**:

1. `more` is already running (because of `exec`). It will notice the smaller window size (via the kernel) and will show fewer lines per page — i.e., each “page” becomes shorter. You will see less text at once and need more presses of Space / Enter to move through the file.
2. If you press `v` inside `more`, it will attempt to open the file in `vi`/`vim`:
    - `vi` will also get the actual window size and adapt its layout.
    - But because the script exported `TERM=linux` unconditionally, `more` and `vi` will *think* the terminal type is `linux`. If your local terminal is actually an xterm, GNOME Terminal, iTerm2, etc., the control sequences `more`/`vi` expect may differ from what your terminal supports.
        - Worst case: screen drawing is garbled (weird characters), cursor movement or screen clearing misbehaves.
        - Likely case: things mostly work, but some advanced features (colors, certain cursor moves) may be wrong.
3. The forced `TERM=linux` **can make the UI look odd** when using a GUI terminal emulator resized to a small size, but the pagination itself will still respond to the smaller dimensions.

step4: so we have understood what the content of showtext do when we try to login to bandit26 so, we will make the tab screen small and try to login. and after that we will press button v . so that it will enter the editor mode. 

step5: so use command `:e /etc/bandit_pass/bandit26` and press enter , and you will get the password

![image alt](https://github.com/SongaPraneeth/CTF/blob/3d95217f6498d1b845e4fcc465afe215e5eea7c1/CTFs%20Write%20ups/images/bandit_images/bandit25.1.png)

![image alt](https://github.com/SongaPraneeth/CTF/blob/3d95217f6498d1b845e4fcc465afe215e5eea7c1/CTFs%20Write%20ups/images/bandit_images/bandit25.2.png)

as we know that the shell for the bandit26 is /bin/bash/showtext , so we show change that to /bin/bash, we will do that in the same vim editor 

![image alt](https://github.com/SongaPraneeth/CTF/blob/3d95217f6498d1b845e4fcc465afe215e5eea7c1/CTFs%20Write%20ups/images/bandit_images/bandit25.3.png)

![image alt](https://github.com/SongaPraneeth/CTF/blob/3d95217f6498d1b845e4fcc465afe215e5eea7c1/CTFs%20Write%20ups/images/bandit_images/bandit25.4.png)

![image alt](https://github.com/SongaPraneeth/CTF/blob/3d95217f6498d1b845e4fcc465afe215e5eea7c1/CTFs%20Write%20ups/images/bandit_images/bandit25.5.png)

![image alt](https://github.com/SongaPraneeth/CTF/blob/3d95217f6498d1b845e4fcc465afe215e5eea7c1/CTFs%20Write%20ups/images/bandit_images/bandit25.3.png)

![image alt](https://github.com/SongaPraneeth/CTF/blob/3d95217f6498d1b845e4fcc465afe215e5eea7c1/CTFs%20Write%20ups/images/bandit_images/bandit25.6.png)

![image alt](https://github.com/SongaPraneeth/CTF/blob/3d95217f6498d1b845e4fcc465afe215e5eea7c1/CTFs%20Write%20ups/images/bandit_images/bandit25.7.png)

![image alt](https://github.com/SongaPraneeth/CTF/blob/3d95217f6498d1b845e4fcc465afe215e5eea7c1/CTFs%20Write%20ups/images/bandit_images/bandit25.8.png)

now you will gain the bandit26 shell.