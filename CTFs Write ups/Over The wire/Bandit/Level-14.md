Level Goal:

The password for the next level can be retrieved by submitting the password of the current level to **port 30000 on localhost**.

Steps to solve :

step1:  use command `telnet -4 [localhost](http://localhost) 30000`

step2: Then enter the password of current level

![image alt](https://github.com/SongaPraneeth/CTF/blob/fae3ccfc95a09337a2390be80f1cf34fbe0b90ce/CTFs%20Write%20ups/images/bandit_images/bandit14.1.png)

or 

step1 : use `nc [localhost](http://localhost) 3000` and enter current level password

![image alt](https://github.com/SongaPraneeth/CTF/blob/fae3ccfc95a09337a2390be80f1cf34fbe0b90ce/CTFs%20Write%20ups/images/bandit_images/bandit14.png)

the command you wrote is valid:

```bash
telnet -4 localhost 30000
```

### ✅ Here's what it does:

- `telnet`: Connects to a TCP port.
- `4`: Forces the use of **IPv4** (instead of IPv6).
- `localhost`: Refers to your local machine (`127.0.0.1`).
- `30000`: The TCP port you're connecting to.
    
    

### command:

```bash
nc localhost 30000

```

Then type (or paste) the **bandit14 password**, press **Enter**, and you'll receive the password for `bandit15`.