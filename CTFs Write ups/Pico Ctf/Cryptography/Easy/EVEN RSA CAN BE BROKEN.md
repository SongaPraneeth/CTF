# EVEN RSA CAN BE BROKEN???

**Description:**

This service provides you an encrypted flag. Can you decrypt it with just N & e?

Additional details will be available after launching your challenge instance.

**Steps to solve:**

step1: After connecting to a remote server  using the command `nc verbal-sleep.picoctf.net 54924` , we will get `N`, `e`and `cipher text`

step2: Now use a website to decode RSA cipher text using `n` and `e` and `ciphertext`, i am using website https://www.dcode.fr/rsa-cipher

![image alt](https://github.com/SongaPraneeth/CTF/blob/bc7b51486dba5301ab4f66aec8dce913238ab4e7/CTFs%20Write%20ups/images/picoctf_images/Crypto/Easy/EVEN_RSA_CAN%20BE_BROKEN_2.png)


![image alt](https://github.com/SongaPraneeth/CTF/blob/bc7b51486dba5301ab4f66aec8dce913238ab4e7/CTFs%20Write%20ups/images/picoctf_images/Crypto/Easy/EVEN_RSA_CAN%20BE_BROKEN_1.png)

## RSA Algorithm — All Terms Explained

We’ll use one clear working example:

p=61, q=53

---

### **1️⃣ p and q → Prime numbers**

- These are two **randomly chosen prime numbers**.
- They must be **kept secret**.
- In real RSA, they’re hundreds of digits long.

> Example:
> 
> 
> p=61,q=53
> 

---

### **2️⃣ n = p × q → The modulus**

- This is used in both the **public** and **private keys**.
- It defines the “range” of RSA encryption.

n=61×53=3233

✅ **n = 3233**

This number **is public**.

---

### **3️⃣ φ(n) = (p−1)(q−1) → Euler’s Totient**

- φ(n) tells how many numbers below n are **coprime** with n.
- We use this to find e and d.

φ(n)=(61−1)×(53−1)=60×52=3120

✅ **φ(n) = 3120**

This number is **secret** (because p and q are secret).

---

### **4️⃣ e → Public exponent**

- We pick a number **e** that satisfies:
    1. 1<e<φ(n)1 
    2. gcd(e, φ(n)) = 1 → they must be **coprime**

Usually, we pick a small **prime** like 3, 17, or 65537.

Let’s check for 17:

gcd(17,3120)=1

✅ Works!

So **e = 17**

This number is **public** (it’s part of the public key).

---

### **5️⃣ d → Private exponent**

- This is the **modular inverse** of e mod φ(n).
    
    It satisfies:
    

d×e≡1(modφ(n))

In our case:

d×17≡1(mod3120)

We solve this using the **Extended Euclidean Algorithm** →

✅ **d = 2753**

This is **secret** — it’s the private key part.

---

### **6️⃣ Public and Private Keys**

| Key Type | Values | Use |
| --- | --- | --- |
| **Public Key** | (n, e) = (3233, 17) | Encryption |
| **Private Key** | (n, d) = (3233, 2753) | Decryption |

---

### **7️⃣ Encryption**

If you want to send a message M (in number form):

C = M^e \mod n

Let’s encrypt M=65:

C = 65^17 mod 3233 = 2790

✅ **Ciphertext = 2790**

---

### **8️⃣ Decryption**

To get the original message back:

M = C^d mod n

M = 2790^2753 mod 3233 = 65

✅ Original message (65) is recovered.

---

## 🔐 Summary Table

| Symbol | Meaning | Formula / How It’s Found | Example Value |
| --- | --- | --- | --- |
| **p, q** | Two large prime numbers | Chosen randomly | 61, 53 |
| **n** | Modulus for keys | p × q | 3233 |
| **φ(n)** | Totient (used to find e, d) | (p−1)(q−1) | 3120 |
| **e** | Public exponent | Coprime with φ(n) | 17 |
| **d** | Private exponent | (d × e) mod φ(n) = 1 | 2753 |
| **Public Key** | Used to encrypt | (n, e) | (3233, 17) |
| **Private Key** | Used to decrypt | (n, d) | (3233, 2753) |

---

### 🧠 In simple words:

- **p & q:** secret building blocks.
- **n:** public product used for encryption math.
- **φ(n):** helper to calculate valid e and d.
- **e:** public “lock” number.
- **d:** secret “unlock” number that undoes e.