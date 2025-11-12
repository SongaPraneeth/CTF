Level Goal :

The credentials for the next level can be retrieved by submitting the password of the current level to **a port on localhost in the range 31000 to 32000**. First find out which of these ports have a server listening on them. Then find out which of those speak SSL/TLS and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.

Steps to solve :

step1 : Use `ncat --ssl 127.0.0.1 31790`  command and press enter and then enter the password of current level and press enter.

![image alt](https://github.com/SongaPraneeth/CTF/blob/3d95217f6498d1b845e4fcc465afe215e5eea7c1/CTFs%20Write%20ups/images/bandit_images/bandit16.png)

The command:

```bash
ncat --ssl 127.0.0.1 31790

```

means you're using **`ncat`** (a networking utility from the Nmap project) to connect to a **TCP server** on **localhost (127.0.0.1)** at **port 31790**, using **SSL/TLS encryption**.

---

### Breakdown of the command:

- `ncat`: A modern version of `netcat` (also known as `nc`), used for reading and writing data across networks.
- `-ssl`: Tells `ncat` to use **SSL/TLS** to encrypt the connection.
- `127.0.0.1`: The **loopback address**, referring to the local machine.
- `31790`: The **port number** you're connecting to.

---

### What happens when you run it?

You're opening an encrypted connection to a service running on your local machine on port 31790. What happens next depends on what's running on that port.

- If there's an SSL-enabled service listening, you'll establish a secure connection.
- If nothing is listening on that port, or if the service doesn't support SSL, you'll get a connection error.