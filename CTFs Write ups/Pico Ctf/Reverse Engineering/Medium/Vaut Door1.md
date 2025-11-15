Description:

This vault uses some complicated arrays! I hope you can make sense of it, special agent. The source code for this vault is here: VaultDoor

Steps to solve:

step1: Here we have a java file, lets see what inside the file using `cat VaultDoor1.java`

step2: Here in the code, 

```bash
if (vaultDoor.checkPaspisword(input)) {
System.out.println("Access granted.");
}
```

The function `checkPassword` is being called with a `parameter`, which is `input`

```bash
public boolean checkPassword(String password) {
return password.length() == 32 &&
password.charAt(0)  == 'd' &&
password.charAt(29) == '3' &&
password.charAt(4)  == 'r' &&
password.charAt(2)  == '5' &&
password.charAt(23) == 'r' &&
password.charAt(3)  == 'c' &&
password.charAt(17) == '4' &&
password.charAt(1)  == '3' &&
password.charAt(7)  == 'b' &&
password.charAt(10) == '*' &&
password.charAt(5)  == '4' &&
password.charAt(9)  == '3' &&
password.charAt(11) == 't' &&
password.charAt(15) == 'c' &&
password.charAt(8)  == 'l' &&
password.charAt(12) == 'H' &&
password.charAt(20) == 'c' &&
password.charAt(14) == '*' &&
password.charAt(6)  == 'm' &&
password.charAt(24) == '5' &&
password.charAt(18) == 'r' &&
password.charAt(13) == '3' &&
password.charAt(19) == '4' &&
password.charAt(21) == 'T' &&
password.charAt(16) == 'H' &&
password.charAt(27) == 'f' &&
password.charAt(30) == 'b' &&
password.charAt(25) == '_' &&
password.charAt(22) == '3' &&
password.charAt(28) == '6' &&
password.charAt(26) == 'f' &&
password.charAt(31) == '0';
}
```

In the function, length of the password is checked and then

each index of the user input is compared with a specific character, These characters used for comparison are actually the real password characters, but the index's are shuffled. So i wrote a code. Below you can see the code and also the explanation. 

![image alt](https://github.com/SongaPraneeth/CTF/blob/f8114b8cc97b2dab599d3d2c0608d95f2b565493/CTFs%20Write%20ups/images/picoctf_images/Reverse/Medium/vault-door_1.png)

![image alt](https://github.com/SongaPraneeth/CTF/blob/f8114b8cc97b2dab599d3d2c0608d95f2b565493/CTFs%20Write%20ups/images/picoctf_images/Reverse/Medium/vault-door_2.png)

```python
password = [''] * 32

print(len(password))
password[0]  = 'd' 
password[29] = '3' 
password[4]  = 'r' 
password[2]  ='5' 
password[23] = 'r' 
password[3]  = 'c' 
password[17] = '4' 
password[1]  = '3' 
password[7]  = 'b' 
password[10] = '_' 
password[5]  = '4' 
password[9]  = '3' 
password[11] = 't' 
password[15] = 'c' 
password[8]  = 'l' 
password[12] = 'H' 
password[20] = 'c' 
password[14] = '_' 
password[6]  = 'm' 
password[24] ='5' 
password[18] = 'r' 
password[13] = '3' 
password[19] = '4' 
password[21] = 'T' 
password[16] = 'H' 
password[27] = 'f' 
password[30] = 'b' 
password[25] = '_' 
password[22] = '3' 
password[28] = '6' 
password[26] = 'f'
password[31] = '0'

a = ''.join(password)
  
print(f"picoCTF{{{a}}}")
```

### **1. Creating a list of 32 empty strings**

```python
password = [''] * 32

```

This creates a list of length **32**, where each element is an empty string:

```
['', '', '', '', ..., '']

```

We will later fill each position with the correct character of the password.

---

### **2. Assigning characters to specific index positions**

```python
password[0]  = 'd'
password[29] = '3'
password[4]  = 'r'
password[2]  = '5'
password[23] = 'r'
password[3]  = 'c'
password[17] = '4'
password[1]  = '3'
password[7]  = 'b'
password[10] = '_'
password[5]  = '4'
password[9]  = '3'
password[11] = 't'
password[15] = 'c'
password[8]  = 'l'
password[12] = 'H'
password[20] = 'c'
password[14] = '_'
password[6]  = 'm'
password[24] = '5'
password[18] = 'r'
password[13] = '3'
password[19] = '4'
password[21] = 'T'
password[16] = 'H'
password[27] = 'f'
password[30] = 'b'
password[25] = '_'
password[22] = '3'
password[28] = '6'
password[26] = 'f'
password[31] = '0'

```

These assignments come from the **JavaScript code** used in the challenge.

Each index represents the correct position of every character in the final password.

At the end, the list becomes something like:

```
['d','3','5','c','r', ... '0']

```

---

### **3. Joining the list into a single string**

```python
a = ''.join(password)

```

The list gets combined into one continuous string without spaces:

```
d35cr4b...f0

```

This is the recovered password.

---

### **4. Printing the flag using an f-string**

```python
print(f"picoCTF{{{a}}}")

```

In a Python f-string:

- `{{` → prints a literal `{`
- `{a}` → inserts the value of variable `a`
- `}}` → prints a literal `}`

So the output becomes:

```
picoCTF{d35cr4b_lHHTc...f0}

```

This is the final flag.

After executing the code we will get the flag: 

![image alt](https://github.com/SongaPraneeth/CTF/blob/f8114b8cc97b2dab599d3d2c0608d95f2b565493/CTFs%20Write%20ups/images/picoctf_images/Reverse/Medium/vault-door_3.png)
