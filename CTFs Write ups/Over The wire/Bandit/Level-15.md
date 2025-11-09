**Level Goal:**

The password for the next level can be retrieved by submitting the password of the current level to **port 30001 on localhost** using SSL/TLS encryption.

Steps to solve: 

step1: Use command `openssl s_client -connect [localhost:30001](http://localhost:30001)` to connect to the host at the port 

step2: After connect enter the password of current level and press enter and you will get the password for next level

![image alt](https://github.com/SongaPraneeth/CTF/blob/fae3ccfc95a09337a2390be80f1cf34fbe0b90ce/CTFs%20Write%20ups/images/bandit_images/bandit15.png)

![image alt](https://github.com/SongaPraneeth/CTF/blob/fae3ccfc95a09337a2390be80f1cf34fbe0b90ce/CTFs%20Write%20ups/images/bandit_images/bandit15.1.png)

![image alt](https://github.com/SongaPraneeth/CTF/blob/fae3ccfc95a09337a2390be80f1cf34fbe0b90ce/CTFs%20Write%20ups/images/bandit_images/bandit15.2.png)

Here's a simple breakdown of the command:

```bash
openssl s_client -connect localhost:30001
```

### Breakdown:

- `openssl`
    
    This is the main command to run the OpenSSL toolkit.
    
- `s_client`
    
    This tells OpenSSL to act as an SSL/TLS **client** and try to connect to a server using SSL/TLS.
    
- `connect localhost:30001`
    
    This specifies the **address and port** to connect to:
    
    - `localhost` means your own computer (127.0.0.1).
    - `30001` is the port number on which the server is listening.

---

### What happens when you run this?

- OpenSSL tries to **open a secure SSL/TLS connection** to the server on your machine at port 30001.
- It performs the **TLS handshake** (the process to establish a secure connection).
- It prints details like:
    - Server certificates
    - TLS version and cipher used
    - Connection status
- After connection, you can **type data manually** to send to the server over this secure connection.