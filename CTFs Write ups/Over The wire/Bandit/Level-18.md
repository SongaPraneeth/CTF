Level Goal:

The password for the next level is stored in a file **readme** in the homedirectory. Unfortunately, someone has modified **.bashrc** to log you out when you log in with SSH.

Steps to solve:

step1 : Use command `ssh [bandit18@bandit.labs.overthewire.org](mailto:bandit18@bandit.labs.overthewire.org) -p 2220 "cat readme"` 

![image alt](https://github.com/SongaPraneeth/CTF/blob/3d95217f6498d1b845e4fcc465afe215e5eea7c1/CTFs%20Write%20ups/images/bandit_images/bandit18.png)

This command:

```bash
ssh bandit18@bandit.labs.overthewire.org -p 2220 "cat readme"

```

### Explanation:

- `ssh`: starts a secure shell connection.
- `bandit18@bandit.labs.overthewire.org`: logs in as user `bandit18` on that server.
- `p 2220`: connects to port 2220 instead of the default port 22.
- `"cat readme"`: runs the command `cat readme` on the remote server **right after connecting**, printing the content of the `readme` file.

### Key point:

The quotes around `"cat readme"` ensure the entire command is passed to the remote shell to execute, instead of opening an interactive session.

After printing the contents, the SSH session closes automatically. This is especially useful if the remote shell immediately logs you out, preventing interactive use.