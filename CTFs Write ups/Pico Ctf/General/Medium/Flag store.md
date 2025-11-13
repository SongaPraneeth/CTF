**Description:**
There's a flag shop selling stuff, can you buy a flag? Source. Connect with nc jupiter.challenges.picoctf.org 4906.

**Steps to solve:**

step1: First run the command `nc jupiter.challenges.picoctf.org 4906`. and it will ask for enter a menu selection, press 1 and check the balance it will be 1100.

step2: now press `2` and it will give two options press `1`and enter a number which will make the buffer overflow and the final cost will be in negative numbers and that value will be transferred to you account.   

step3: Now press enter to buy 1337 flag and you will get your flag.

Note : 

This is the code in source code, where issue occurs: 

`int number_flags = 0;
fflush(stdin);
scanf("%d", &number_flags);
if(number_flags > 0){
int total_cost = 0;
total_cost = 900*number_flags;
printf("\nThe final cost is: %d\n", total_cost);
if(total_cost <= account_balance){
account_balance = account_balance - total_cost;
printf("\nYour current balance after transaction: %d\n\n", account_balance);
}
else{
printf("Not enough funds to complete purchase\n");
}`

`}`

### What the code tries to do

It multiplies

```
total_cost = 900 * number_flags;

```

So if you enter `number_flags = 2,500,000`,

it tries to calculate

```
900 × 2,500,000 = 2,250,000,000

```

---

### What actually happens

The variable `total_cost` is an `int`.

On most systems, an `int` is **32 bits**, meaning it can only store values between:

```
-2,147,483,648  to  +2,147,483,647

```

Now look at your result:

```
2,250,000,000  >  2,147,483,647

```

That’s **too big** to fit in a 32-bit int.

So it **wraps around** — this is called **integer overflow**.

---

### In simple terms

Imagine your `int` is like a speedometer that goes up to 2,147,483,647.

When you push past that, it loops back to the negative side — just like a car’s odometer rolling over from 99999 to 00000.

So your `total_cost` will not be 2.25 billion; instead it will **become a negative number**.

---

### What happens next

- Since `total_cost` is negative, the condition
    
    ```c
    if (total_cost <= account_balance)
    
    ```
    
    will probably **be true** (because negative numbers are less than almost any positive balance).
    
- Then it does:
    
    ```c
    account_balance = account_balance - total_cost;
    
    ```
    
    But subtracting a negative value means **adding** — so your balance will **increase** instead of decreasing 
    
    ![image alt](https://github.com/SongaPraneeth/CTF/blob/33eda6bda3a3f5beac71d950140ed4b90264a9a9/CTFs%20Write%20ups/images/picoctf_images/general/Medium/flag_shop_1.png)
    
    ![image alt](https://github.com/SongaPraneeth/CTF/blob/33eda6bda3a3f5beac71d950140ed4b90264a9a9/CTFs%20Write%20ups/images/picoctf_images/general/Medium/flag_shop_2.png)