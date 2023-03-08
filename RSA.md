# RSA

### Resources


********************

### Overview

R: Ron Rives
S: Adi Shamir
A: Leonard Adleman

* The easy algorithm multiplies two prime numbers.
* Its difficult pair algorithm is factoring the product of the multiplication into its two component primes.

* Its security relies on the fact that factoring is slow and multiplication is fast.

* RSA relies on the fact that multiplying prime numbers to get a larger number is easy, while factoring huge numbers back to the original primes is much more difficult.


### Walkthrough

* Max value: is obtained by multiplying two randome prime numbers. The public and private keys are two specially chosen numbers such that 0 < (pub,priv) < max. This numbers are called **pub** and **priv**.

* Encrypt: The number chosen will be multiplied by itself *pub* times (it will be wrapped around when you hit the max).

* Decrypt: The message will be multiplied *priv* times and then you get back to the original number.

### RSA Key Pair creation

1. Multiply two prime random numbers and get the max.
2. Pick a number to be the public key *pub*.
3. Compute the private key *priv* from public key.

>This is how factoring relates to breaking RSA — factoring the maximum number into its component primes allows you to compute someone's private key from the public key and decrypt their private messages.

### Example

* Primes = 13 ^ 7 
* Product = 91 = max
* Pub = 5
* We use the extended euclidean algorithm and primes and max we get that the private key is the number 29.

* System = (max=91,pub=5,priv=29)

***

Encrypt now the message **CLOUD**: 

1. We turn the letters into numbers using UTF-8: 

```
C = 67
L = 76
O = 79
U = 85
D = 68
```

Because each digit is smaller than *max*, we will encrypt each of them individually

```
67*67 = 4489 = 30 *
```

Here, we have to wrap 4489 because it is bigger than max. To wrap it is nothing more than making the number modulo max and taking the remainder.

```
4489 = 91 * 49 + 30

30 * 67 = 2010 = 8

8 * 67 = 536 = 81

81 * 67 = 5427 = 58
```

This means the encrypted version of 67 is 58

Final message: 58,20,53,50,87

Decrypt message: We take each number and multiply it by itself 29 times

```
58*58 = 3364 = 88 
```

why 88? Because once again we have to wrap it around the max.

```
88 * 58 = 5104 = 8
....
9 * 58 = 522 = 67
```

******

### Efficiency 

* These factoring algorithms get more efficient as the size of the numbers being factored get larger.

* The gap between the difficulty of factoring large numbers and multiplying large numbers is shrinking as the number (i.e. the key's bit length) gets larger.

* The gap between factoring and multiplying is not sustainable in the long term.

* To remain secure, RSA needs keys that are 2048 bits or longer. 

>the mathematics and computational power required to factor large numbers and ‘break’ RSA keys have become increasingly more available and practical for attackers to use. To counter the threats posed by advanced computing and mathematics, RSA key sizes need to grow, which becomes unsustainable in the long-term.


